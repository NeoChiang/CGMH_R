��¦��Ǹ�Ʊ�������
========================================================
author: ������� ���N�� Yi-Ju Tseng
autosize: true
font-family: 'Microsoft JhengHei'
navigation: slide


�j��
====================================
type:sub-section 

- ����O��Ʊ���
- Regression �j�k
- Decision Trees �M����
- �ҫ�����
- �į����
- `caret` package

����O��Ʊ���
====================================

�إ߱q**��J���**�ǲ߷s��T�A�ܦ����z��**�t��k**��**��ƼҦ�**�A�Ψ�**�w���ƥ�**��**��U�M��**

- �ΤH�u���z�B�����ǲߡB�έp�ǵ���k
- �b�۹���j������ƶ����o�{�Ҧ����p��L�{
- ���Ƥ�`��`��`��ż`���ɭԡA��Ʊ��ɪ��ĤO�|�Q�v�T

��Ʊ��ɱ���
====================================
��Ʊ��ɭn���W�γ��A�������H�U����G

- ���@�ǼҦ�/�ҫ��i`��`
- �����w�q�o�ǼҦ�/�ҫ�
- ����ƥi`��`�o�ǼҦ�/�ҫ�

��Ʊ��ɥi���Φb
====================================

- ���Ĺw���]�O�_�|�_�o�B��_����...���^
- �E�_�ҫ��]�E�_�Ҧ��ǲ�...���^
- �Ͷչw���]�y�P�רҼƹw��...���^
- �e�f���s

��Ʊ��ɪ�����
====================================

- **�ʷ���**�ǲ߻P**�D�ʷ���**�ǲ�
- **�ʷ����ǲ�**���S�I�O�V�m��Ƥ���**���T����**�A�ѿ�J����M�w����X�Ҳզ��A�Ӻt��k�i�H�ѰV�m��Ƥ��Ǩ�Ϋإߤ@�ӼҦ��A�è̦��Ҧ������s�����
- **�D�ʷ����ǲ�**�h���δ���**���T����**�A�]�N�O���ݭn�H�O�ӿ�J���ҡA��§Q�ΰV�m��ƪ��S�ʡA�N��Ƥ��s���աC

��Ʊ��ɪ�����
====================================

- Supervised learning �ʷ����ǲ�
    - Regression �j�k�G�u�ꪺ'��'�]�y�P�רҼơB��_�q���^
    - Classification �����G�������]P/N, Yes/No, M/F, Sick/Not sick�^/���h�� (Type A/Type B/Type C/Type D)

- Unsupervised learning �D�ʷ����ǲ�
    - Clustering ���s
    - Association Rules ���p���W�h

�ʷ����ǲ�
====================================

�b**�ʷ���**�ǲߤ��`������Ʊ��ɺt��k�p�U�G 
  - Linear Regression �u�ʰj�k (��X:�s���)
  - Logistic Regression ù�N���j�k�B�޿�j�k (��X:�G��)
  - Support Vector Machines ����V�q�� (��X:�s���/�G��)
  - Decision Trees �M���� (��X:�s���/�G��)
  - K-Nearest Neighbor
  - Neural Networks ���g����
  - Deep Learning �`�׾ǲ�

�D�ʷ����ǲ�
====================================

�b**�D�ʷ���**�ǲߤ��`������Ʊ��ɺt��k�p�U�G 
  - Hierarchical clustering ���h�����s
  - K-means clustering
  - Neural Networks ���g����
  - Deep Learning �`�׾ǲ�


Regression �j�k
====================================

- �Φb�F�Ѩ�өΦh���ܼƶ�`�O�_����`�B`������V`�P`�j��`
- �إ�`�ƾǼҫ�`�H�K�[��S�w�ܼƨӹw����s�̷P���쪺�ܼ�

�`�����j�k���R�t��k�]�A�G

- Linear Regression �u�ʰj�k (��X:�s���)
- Logistic Regression ù�N���j�k�B�޿�j�k (��X:�G��)

Linear Regression �u�ʰj�k
====================================

- ���ձNLinear Regression �u�ʰj�k�Φb�Ѫǹ������ͪ����Ϊ����
- ���Ѫǹ�`��������`�P`���L�RC���q`���u�ʰj�k�[��

```r
# install.packages("mlbench")
library(mlbench)
# The Effect of Vitamin C on Tooth Growth in Guinea Pigs
data("ToothGrowth")
knitr::kable(head(ToothGrowth))
```



|  len|supp | dose|
|----:|:----|----:|
|  4.2|VC   |  0.5|
| 11.5|VC   |  0.5|
|  7.3|VC   |  0.5|
|  5.8|VC   |  0.5|
|  6.4|VC   |  0.5|
| 10.0|VC   |  0.5|


lm()
====================================

- �bR���A�̰򥻪�²��u�ʰj�k���R��`lm()`
- `lm(formula,data=��ƦW��)`�A�f�tformula�ϥ�
- formula�����g��k���G**���ܶ�~���ܶ�1�Ϧ��ܶ�2��**....
- ���R�Ѫǹ�`��������`�P`���L�RC���q`�����Y�d��

```r
lm(len~dose,
   data =ToothGrowth)
```

```

Call:
lm(formula = len ~ dose, data = ToothGrowth)

Coefficients:
(Intercept)         dose  
      7.423        9.764  
```

len = `9.764` * dose + `7.423`

glm()
====================================
- ��Q�s�x�ϥΪ��O�s�q�u�ʰj�k�ҫ�generalized linear models (glm)�A`glm()`
- �ϥΤ�k�P`lm()`����
- �]�A�u�ʰj�k�ҫ��M�޿�j�k�ҫ�
- �p�G�ݭn�ק�w�]�ҫ��A�i�]�wfamily�ѼơG
    - `family="gaussian"` �u�ʼҫ��ҫ�
    - `family="binomial"` �޿�j�k�ҫ�
    - `family="poisson"` �R�˪Q�j�k�ҫ�
    
Gaussian distribution
====================================
Gaussian distribution������ƬO`�`�A����`���K�ר��

![plot of chunk unnamed-chunk-1](https://upload.wikimedia.org/wikipedia/commons/a/a9/Empirical_Rule.PNG)

Binomial distribution
====================================
Binomial distribution�G�������O`n�ӿW�ߪ��O/�D���礤���\������`���������v����
![plot of chunk unnamed-chunk-2](https://upload.wikimedia.org/wikipedia/commons/thumb/1/17/Pascal%27s_triangle%3B_binomial_distribution.svg/794px-Pascal%27s_triangle%3B_binomial_distribution.svg.png)

Poisson distribution
====================================
Poisson distribution`����`���G�G

- �Y�@�A�ȳ]�I�b�@�w�ɶ������쪺�A�ȽШD������
- ���������ԫȤH��
- �۵M�a�`�o�ͪ�����

![plot of chunk unnamed-chunk-3](https://upload.wikimedia.org/wikipedia/commons/thumb/1/16/Poisson_pmf.svg/360px-Poisson_pmf.svg.png)

�s�q�u�ʰj�k�P�Ѫǹ�����������
====================================
���R�Ѫǹ�`��������`�P`���L�RC���q`�H��`Supplement type`�����Y�d��

```r
glm(len ~ supp+dose,
    data =ToothGrowth)
```

```

Call:  glm(formula = len ~ supp + dose, data = ToothGrowth)

Coefficients:
(Intercept)       suppVC         dose  
      9.272       -3.700        9.764  

Degrees of Freedom: 59 Total (i.e. Null);  57 Residual
Null Deviance:	    3452 
Residual Deviance: 1023 	AIC: 348.4
```
len = `-3.700` * suppVC + `9.764` * dose + `9.272`

�����ܶ� Dummy Variable
====================================
- `Supplement type`���ܶ��Q�ର**�����ܶ� Dummy Variable**
- suppVC
- �p�G�OOJ(��Ƕ�)�A�|�o��G
  - suppVC=0
  
�u�ʰj�k�m��
====================================
type:alert
- ��[BostonHousing](https://archive.ics.uci.edu/ml/datasets/Housing)���


```r
install.packages("mlbench")
library(mlbench)
data(BostonHousing)
```

- �ϥ�crim�Btax�Bdis���w��medv(Median value of owner-occupied homes in $1000's)
  - glm()�s�q�u�ʰj�k

�u�ʰj�k�`��
====================================
�`���H�W�A�h�ܶq�u�ʰj�k���R���U�C�S��G

- ���]�G�U�ܼƬۤ��W�ߡI
- �Y���ܶ�X�O���O�ܶ��A�ݭn�إ�`�����ܶ�`
- �bR�̡A`���O�ܶ�`�аO�o�নfactor�AR�|�۰ʫإ�`�����ܶ�`
- �Φb`���ܼƬ��s���ܼ�`�A`���ܼƬ��s���ܼƩε����ܼ�`�����X


Logistic Regression ù�N���j�k
====================================

�`�Φb`���ܼƬ��G���ܼơ]�D0�Y1�^`�����X�A�p�G
  - �ͯf/�S�ͯf
  - ����/������
  - `family="binomial"` ù�N���j�k�ҫ�

Logistic Regression ù�N���j�k
====================================
- ���ձNLogistic Regression ù�N���j�k�Φb�}���f�����

```r
library(mlbench)
data("PimaIndiansDiabetes2")
#�h������|�Ȫ����
PimaIndiansDiabetes2<-
  PimaIndiansDiabetes2[complete.cases(PimaIndiansDiabetes2),]
```

���R�O�_�o�}���f�H
====================================

```r
head(PimaIndiansDiabetes2)
```

|   | pregnant| glucose| pressure| triceps| insulin| mass| pedigree| age|diabetes |
|:--|--------:|-------:|--------:|-------:|-------:|----:|--------:|---:|:--------|
|4  |        1|      89|       66|      23|      94| 28.1|    0.167|  21|neg      |
|5  |        0|     137|       40|      35|     168| 43.1|    2.288|  33|pos      |
|7  |        3|      78|       50|      32|      88| 31.0|    0.248|  26|pos      |
|9  |        2|     197|       70|      45|     543| 30.5|    0.158|  53|pos      |
|14 |        1|     189|       60|      23|     846| 30.1|    0.398|  59|pos      |
|15 |        5|     166|       72|      19|     175| 25.8|    0.587|  51|pos      |

���R�O�_�o�}���f�H
====================================
- ��`�o�}���f�P�_`�P`�h��`+`BMI`+`��}`+`triceps`��ù�N���j�k�[��

```r
mylogit <- 
  glm(diabetes ~ pregnant+glucose+triceps+mass,
      data = PimaIndiansDiabetes2, 
      family = "binomial")
sum<-summary(mylogit)
```

```r
sum$coefficients
```

|            |   Estimate| Std. Error|   z value| Pr(>&#124;z&#124;)|
|:-----------|----------:|----------:|---------:|------------------:|
|(Intercept) | -8.8083182|  0.9733009| -9.049944|          0.0000000|
|pregnant    |  0.1433008|  0.0406067|  3.528997|          0.0004171|
|glucose     |  0.0382373|  0.0048203|  7.932506|          0.0000000|
|triceps     |  0.0189975|  0.0165837|  1.145551|          0.2519809|
|mass        |  0.0635506|  0.0253800|  2.503965|          0.0122810|

ù�N���j�k�m��
====================================
type:alert
- ��[PimaIndiansDiabetes2](https://archive.ics.uci.edu/ml/datasets/Pima+Indians+Diabetes)���


```r
install.packages("mlbench")
library(mlbench)
data(PimaIndiansDiabetes2)
PimaIndiansDiabetes2<-
  PimaIndiansDiabetes2[complete.cases(PimaIndiansDiabetes2),]
```

- �ϥΥ������w��diabetes
  - diabetes ~ **.**
  - glm()�s�q�u�ʰj�k
  - family = "binomial"

�̨μҫ��z��
====================================

�쩳�ӥέ��Ӽҫ��ӹw���A�ҫ��t�A�׷|�̦n�H�b�j�k�ҫ����A�`�Ϊ��P�_�ǫh�]�A�G

  - Akaike��s Information Criterion (AIC)
  - Bayesian Information Criterion (BIC)

AIC
====================================
AIC�MBIC���O�ƭȶV�p�V�n�A�H�U�إߤT�Ӽҫ��A�ä����AIC

```r
OneVar<-glm(diabetes ~ mass,
               data = PimaIndiansDiabetes2, 
               family = "binomial")
TwoVar<-glm(diabetes ~ triceps+mass,
               data = PimaIndiansDiabetes2, 
               family = "binomial")
ThreeVar<-glm(diabetes ~ glucose+triceps+mass,
               data = PimaIndiansDiabetes2, 
               family = "binomial")
```

AIC
====================================

```r
c(OneVar$aic,TwoVar$aic,ThreeVar$aic)
```

```
[1] 473.0310 470.5486 377.4528
```

�Ҧ��ѼƳ����ζܡH
====================================
- �b�إ߰j�k�ҫ��ɡA�`�|�J�쪺���D�G�쩳�ө�h�ְѼơH
- �Ҧ��ѼƳ����ζܡH
- �ǥ��[��coefficients�ӧP�_�ѼƦb�ҫ�����"��ε{��"

```r
sum2<-summary(TwoVar)
sum2$coefficients
```

|            |   Estimate| Std. Error|   z value| Pr(>&#124;z&#124;)|
|:-----------|----------:|----------:|---------:|------------------:|
|(Intercept) | -3.5327637|  0.5917333| -5.970196|          0.0000000|
|triceps     |  0.0298567|  0.0141633|  2.108036|          0.0350278|
|mass        |  0.0574192|  0.0215457|  2.664997|          0.0076989|

�Ҧ��ѼƳ����ζܡH
====================================

```r
sum3<-summary(ThreeVar)
sum3$coefficients
```

|            |   Estimate| Std. Error|   z value| Pr(>&#124;z&#124;)|
|:-----------|----------:|----------:|---------:|------------------:|
|(Intercept) | -8.2515186|  0.9307316| -8.865626|          0.0000000|
|glucose     |  0.0405379|  0.0048409|  8.374035|          0.0000000|
|triceps     |  0.0266201|  0.0162911|  1.634024|          0.1022537|
|mass        |  0.0469444|  0.0245083|  1.915454|          0.0554347|

Decision Trees �M����
====================================
- �b`�𪬥ؿ�`���إߤ@�t�C���ΡA�H�إ߼ҫ�
- �o�Ǥ��η|��ܦ�`�u�`�I�v(Node)`
- �C���o�{��J��Ʀ�P�i�w����Ʀ榳����a�ۤ����p�ɡA���t��k�N�|�b�ҫ����[�J�@��`�`�I`
- �t��k�M�w���ê��覡���P

![plot of chunk unnamed-chunk-9](05DataMining-figure/unnamed-chunk-9-1.png)

Classification And Regression Tree (CART)
====================================
- �`����Classification And Regression Tree (CART)
- �ϥΫe�����w��`rpart` packages


```r
install.packages("rpart")
```

CART
====================================
- ���եΥ�pregnant+glucose+triceps+mass�ӧP�_�O�_�o�}���f
- �إߨM���𪺨�Ƭ�`rpart()`
- �ϥΤ覡��`rpart(formula, data)`

```r
library(rpart)
DT<-rpart(diabetes ~ pregnant+glucose+triceps+mass,
          data=PimaIndiansDiabetes2)
DT
```

```
n= 392 

node), split, n, loss, yval, (yprob)
      * denotes terminal node

  1) root 392 130 neg (0.6683673 0.3316327)  
    2) glucose< 127.5 241  36 neg (0.8506224 0.1493776) *
    3) glucose>=127.5 151  57 pos (0.3774834 0.6225166)  
      6) glucose< 165.5 105  52 pos (0.4952381 0.5047619)  
       12) triceps< 22.5 20   3 neg (0.8500000 0.1500000) *
       13) triceps>=22.5 85  35 pos (0.4117647 0.5882353)  
         26) pregnant< 7.5 64  31 pos (0.4843750 0.5156250)  
           52) glucose>=134.5 49  20 neg (0.5918367 0.4081633)  
            104) mass< 30.25 11   2 neg (0.8181818 0.1818182) *
            105) mass>=30.25 38  18 neg (0.5263158 0.4736842)  
              210) mass>=32.4 30  11 neg (0.6333333 0.3666667)  
                420) glucose>=141.5 22   6 neg (0.7272727 0.2727273) *
                421) glucose< 141.5 8   3 pos (0.3750000 0.6250000) *
              211) mass< 32.4 8   1 pos (0.1250000 0.8750000) *
           53) glucose< 134.5 15   2 pos (0.1333333 0.8666667) *
         27) pregnant>=7.5 21   4 pos (0.1904762 0.8095238) *
      7) glucose>=165.5 46   5 pos (0.1086957 0.8913043) *
```

CART
====================================

```r
par(mfrow=c(1,1), mar = rep(1,4)) #�U,��,�W,�k
plot(DT)
text(DT, use.n=F, all=F, cex=1)
```

![plot of chunk rpart3](05DataMining-figure/rpart3-1.png)

�M�����
====================================
���`rpart.plot` package �̭���`prp()`

```r
#�Ĥ@���ϥΫe�����w��
install.packages("rpart.plot") 
```

```r
library(rpart.plot)
prp(DT)	
```

![plot of chunk rpart4](05DataMining-figure/rpart4-1.png)

�M���� �`�I
====================================
�M����t��k�M�w`�`�I`���覡�p�U�G

- Gini impurity
- Information gain
- Variance reduction

�Ӹ`�i�Ѧ�[����ʬ�](https://en.wikipedia.org/wiki/Decision_tree_learning)


�M���� �m��
====================================
type:alert
- ��[PimaIndiansDiabetes2](https://archive.ics.uci.edu/ml/datasets/Pima+Indians+Diabetes)���


```r
install.packages("mlbench")
library(mlbench)
data(PimaIndiansDiabetes2)
PimaIndiansDiabetes2<-
  PimaIndiansDiabetes2[complete.cases(PimaIndiansDiabetes2),]
```

- �ϥΨM����t��k�A�åΩҦ����w��diabetes
  - diabetes~.
- �ϥ�rpart.plot�M��e�X�M����
  - prp()


�ҫ�����
====================================
- �b�����ҫ��V�m��A���F���Ҽҫ��V�m���n���n�A�ݭn�Τ@��**�W��**�����ո�ơA�Ӱ��ҫ�������
- �b�V�m�ҫ��e�A�����S�O�d�N�O�_���O�d�@��**�W�ߪ����**�A�ýT�O�b�V�m�ҫ��ɳ����Ψ즹�W�߸�ƶ��C

�]���A��ƶ��i�����H�U��ءG

- **�V�m��** Training set, Development set: ���t��k`��`��`����`
- **���ղ�** Test set, Validation set: ����`��`������

�ҫ�����
====================================
- Training set�MTest set�q�`�|��Ҥ��t
  - �p2/3����Ƴ]��`Training set`
  - �ѤU��1/3������`Test set`
- �H�U�Ϫ��ʷ����ǲ߬y�{�Ϭ��ҡA�i�H�`�N����b�Y����ƶ��b�V�m�L�{���q���Q�ϥΡC


�ҫ�����
====================================
![plot of chunk unnamed-chunk-11](figures/traintest1.PNG)

�ҫ�����
====================================
![plot of chunk unnamed-chunk-12](figures/traintest2.PNG)

�ҫ�����
====================================
![plot of chunk unnamed-chunk-13](figures/traintest3.PNG)

�ҫ�����
====================================
![plot of chunk unnamed-chunk-14](figures/traintest4.PNG)


�ҫ�����
====================================
- �HTraining set��`��ݰ_�ӳ̦n���ҫ�`
- ��Test set��`���Ҽҫ��O���O�u���ܦn`

- �V�m�ҫ��ɡA�u���Training set�A��Training set�ӿ�@�ӳ̦n���ҫ�
- �V�m�ҫ��ɡA���ఽ��Test set�A�~�O�u��������


�ҫ�����
====================================
![plot of chunk unnamed-chunk-15](figures/SupervisedLearning.png)

Regression �j�k����
====================================

- �HPimaIndiansDiabetes��Ƭ��ҡA�������N���Ū�J
- ���צ����Ϩ⭱�ɡA��ĳ`Level 2 �񥿭�����`-->���f/����...

```r
library(mlbench)
data("PimaIndiansDiabetes2")
PD2<-
  PimaIndiansDiabetes2[complete.cases(PimaIndiansDiabetes2),]
head(PD2$diabetes)
```

```
[1] neg pos pos pos pos pos
Levels: neg pos
```

Regression �j�k���ҡG��Ƥ���
====================================
�����X�V�m�ջP���ղաA�ݨϥ��H����˪��覡

```r
sample(1:10,3) # �q1��10�A�H�����T�ӼƦr
```

```
[1] 4 3 5
```

```r
#�q�Ĥ@�C��̫�@�C�A�H����1/3�C��
sample(1:nrow(PD2),nrow(PD2)/3) 
```

```
  [1] 134  14 150 121 158  27 315 370  10 344 289 204 176 323 278 140 245
 [18] 237 196 145 336  93  42 166 262 205 290 239 131 125 266 157 160  46
 [35] 220 342 189  16 297 332 378 296 282 358 346  65 231 209 111  95 133
 [52] 359 165 287 351 339 253 313  17 218 185 193 367 347  54 219 210 100
 [69]  75 159 271 153 124 214 337 343  91 368 369 291 188 103 246 232 241
 [86] 361 303  44 350 331  41 283 338 168 280 171 257 102 108 147 169 116
[103] 211  15 389 226 286 199 340 162 330 137  73 222 234 184 104 224   6
[120] 173 272 192 109 270  31 300 352 128 288  92
```

Regression �j�k���ҡG��Ƥ���
====================================
�ϥ��H����˪k�A��X1/3��������m�A��f�H����Ƥ���Training �M Test set

```r
PD2$Test<-F #�s�W�@�ӰѼƬ�������
#�H����1/3��Test set
PD2[sample(1:nrow(PD2),
           nrow(PD2)/3),]$Test<-T
# Training set : Test set�f�H��
c(sum(PD2$Test==F),
  sum(PD2$Test==T))
```

```
[1] 262 130
```

Regression �j�k���ҡG�ҫ��V�m
====================================
�åΰV�m�ժ���ơ]PD2$Test==F�^�A�V�m�@�Ӧh�ܼ�ù�N���j�k�ҫ�

```r
fit<-glm(diabetes~.,
         data =PD2[PD2$Test==F,],
         family = "binomial")
summary(fit)$coefficients
```

```
                 Estimate  Std. Error    z value     Pr(>|z|)
(Intercept) -10.016523913 1.448643879 -6.9144143 4.698004e-12
pregnant      0.096983449 0.071464122  1.3570929 1.747517e-01
glucose       0.041142145 0.006850398  6.0058038 1.903863e-09
pressure     -0.004148344 0.014798056 -0.2803303 7.792241e-01
triceps       0.019917547 0.020862465  0.9547073 3.397257e-01
insulin      -0.002105727 0.001596001 -1.3193766 1.870432e-01
mass          0.061880842 0.033564590  1.8436347 6.523640e-02
pedigree      1.016508125 0.515786814  1.9707912 4.874776e-02
age           0.033967061 0.025600476  1.3268136 1.845703e-01
```

Regression �j�k���ҡG�v�B��ܼҫ�
====================================
�v�B��ܼҫ� stepwise ��h�ǲߡG�@�}�l���N�Ҧ��Ѽƥ[��ҫ��̡A�A�@�Ӥ@�Ӯ���

```r
library(MASS)
##�ھ�AIC�A���v�B���, �w�]�˰h�ǲ� direction = "backward"
##trace=FALSE: ���n��ܨB�J
finalModel_B<-
    stepAIC(fit,
            direction = "backward",
            trace=FALSE)
summary(finalModel_B)$coefficients
```

```
               Estimate  Std. Error   z value     Pr(>|z|)
(Intercept) -9.80735378 1.300682833 -7.540158 4.694032e-14
pregnant     0.09848888 0.069893331  1.409131 1.587963e-01
glucose      0.03685605 0.005974444  6.168951 6.874438e-10
mass         0.06987270 0.025043480  2.790056 5.269901e-03
pedigree     0.98399595 0.508322422  1.935771 5.289572e-02
age          0.03514935 0.024271680  1.448163 1.475715e-01
```

Regression �j�k���ҡG�v�B��ܼҫ�
====================================
�v�B��ܼҫ� stepwise ���V�ǲߡG�Ѽƥ[�[���

```r
##�ھ�AIC�A���v�B���, ���V�ǲ� direction = "both"
finalModel_Both<-
    stepAIC(fit,
            direction = "both",
            trace=FALSE)
summary(finalModel_Both)$coefficients
```

```
               Estimate  Std. Error   z value     Pr(>|z|)
(Intercept) -9.80735378 1.300682833 -7.540158 4.694032e-14
pregnant     0.09848888 0.069893331  1.409131 1.587963e-01
glucose      0.03685605 0.005974444  6.168951 6.874438e-10
mass         0.06987270 0.025043480  2.790056 5.269901e-03
pedigree     0.98399595 0.508322422  1.935771 5.289572e-02
age          0.03514935 0.024271680  1.448163 1.475715e-01
```

Regression �j�k���ҡG�ҫ�����
====================================
- ��Test set�ӵ����ҫ��n���n
- �ϥ�predict��ơA�N���ղո�Ʃ�J�w���ҫ���
  - type = "response": y�� 1 �����v
- �N�w���GpredictPoint����B�ഫ�A>0.5���ഫ��"pos"�A�N���o�}���f�A���ഫ��factor
  - levels=c("pos","neg")�A�N����(���f/���_�o)�]�w��level 2�A��K��Ū

```r
predictPoint<-
    predict(finalModel_Both,
            PD2[PD2$Test==T,],
            type = "response")
DMAns<-factor(ifelse(predictPoint>0.5,"pos","neg"),
                 levels=c("pos","neg"))
head(DMAns)
```

```
  4  14  15  28  40  51 
neg pos neg neg pos neg 
Levels: pos neg
```

Regression �j�k���ҡG�ҫ�����
====================================
- ��Test set�ӵ����ҫ��n���n
- �ϥ�predict��ơA�N���ղո�Ʃ�J�w���ҫ���
  - type = "response": y�� 1 �����v
- �N�w���GpredictPoint����B�ഫ�A>0.5���ഫ��"1"�A�N���o�}���f�A���ഫ��factor
  - levels=c(0,1)�A�N����(���f/���_�o)�]�w��level 2�A��K��Ū

```r
table(x=DMAns,
    y=PD2[PD2$Test==T,"diabetes"]) 
```

```
     y
x     neg pos
  pos   6  28
  neg  73  23
```

Regression �j�k���ҡG�ҫ�����
====================================
- ��Test set�ӵ����ҫ��n���n
- �ϥ�predict��ơA�N���ղո�Ʃ�J�w���ҫ���

```r
plot(x=PD2[PD2$Test==T,"diabetes"],
     y=predictPoint)
```

![plot of chunk unnamed-chunk-24](05DataMining-figure/unnamed-chunk-24-1.png)


�į����
====================================
���׬O�G���ɡG

- Sensitivity �ӷP��
- Specificity �S����
- Positive Predictive Value (PPV) ���ʹw����
- Negative Predictive Value (NPV) ���ʹw����


�į���ЦW������
====================================
![plot of chunk unnamed-chunk-25](figures/para.png)
- TP: ���f�B�w���]���f    FP: �S�f���O�w�����f
- TN: �S�f�B�w���]�S�f    FN: ���f���w���S�f

�į���Ф���
====================================
���׬O�G���B��X�]���G���ɡG�į���Ф���
 
- Sensitivity �ӷP�ʡG�Ҧ�`�u�����f`���H�A�Q`�w�����f`�����
- Specificity �S���ʡG�Ҧ�`�u���S�f`���H�A�Q`�w���S�f`�����
- Positive Predictive Value (PPV) ���ʹw���ȡG�Ҧ��Q`�w�����f`���H�A`�u�����f`�����
- Negative Predictive Value (NPV) ���ʹw���ȡG�Ҧ��Q`�w���S�f`���H�A`�u���S�f`�����

�į����
====================================
 �^�Q�@�U��誺���ҵ��G

```r
table(x=DMAns,
    y=PD2[PD2$Test==T,"diabetes"]) 
```

```
     y
x     neg pos
  pos   6  28
  neg  73  23
```
![plot of chunk unnamed-chunk-27](figures/para.png)

�į���� - �w���ഫ
====================================
 �p��w���į�Ѽ�

```r
predictPoint<-
    predict(finalModel_Both,
            PD2[PD2$Test==T,],
            type = "response")
DMAns<-factor(ifelse(predictPoint>0.5,"pos","neg"),
                 levels=c("pos","neg"))
```

�į���� - Sen, Spe
====================================
 �Q��**caret**�M��A�p��w���į�Ѽ�

```r
# install.packages("caret") #�p��Ѽƪ�packages
library(caret)
sensitivity(DMAns,
            PD2[PD2$Test==T,"diabetes"],
            positive="pos")
```

```
[1] 0.5490196
```

```r
specificity(DMAns,
            PD2[PD2$Test==T,"diabetes"],
            negative="neg")
```

```
[1] 0.9240506
```

�į���� - PPV, NPV
====================================
 �p��w���į�Ѽ�

```r
posPredValue(DMAns,
            PD2[PD2$Test==T,"diabetes"],
             positive="pos")
```

```
[1] 0.8235294
```

```r
negPredValue(DMAns,
            PD2[PD2$Test==T,"diabetes"],
             negative="neg")
```

```
[1] 0.7604167
```

�į����
====================================
���׬O�G���A�B�ҫ���X���s���(�p���v)�ɡG

- Area under the ROC curve (AUC)
![plot of chunk unnamed-chunk-31](https://upload.wikimedia.org/wikipedia/commons/6/6b/Roccurves.png)

�į���� - AUC & ROC curve
====================================
 �p��w���į�Ѽ� AUC

```r
# install.packages("pROC")
library(pROC)
# Draw ROC curve.
result.roc <- 
  roc(PD2[PD2$Test==T,"diabetes"], predictPoint) 
# youden or closest.topleft
coords(result.roc, "best", 
       best.method="closest.topleft", 
       ret=c("threshold", "accuracy"))
```

```
threshold  accuracy 
0.2835452 0.8153846 
```

�į���� - AUC & ROC curve
====================================
 �p��w���į�Ѽ� AUC
  �p��w���į�Ѽ� AUC

```r
plot(result.roc, print.thres="best", 
     print.thres.best.method="closest.topleft")
```

![plot of chunk unnamed-chunk-33](05DataMining-figure/unnamed-chunk-33-1.png)

�į���� - AUC & ROC curve
====================================
 �p��w���į�Ѽ� AUC

```r
library(ROCR)
pred=prediction(predictPoint,
                PD2[PD2$Test==T,"diabetes"])
#Calculate the AUC value
perf_AUC=performance(pred,"auc") 
AUC=perf_AUC@y.values[[1]]
#plot the actual ROC curve
perf_ROC=performance(pred,"tpr","fpr") 
plot(perf_ROC, main="ROC plot")
text(0.5,0.5,paste("AUC = ",
                   format(AUC, digits=5, 
                          scientific=FALSE)))
```

![plot of chunk unnamed-chunk-34](05DataMining-figure/unnamed-chunk-34-1.png)

�į���� - AUC & ROC curve
====================================
 With **ggplot** and **pROC**: https://gist.github.com/jwaage/6d8f4eb096e4f18a0894ca1ce27af834

�w���ҫ��إ߻P���Һ�X�m��
====================================
type:alert

- Sonar��ưO���q���P���Y�����U�Ӥ��P���ת��n�i������A�����쪺�^�n�ƭ�
- �@�@��60�ӰѼơA�N��ϥΤ@�S�O���ת��n�i�����q�۩ұo�^�n
- �������G���G�������A�]�A�q�� ( M ) �P���Y ( R ) 
- �N����H�������V�m��(2/3)�P���ղ�(1/3)
- �V�m�ҫ������ҡI

library(mlbench)
data(Sonar) 


caret package
====================================
type:sub-section

http://topepo.github.io/caret/index.html

- data splitting
- pre-processing
- feature selection
- model tuning using resampling
- evaluation
- variable importance estimation

caret: data splitting
====================================
- `createDataPartition`
  - p: �V�m�դ��

```r
library(caret)
set.seed(3456)
trainIndex <- 
  createDataPartition(iris$Species, 
                      p = .8, 
                      list = FALSE, 
                      times = 1)
head(trainIndex)
```

```
     Resample1
[1,]         1
[2,]         2
[3,]         4
[4,]         5
[5,]         6
[6,]         8
```

caret: data splitting
====================================
�ϥ�`createDataPartition`����X���l��

```r
trainData<-iris[trainIndex,]
testData<-iris[-trainIndex,]
nrow(trainData)
```

```
[1] 120
```

```r
nrow(testData)
```

```
[1] 30
```

caret: model tuning using resampling
====================================
`trainControl`�]�w�ҫ��ѼưV�m�k

```r
fitControl <- 
  trainControl(## 10-fold CV
    method = "repeatedcv",
    number = 10,
    ## repeated ten times
    repeats = 10)
```

Cross-validation
====================================
- ���b�@�Ӥl���W�����R�A �Ө䥦�l���h�ΨӰ�����惡���R���T�{������

![plot of chunk unnamed-chunk-38](https://upload.wikimedia.org/wikipedia/commons/1/1c/K-fold_cross_validation_EN.jpg)


caret: model tuning using resampling
====================================
method = "rpart" �M����

```r
set.seed(825)
DTFit1 <- 
  train(Species ~ ., data = trainData, 
        method = "rpart", 
        trControl = fitControl)
```

caret: model tuning using resampling
====================================

```r
DTFit1
```

```
CART 

120 samples
  4 predictor
  3 classes: 'setosa', 'versicolor', 'virginica' 

No pre-processing
Resampling: Cross-Validated (10 fold, repeated 10 times) 
Summary of sample sizes: 108, 108, 108, 108, 108, 108, ... 
Resampling results across tuning parameters:

  cp     Accuracy   Kappa  
  0.000  0.9108333  0.86625
  0.425  0.7950000  0.69250
  0.500  0.3333333  0.00000

Accuracy was used to select the optimal model using the largest value.
The final value used for the model was cp = 0.
```

caret: evaluation
====================================

```r
predict(DTFit1, 
        newdata = testData, 
        type = "prob")
```

```
    setosa versicolor virginica
3        1 0.00000000 0.0000000
7        1 0.00000000 0.0000000
12       1 0.00000000 0.0000000
14       1 0.00000000 0.0000000
21       1 0.00000000 0.0000000
23       1 0.00000000 0.0000000
41       1 0.00000000 0.0000000
44       1 0.00000000 0.0000000
48       1 0.00000000 0.0000000
49       1 0.00000000 0.0000000
54       0 0.88636364 0.1136364
55       0 0.88636364 0.1136364
61       0 0.88636364 0.1136364
64       0 0.88636364 0.1136364
70       0 0.88636364 0.1136364
82       0 0.88636364 0.1136364
91       0 0.88636364 0.1136364
95       0 0.88636364 0.1136364
96       0 0.88636364 0.1136364
100      0 0.88636364 0.1136364
101      0 0.02777778 0.9722222
102      0 0.02777778 0.9722222
109      0 0.02777778 0.9722222
110      0 0.02777778 0.9722222
111      0 0.02777778 0.9722222
125      0 0.02777778 0.9722222
129      0 0.02777778 0.9722222
138      0 0.02777778 0.9722222
147      0 0.02777778 0.9722222
149      0 0.02777778 0.9722222
```

caret: data splitting
====================================
`createDataPartition`

```r
library(caret)
set.seed(3456)
trainIndexBinary <- 
  createDataPartition(PD2$diabetes, 
                      p = .75, 
                      list = FALSE, 
                      times = 1)
head(trainIndexBinary)
```

```
     Resample1
[1,]         1
[2,]         2
[3,]         3
[4,]         4
[5,]         5
[6,]         6
```

caret: data splitting
====================================
`createDataPartition`

```r
trainDataBinary<-PD2[trainIndexBinary,]
testDataBinary<-PD2[-trainIndexBinary,]
```

caret: model tuning using resampling
====================================

```r
fitControlBinary <- 
  trainControl(method = "repeatedcv",
               number = 10,
               repeats = 10,
               ## Estimate class probabilities
               classProbs = TRUE,
               ## Evaluate performance using 
               ## the following function
               summaryFunction = twoClassSummary)
```

caret: model tuning using resampling
====================================

```r
set.seed(825)
DTFitBinary <- 
  train(diabetes ~ ., 
        data = trainDataBinary, 
        method = "rpart", 
        trControl = fitControlBinary,
        ## Specify which metric to optimize
        metric = "ROC")
```

caret: model tuning using resampling
====================================

```r
DTFitBinary
```

```
CART 

295 samples
  9 predictor
  2 classes: 'neg', 'pos' 

No pre-processing
Resampling: Cross-Validated (10 fold, repeated 10 times) 
Summary of sample sizes: 266, 265, 265, 265, 266, 266, ... 
Resampling results across tuning parameters:

  cp          ROC        Sens       Spec     
  0.03809524  0.7664378  0.8431579  0.6636364
  0.11428571  0.7668158  0.8100000  0.6978182
  0.36190476  0.6079545  0.8600000  0.3559091

ROC was used to select the optimal model using the largest value.
The final value used for the model was cp = 0.1142857.
```

caret: evaluation
====================================

```r
pred<-
  predict(DTFitBinary, 
          newdata = testDataBinary, 
          type = "prob")
knitr::kable(head(pred))
```



|   |       neg|       pos|
|:--|---------:|---------:|
|19 | 0.8596491| 0.1403509|
|36 | 0.8596491| 0.1403509|
|40 | 0.8596491| 0.1403509|
|51 | 0.8596491| 0.1403509|
|57 | 0.3467742| 0.6532258|
|69 | 0.8596491| 0.1403509|

�į���ЦW������
====================================
![plot of chunk unnamed-chunk-48](figures/para.png)
- TP: ���f�B�w���]���f    FP: �S�f���O�w�����f
- TN: �S�f�B�w���]�S�f    FN: ���f���w���S�f

caret: evaluation
====================================



```
processing file: 05DataMining.Rpres
Loading required package: lattice
Loading required package: ggplot2
Type 'citation("pROC")' for a citation.

Attaching package: 'pROC'

The following objects are masked from 'package:stats':

    cov, smooth, var

Loading required package: gplots

Attaching package: 'gplots'

The following object is masked from 'package:stats':

    lowess

Quitting from lines 878-882 (05DataMining.Rpres) 
���~: `data` and `reference` should be factors with the same levels.
�������
```
