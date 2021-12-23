# Introduction
This is an assignment from a mechine learning course provided by Hongyi Lee: <br><br>
There are 11 categories： Bread, Dairy Product, Dessert, Egg, Fried Food, Meat, Noodles/Pasta, Rice, Seadfood, Soup and Vegetable/Fruit. Each category is represented by a number. For example, 0 stands for Bread.<br><br>
Training set has 9866 photos; Validation set has 3430 photos; Testing set has 3347 photos.<br><br>

**Examples of some photos in training set:** <br>
The first digit stands for the category, the second one stands for its id.<br><br>
<img width="550" alt="image" src="https://user-images.githubusercontent.com/55254825/147184185-d8e7dd07-0583-4062-80d5-b562a253ce88.png"><br>

**Examples of some photos in testing set:** <br><br>
Digits stand for id of each photos.<br><br>
<img width="558" alt="image" src="https://user-images.githubusercontent.com/55254825/147184318-6fceb220-f25d-4aac-8a68-22b852af46da.png">


# How to run it

openCV2, pytorch needed. <br><br>
Recommend gpu(cuda) and run on Colab. 

**Every time I run it on Colab takes more than 20 mins**

# Discussion

### First Version

Details of first version shows in `main_version1.ipynb`<br>

**Parameters**

| Epoch   |      Optimizer      |  Learning Rate | CNN Layer |
|----------|:-------------:|:-------------:|------:|
| 30 |  Adam | 0.001 | 5


**Accurancy on training set & validation set**

```
[001/030] 66.58 sec(s) Train Acc: 0.352220 Loss: 0.014658 | Val Acc: 0.304956 loss: 0.017854
[002/030] 67.79 sec(s) Train Acc: 0.489357 Loss: 0.011786 | Val Acc: 0.436443 loss: 0.012535
[003/030] 68.20 sec(s) Train Acc: 0.574296 Loss: 0.009729 | Val Acc: 0.474052 loss: 0.012776
[004/030] 68.26 sec(s) Train Acc: 0.628826 Loss: 0.008495 | Val Acc: 0.495627 loss: 0.012022
[005/030] 67.89 sec(s) Train Acc: 0.680215 Loss: 0.007383 | Val Acc: 0.514286 loss: 0.012092
[006/030] 67.82 sec(s) Train Acc: 0.716805 Loss: 0.006481 | Val Acc: 0.523032 loss: 0.011752
[007/030] 67.76 sec(s) Train Acc: 0.779850 Loss: 0.005155 | Val Acc: 0.440525 loss: 0.019107
[008/030] 67.77 sec(s) Train Acc: 0.818772 Loss: 0.004374 | Val Acc: 0.544315 loss: 0.012200
[009/030] 67.82 sec(s) Train Acc: 0.902595 Loss: 0.002618 | Val Acc: 0.581633 loss: 0.011239
[010/030] 67.80 sec(s) Train Acc: 0.907764 Loss: 0.002408 | Val Acc: 0.610496 loss: 0.010349
[011/030] 67.83 sec(s) Train Acc: 0.978208 Loss: 0.000840 | Val Acc: 0.586297 loss: 0.012150
[012/030] 67.83 sec(s) Train Acc: 0.994729 Loss: 0.000375 | Val Acc: 0.621283 loss: 0.011448
[013/030] 67.83 sec(s) Train Acc: 0.999189 Loss: 0.000142 | Val Acc: 0.650729 loss: 0.010762
[014/030] 67.83 sec(s) Train Acc: 0.999899 Loss: 0.000072 | Val Acc: 0.653353 loss: 0.010538
[015/030] 67.73 sec(s) Train Acc: 1.000000 Loss: 0.000043 | Val Acc: 0.662974 loss: 0.010663
[016/030] 67.54 sec(s) Train Acc: 0.999797 Loss: 0.000042 | Val Acc: 0.657726 loss: 0.011135
[017/030] 68.04 sec(s) Train Acc: 1.000000 Loss: 0.000029 | Val Acc: 0.641108 loss: 0.011591
[018/030] 67.90 sec(s) Train Acc: 0.947496 Loss: 0.001220 | Val Acc: 0.325364 loss: 0.035857
[019/030] 67.85 sec(s) Train Acc: 0.895601 Loss: 0.002510 | Val Acc: 0.532945 loss: 0.015924
[020/030] 67.77 sec(s) Train Acc: 0.991891 Loss: 0.000337 | Val Acc: 0.626531 loss: 0.012153
[021/030] 67.14 sec(s) Train Acc: 0.998986 Loss: 0.000094 | Val Acc: 0.650729 loss: 0.011577
[022/030] 67.15 sec(s) Train Acc: 1.000000 Loss: 0.000025 | Val Acc: 0.651895 loss: 0.011703
[023/030] 67.06 sec(s) Train Acc: 1.000000 Loss: 0.000018 | Val Acc: 0.652770 loss: 0.011770
[024/030] 67.09 sec(s) Train Acc: 1.000000 Loss: 0.000012 | Val Acc: 0.654227 loss: 0.011894
[025/030] 67.07 sec(s) Train Acc: 1.000000 Loss: 0.000010 | Val Acc: 0.655977 loss: 0.011955
[026/030] 67.07 sec(s) Train Acc: 1.000000 Loss: 0.000009 | Val Acc: 0.654227 loss: 0.011962
[027/030] 67.09 sec(s) Train Acc: 1.000000 Loss: 0.000008 | Val Acc: 0.657726 loss: 0.012085
[028/030] 67.17 sec(s) Train Acc: 1.000000 Loss: 0.000007 | Val Acc: 0.650729 loss: 0.012253
[029/030] 67.03 sec(s) Train Acc: 1.000000 Loss: 0.000006 | Val Acc: 0.656268 loss: 0.012184
[030/030] 67.06 sec(s) Train Acc: 1.000000 Loss: 0.000006 | Val Acc: 0.648980 loss: 0.012438
```

The accurancy on training set demonstrates the overfitting problem, therefore, I try to eliminate the number of layers of CNN.

### Second Version

Details of first version shows in `main_version2.ipynb`<br>

**Parameters**

| Epoch   |      Optimizer      |  Learning Rate | CNN Layer |
|----------|:-------------:|:-------------:|------:|
| 30 |  Adam | 0.001 | 3

**Accurancy on training set & validation set**
```
1 30 37.67370271682739  0.3331644030002027  0.015129434876332728
2 30 37.88792681694031  0.4497263328603284  0.012505259012175505
3 30 38.01456022262573  0.5240218933711738  0.011051910923529222
4 30 37.98996138572693  0.5691262923170485  0.00985581438536096
5 30 38.00493907928467  0.627609973646868   0.008618135934859097
6 30 37.99918651580810  0.686195013176566   0.007473834830125012
7 30 38.03762173652649  0.7178187715386175  0.006692791339134604
8 30 37.98207449913025  0.7878572876545713  0.005423812348582115
9 30 37.971869707107544 0.8116764646259882  0.004766141428271776
10 30 38.02905488014221 0.8653963105615244  0.0037024831514486114
11 30 38.06076455116272 0.8976282181228461  0.002989106908812137
12 30 38.18526339530945 0.9448611392661667  0.0021030235587765184
13 30 38.17484641075134 0.9339144536793027  0.0021383255303280605
14 30 38.01467537879944 0.9525643624569228  0.0017046179488745322
15 30 38.0549213886261  0.9803365092235962  0.0010347942208666216
16 30 38.14662098884582 0.9892560308128928  0.0007845818080399212
17 30 38.19715356826782 0.9952361646057166  0.0005767623771766656
18 30 38.08037400245666 0.9875329414149605  0.0006729926364207495
19 30 38.07085943222046 0.9965538212041354  0.00041570035884594446
20 30 38.18836951255798 0.9990877762010947  0.0002428372842730747
21 30 38.20771718025207 0.9975674032029191  0.0002823567454783012
22 30 38.00709891319275 0.9997972836002432  0.00016656942203408342
23 30 37.99919581413269 1.0                 0.00012365268307747257
24 30 38.09369802474975 1.0                 0.00011138154964795128
25 30 38.09435153007507 1.0                 0.0001228893619954296
26 30 38.19451379776001 0.9969592540036489  0.00021613575518131256
27 30 38.06573939323425 1.0                 6.537853747518676e-05
28 30 38.01408100128174 1.0                 5.66065469971948e-05
29 30 38.03998279571533 1.0                 4.968661396276563e-05
30 30 38.05332970619202 0.999189134400973   0.00012011803619030424
```

Still got the overfitting problem, this time I try to transform the image.<br>

### Third Version

Details of third version shows in `main_version3.ipynb`<br>

**Parameters**

| Epoch   |      Optimizer      |  Learning Rate | CNN Layer |Image Transform
|----------|:-------------:|:-------------:|:--------:|------------:|
| 30 |  Adam | 0.001 | 3 | Yes


**Accurancy on training set & validation set**
```
1 30  43.316243410110474 0.3007297790391243 0.01574632460800842
2 30  43.09182024002075  0.411007500506791  0.013430775275173376
3 30  43.13574838638306  0.4691871072369755 0.012170958381237568
4 30  43.10466504096985  0.4962497466045003 0.011470776976375243
5 30  43.09687924385071  0.5269612811676465 0.010743892811481933
6 30  43.092318534851074 0.5552402189337118 0.010170827911418712
7 30  43.16780209541321  0.5783498885059801 0.009753331206716294
8 30  43.097652435302734 0.595276707885668  0.009294017983236879
9 30  43.15468454360962  0.6122035272653558 0.008805817676175325
10 30 43.10450267791748  0.6271031826474762 0.008533040233395923
11 30 43.17072582244873  0.6378471518345834 0.00828840155981386
12 30 43.132317781448364 0.6626799108047841 0.007790329373924384
13 30 43.13890290260315  0.6803162375836205 0.007421993862512071
14 30 43.22617030143738  0.6892357591729171 0.007162672545879433
15 30 43.24321413040161  0.7013987431583215 0.006879977702176187
16 30 43.037864208221436 0.7131562943442125 0.006645079216559808
17 30 42.89113664627075  0.7280559497263328 0.0062569076829330685
18 30 42.898669481277466 0.7463004257044394 0.006059703262877372
19 30 42.95213055610657  0.7331238597202514 0.006180546128094958
20 30 42.80718755722046  0.7414352321102777 0.005880474101789046
21 30 42.90970063209534  0.763125886884249  0.0054051099957159315
22 30 42.90547704696655  0.782586661260896  0.005152849255844471
23 30 42.83624267578125  0.7808635718629637 0.005180133913318743
24 30 42.742735862731934 0.7950537198459355 0.004778119907789
25 30 42.74918508529663  0.8113723900263531 0.0044253207735616105
26 30 42.76734709739685  0.8242448814109061 0.004248912025000632
27 30 42.75151968002319  0.8281978512061626 0.0041061383689994044
28 30 42.7867374420166   0.8325562538009325 0.004006561285314129
29 30 42.77878952026367  0.8425907155888911 0.0038066209601070344
30 30 42.78259897232056  0.8509020879789175 0.003616110457021712
```

With image transform, I solve the overfitting problem. Also, the accurancy on training set is 0.8509020879789175, and the accurancy on validation set is 0.003616110457021712.


The accurancy on validation set is still low. 

### Fouth Version
Needed to complete.

