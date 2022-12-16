# GMM-WBIC_with_PyMC
### PyMC source program to determine the number of clusters in multi-dimensional data by WBIC.

PythonでGaussian Mixture Model(GMM)のWBICを計算するプログラムをPyMCと呼ばれるベイズ推定用のライブラリを用いて実装しました。
用途としては、多次元データの潜在的なクラスタ数の決定などに使用できます。

逆温度つきのGMMの尤度関数をtheanoを使って自前で設計しています。<br>
多次元かつ潜在的に複数のクラスターを持つようなデータに対応しており、テンソルとしてデータを投げればどんなデータでもGMMのWBICが計算できます。<br>

使用したライブラリは以下のとおりです。

・pymc3 <br>
・theano

計算の流れ
Step1 ) GMMの逆温度付き尤度関数を用いたベイズ事後分布からのパラメータをMCMCで生成する。
Step2 ) Step1で生成したパラメータを用いて、通常のGMMの尤度関数(逆温度=1)の期待値(=WBIC)を求める。

