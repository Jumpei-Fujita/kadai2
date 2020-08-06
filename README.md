# 課題２

## データセットの作成

### 1.priceの標準化
priceを扱いやすい大きさにするため全てのデータをその中の最大値で割ることで0~1の間に丸めた。
### 2.入力データの標準化
入力ベクトルからそれぞれの次元の平均を引き、標準偏差で割ることで平均０、分散１に落とし込み、のちに作成するニューラルネットで扱いやすい形にする。
### 3.データの分割
今回はscikit-learnを用いて訓練データ、検証用データ、テスト用データをそれぞれ6:2:2に分割する

## モデル構築
![model](https://github.com/Jumpei-Fujita/kadai2/blob/master/dentsu_neuralnet.png)
今回はニューラルネットワークにより学習をこなうことで回帰を行った。
ニューロン数は上の画像の通りである。
出力と訓練データのラベルのMSEを最小にするように学習パラメータの更新を行った。
最適化手法はSGDを選択し、ハイパーパラメータとしてlearning rate、weight decayの設定を訓練データ、検証用データの評価を考慮して行った。

## テスト結果
### 1.テスト用データに対するMAE, RMSE, MER(平均誤差率)
|learning rate|weight decay|MAE|RMSE|MER|R2スコア|
|:--|:--|:--|:--|:--|:--|
|0.1|10^(-8)|135447.69|241691.66|24%|0.6078636|


