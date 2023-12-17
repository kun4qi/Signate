## exp50とexp65はyujiさんのexp番号に対応



### exp050
#### 1段階目  
純粋な予測モデル(30+10個)

#### 2段階目
| method | CV | LB | filename |
| - | - | - | - |
| Nelder-Meld | 43.57204422204847 | 43.2521041 | kun4qi exp55 |
| stacking_lgb | 43.60 |  | kun4qi exp56 |
| Hill Climbing | 43.56925636218776 | 43.2500502 | Yuji.K exp051 |
| Simple Greedy1 | 43.56925636218776 | 43.2432630 | Yuji.K exp052 |
| Simple Greedy2 | 43.56925636218776 | 43.2406218 | Yuji.K exp053 |
| Simple Greedy3 | 43.56925636218776 | 43.2620733 | Yuji.K exp054 |

#### 3段階目
| method | CV | LB | filename |
| - | - | - | - |
| Nelder-Meld | 43.496076310831896 | 43.1864741 | kun4qi exp61 |
| stacking_lgb | 43.54 |  | kun4qi exp62 |
| Optuna | 43.501541457142345 |  | Yuji.K exp072 | 
| Hill Climbing | 43.500996476403245 | 43.1851463 | Yuji.K exp073 |
| Simple Greedy1 | 43.49803242660311 | 43.1838002 | Yuji.K exp074 |
| Simple Greedy2 | 43.49799517555315 | 43.1832022 | Yuji.K exp075 |
| Simple Greedy3 | 43.49790678952483 | 43.1836722 | Yuji.K exp076 |


#### 4段目
| method | CV | LB | filename | 
| - | - | - | - |
| Nelder-Meld | 43.47638114611345 | | kun4qi exp65 |
| stacking_lgb |  43.55|  | kun4qi exp66 |
| Optuna | 43.47844292303129 |  | exp083 |
| Hill Climbing | 43.47778313918253 | |  exp084 |
| Simple Greedy1 | 43.47776380559784 | 43.1874960	 | exp085 |
| Simple Greedy2 | 43.477767793581286 |  | exp086 |
| Simple Greedy3 | 43.477758376378624 | 43.1874610 | exp087 |


### exp065
#### 1段階目  
純粋な予測モデル(40+10個)

#### 2段階目
| method | CV | LB | filename |
| - | - | - | - |
| Nelder-Meld | 43.56340118610674 | | kun4qi exp60 |
| stacking_lgb | 43.61044144258124 |  | Yuji.K exp077 |
| Hill Climbing | 43.56453307604806 | | Yuji.K exp066 |
| Simple Greedy1 | 43.58216667876671 | | Yuji.K exp067 |
| Simple Greedy2 | 43.583016983994256 | | Yuji.K exp068 |
| Simple Greedy3 | 43.58368909587582 | | Yuji.K exp069 |
| Simple Greedy4 | 43.5824156325436 | | Yuji.K exp070 |
| Simple Greedy5 | 43.582951599388245 | | Yuji.K exp071 |

#### 3段階目
| method | CV | LB | filename |
| - | - | - | - |
| Nelder-Meld | 43.50759512964418 | | kun4qi exp63|
| stacking_lgb | 43.52|  | kun4qi exp64|
| Optuna | 43.525503530105766 |  | Yuji.exp082 | 
| Hill Climbing | 43.512610839373686 |  | Yuji.K exp081 |
| Simple Greedy1 | 43.512634988062615 |  | Yuji.K exp078 |
| Simple Greedy2 | 43.511237476304665 |  | Yuji.K exp079 |
| Simple Greedy3 | 43.51222899019721 |  | Yuji.K exp080 |




## やったこと
### cv統一前
| 実験名       | コメント                                                                                                                         | cv       |       lb |
|:-------------|:---------------------------------------------------------------------------------------------------------------------------------|:---------|---------:|
| exp1         | ベースライン                                                                                                               | 65.78    |   64.34  |
| exp2         | カテゴリ毎スコアをそれぞれについて計算                                                                                           | 64.8227  |       |
| exp3         | target encordigにしたけど、exp2の話が使えなくなって結局スコアは変わらず                                                          | 64.8355  |       |
| exp4         | データをきれいにした、exp3から派生                                                                                               |       |       |
| exp5         | データをきれいにした、exp２から派生                                                                                              |       |       |
| exp6         | MAPEの最適化→priceにlogをとるとMAPE仕様になるらしい？https://static.signate.jp/competitions/162/summaries/1st_place_solution.pdf | 52.8863  |   51.64  |
| exp7         | exp6の損失をrsmeにした、データきれいにしたのが反映できてなかったからここからがexp4の恩恵を受けてる                               | 52.8528  |       |
| exp8         | 位置情報追加したけどあんまり変わんなかった                                                                                       | 52.8329  |       |
| exp9        | slackの強いベースライン、そのまま                                                                                                | 0.4432   |   43.74  |
| exp10        | なにしたか書いてなくて忘れました。。                                                                                             |       |       |
| exp11        | logにするにはなしで、いったんoptuna経由のlgbにした、_avg_priceも追加した                                                         | 0.4473   |       |
| exp12        | exp10に戻してoptunaのlgbm→exp11とほぼ変わらないかもです。                                                                        | 0.4457   |   43.862 |
| exp13        | exp6を参考にpriceをlogにしたけど、良くならなかった                                                                               |  |       |
| exp14        | optunaのlgbmじゃなくて、用意してくれてるやつで実装                                                                               |       |       |
| exp15        | いろいろ特徴量追加                                                                                                               | 0.443    |   43.63  |
| exp16        | odometerの-1をnp.nanにした、onehotencoderに変更                                                                                  | 0.4427   |   43.64  |
| exp17        | binにしたやつを追加                                                                                                              | 0.4418   |   43.65  |
| exp18        | odometerのやつでさらに追加                                                                                                       | 0.4424   | 4364     |
| exp19        | target encordingのときにのリークをなくした                                                                                       | 0.4417   |   43.603 |
| exp20        | リーク直して、exp17                                                                                                              | 0.4417   |   43.643 |
| exp21        | year_odometer_ratio追加                                                                                                          | 0.442    |   43.63  |
| exp22        | foldの数を10にしてみた、exp19の派生                                                                                              | 0.4417   |   43.617 |
| exp23        | https://www.kaggle.com/code/senkin13/han-20200904 foldの仕方をメーカーごとのstratifiedにした、上のURLのコンペと今回のデータが似ていた、craigslist.orgからデータをとってきてるかも                                                                         | 0.4439   |   43.57  |
| exp24        | exp23に特徴量追加、追加したやつあんまり使えなさそうだったからほぼ消した状態、cvは消す前の奴                                      | 0.4434   |   44.32  |
| exp25        | exp24の特徴量減らしたやつに、基準の値段とかのを追加(exp23のurlのところを参考)、ただしリークしてる                                | 0.443    |   43.66  |
| exp26        | exp25のリークなおした                                                                                                            | 0.4438   |   43.62  |
| exp27        | exp26からstdのターゲットエンコーディングをとった                                                                                 | 0.4437   |   43.644 |
| exp28        | exp27ではstratifiedから普通のkfold元に戻した                                                                                     | 0.4431   |   43.649 |
| nan          | exo28から列をimportanceで絞った                                                                                                  | 0.4443   |       |
| exp29        | resionとってみたexp23                                                                                                            | 0.4428   |   43.69  |
| exp30        | resionとってみたexp19                                                                                                            | 0.4414   |   43.64  |
| exp31        | exp29にyujiさんのをいくつか追加、エラー出て実行できてない                                                                       |       |       |
| exp32        | exp３０のリークとろうとしたけど、まだほかにリークが残ってたからLBは図れてない、exp34に完全にとったやつを実装                                                                                                       | 0.4427   |     |



### cv統一後
| 実験名       | コメント                                         |   cv |   lb |
|:-------------|:-------------------------------------------------|-----:|-----:|
| exp33        | cv合わせたやつにした 、exp32の派生                                                                                                            | 0.4421    |   43.628|
| exp34        | コード整理した、リーク完全にとった             |  0.4426 |  43.61 |
| exp35        | ・経度×緯度の特徴量生成  経度と緯度を組み合わせて座標点とした これに対してカウントエンコーディング  ・経度、緯度をkmeansでクラスタリング クラスタ数は試行を繰り返して最終的に15クラスタに                      |  0.4425 |   
| exp36        | 特徴量選択のやつで特徴量を減らしていこうと思ったけど、上手くいかなくて挫折                      |   |   
| exp37        | exp35のoptunaのパラメータを変更、foldは5    | 0.4422      |       |



### cv統一後　かつ　fold数8
| 実験名       | コメント                                         |   cv |   lb |
|:-------------|:-------------------------------------------------|-----:|-----:|
| exp38        | exp34のfold数8                                                                   | 0.4403      |  43.475     |
| exp39        | exp35のfold数8                                                                   | 0.4414      |   43.50    |
| exp40        | exp38でoptunaのバリエーション増やした、悪化した                                                                   | 0.4415      |       |
| exp41        | exp38のseed値変更(3053)                                                                   | 0.4404      |       |
| exp42        | exp38のseed値変更(673)                                                                   | 0.4406      |       |
| exp43        | exp38のseed値変更(952)                                                                   | 0.4411      |       |
| exp44        | exp38で最頻値で欠損値を補完                                                                  | 0.4408      |       |
| exp45        | yujiさんのexp25のスタッキングversion、kunaiのexp38-40、yujiのexp14-23                                                                  |  0.4398     |       |
| exp46        | 2変数ターゲットエンコーディング、odometerとcar_age_binをワンホットしてたけど、取った                                                                  |   0.4402    |       |
| exp47        | 2変数ターゲットエンコーディング、odometerのbinのやつを追加                                                                  |   0.4407    |       |
| exp48        | 2変数ターゲットエンコーディング、yujiさんの特徴量をお借りしました                                                                 |   0.4400    |       |
| exp49        | ワンホットエンコーディングの次元圧縮、exp48からの派生|   0.4402   |       |
| exp50        | ワンホットエンコーディングの次元圧縮、regionも加えてやりたい、|   0.4416   |       |
| exp51        | ワンホットエンコーディングの次元圧縮、regionも加えてやりたい、次元数を5から10にした|   0.4403   |       |
| exp52        | exp38-48の集約|      |       |
| exp53        | yujiさんのexp14からのと、自分のexp38-48のスタッキング|    0.4380  |       |
| exp54        | yujiさんのexp14からのと、自分のexp38-48のアンサンブル|    0.4368  |       |
| exp55        | yujiさんのexp14からのと、自分のexp38-48のNelder-Mead method(exp50の二段目)|   43.572    |    43.252   |
| exp56        | yujiさんのexp14からのと、自分のexp38-48のスタッキングをnnじゃなくてlgbmでやってみたい(exp50の二段目)|    0.4360   |       |
| exp57        | yujiさんのexp14からのと、自分のexp38-48のスタッキングをp乗してからHill Climbing|    だめだった   |       |
| exp58        | yujiさんのexp14からのと、自分のexp38-48のスタッキングをp乗してからNelder-Mead method|   だめだった    |       |
| exp59        | 異なる手法でアンサンブルしたのをさらにWeighted Average？(cvが43.60以下のやつ)、俺のexp55,56|   43.5009    |   43.183    |
| exp60        | yujiさんのexp14からのと+yujimodelさんの追加のmodel10個、自分のexp38-48のNelder-Mead method(exp65の二段目)|   43.563    |     |
| exp61        | 異なる手法でアンサンブルしたのをさらにNelder-Mead method？(cvが43.60以下のやつ)、俺のexp55,56とyujiさんのexp51-54(exp50の三段目|    43.496   |       |
| exp62        | 異なる手法でアンサンブルしたのをさらにstacking-lgb、俺のexp55,56とyujiさんのexp51-54(exp50の三段目)|   0.4354    |       |
| exp63        | 異なる手法でアンサンブルしたのをさらにNelder-Mead、俺のexp55,56とyujiさんのexp51-54(exp65の三段目)|   43.50759512964418    |       |
| exp64        | 異なる手法でアンサンブルしたのをさらにstacking-lgb、俺のexp55,56とyujiさんのexp51-54(exp65の三段目)|    43.52   |       |
| exp65        | 異なる手法でアンサンブルしたのをさらにNelder-Mead、exp50シリーズの4段目|   43.47638114611345    |       |
| exp66        | 異なる手法でアンサンブルしたのをさらにstacking-lgb、exp50シリーズの4段目|       |       |
| exp67        | exp50で１段目と２段目のすべてでNelder-Mead|    43.46088582832526   |    43.2463   |
