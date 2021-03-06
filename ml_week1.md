# Week1授業前課題1 Pythonを使ってみよう（機械学習コースワークサンプル用）

⚠授業前日までに提出してください。

⚠課題を完了させることは、DIVE INTO CODEを卒業するための必須条件です。

⚠課題では、テキストにも含まれていない新しい知識が含まれています。これは自分で調べて新しいことを把握する力を身に着けてほしいからです。

`課題`を一人で遂行できる力を身につけることで、きちんとした現場に通用する能力を身につけることができます。それでは頑張っていきましょう！

------------
## この課題の目的

- 基礎的なプログラミング方法を確認する。
- 調べながら進める習慣をつける。

------------

`以下の要件をすべて満たしていた場合、合格とします。`

`※Jupyter Notebookを使い課題に沿った検証や説明ができている。`

## 課題

紙を折り続けると厚さが増していき、43回で月に届くという話があります。しかし、実際には10回も折ることができません。また、手計算も大変です。

そこで今回の課題では`1枚の紙を43回折り曲げた時の厚さを計算するプログラム`を作成します。

43回折った紙の厚さ $t_{43}$ は、折る前の紙の厚さ $t_{0}$ を使い以下の数式で求まります。


$$
t_{43} = t_{0}×2^{43}
$$

折る前の紙の厚さ $t_{0}$ は**0.00008m**とします。一般的なコピー用紙の厚さです。

### 今回確認するPythonのスキル

- 基本的な計算
- for文の活用法
- 時間を測る
- 配列（list）の使い方
- 簡単なグラフの表示

## 2つの方法

プログラミングでは同じ動作を様々な方法で記述することができます。今回は以下の2つを作成してもらいます。

- べき乗の算術演算子を使用
- for文を使用

### べき乗の算術演算子を使用

`コーディング`

算術演算子を使用したプログラムを作ってください。  
雛形として紙を1回折った時の厚さを計算するコードを用意しました。これを43回折った時のコードに書き換えてください。

`雛形`

```py
"""
紙を1回折った時の厚さを計算するコード
"""

thickness = 0.00008

folded_thickness = thickness*2

print("厚さ： {}メートル".format(folded_thickness))
```

`ヒント`

「算術演算子」

Pythonで`+`、`-`、`×`、`÷`の四則演算は次のような算術演算子を使い書くことができます。

$2+43$ : `2+43`

$2-43$ : `2-43`

$2×43$ : `2*43`

$2÷43$ : `2/43`

ここではべき乗の計算 $2^{43}$ が行いたいですが、どのような記号（算術演算子）で計算ができるか調査して使用してください。「Python べき乗」のように検索しましょう。

### 単位の変換

`コーディング`

単位がメートルだと実感が湧きづらいので、`◯◯万キロメートル`に変換して表示させてみます。

サンプルとして`◯◯キロメートル`に変換したコードを用意したので、参考にしてください。小数点以下は2桁まで表示されるようにも指定しています。

`サンプルコード`

```py
# メートルをキロメートルに変換して小数点以下2桁で表示する
print("厚さ： {:.2f}キロメートル".format(folded_thickness/1000))
```

「月までの距離」を検索して、折った紙が月に届くかどうか確認してみましょう。

### for文を使用

`コーディング`

次に、for文を使用したプログラムを作ってください。

べき乗の算術演算子は使ってはいけません。四則演算の算術演算子のみが使用可能です。

`ヒント`

「べき乗」

べき乗は以下のように掛け算の繰り返しに置き換えることができます。

$2^3=2×2×2$ 、 $2^5=2×2×2×2×2$

### 計算時間の比較

`コーディング`

2つの方法はどちらが正しいわけでもありませんが、コードの良さを評価する際には以下のような着目点があります。

- 計算速度
- メモリの使用量
- 可読性
- 拡張性
- 再利用性

今回はひとつ目の計算速度を比較してみます。以下の雛形を使用して、2つの方法の計算時間を出力してください。

`雛形`

```py
import time
start = time.time()
#####
# ここに上で書いたコードを貼り付ける
#####
elapsed_time = time.time() - start
print("time : {}[s]".format(elapsed_time))
```

`説明`

それぞれの計算時間の関係を簡単に説明してください。どちらの書き方が良さそうでしょうか。

## 可視化

折り曲げた時の厚さを毎回記録しておき、それを折れ線グラフで可視化してみます。

数式を一般化し、n回折った紙の厚さ $t_{n}$ は以下のように表せます。

$$
t_{n} = t_{0}×2^{n}
$$

この式は`指数関数`になります。指数関数は値が急激に増加する性質があります。厚さが増えて月に到達する様子をグラフで見てみましょう。

### 配列への保存

`コーディング`

ここまでは43回折った後の最後の値だけを使用していました。グラフを表示させるためには折る前の0回から、43回までの合計44個の値を記録しておく必要があります。

for文を使用したコードに、配列（list型変数）へ記録するコードを加えてください。

`ヒント`

1. 空の配列（list型変数）を作成する。
2. 折る前の値を配列に追加する。
3. for文の中でn回折った時の値を配列に追加していく。

配列の扱い方が分からない場合は「Python 配列 作成」「Python 配列 追加」のように検索してみましょう。

最終的に配列に44個の値が格納されていれば正解です。配列の値の数は`len関数`で確認できます。

```py
"""
配列の要素数を確認する例
"""
numbers = [1, 1, 2, 3, 5]
n_numbers = len(numbers)
print("配列の要素数 : {}".format(n_numbers))
```

### 折れ線グラフの表示

`コーディング`

グラフの描画には`Matplotlib`というライブラリを用います。

配列へ記録するコードの後ろで以下の雛形を使用してください。


`雛形`

```py
"""
グラフを表示する。タイトルと軸ラベル名付き。
"""
import matplotlib.pyplot as plt
%matplotlib inline

plt.title("thickness of folded paper")
plt.xlabel("number of folds")
plt.ylabel("thickness[m]")
plt.plot(配列名) # 「配列名」のところにlist型変数を入れる
```

### グラフの考察

`説明`

グラフを表示させた場合はそれに対する考察が重要です。厚さがどのように変化しているかを簡単に説明してください。

---

⚠以下のオプション課題は任意回答です。時間に余裕のある方は取り組んでください。

### （オプション課題）グラフのカスタマイズ

`コーディング`

グラフをカスタマイズしてみましょう。カスタマイズしたグラフを最低3種類作成してください。

例えば以下のように書き換えることで、線の色を赤に変更できます。

`サンプルコード`

```py
"""
赤い折れ線グラフを表示する。
"""
plt.title("thickness of folded paper")
plt.xlabel("number of folds")
plt.ylabel("thickness[m]")
plt.plot(配列名, color='red')
```

どのようなことができるかはMatplotlibの公式ドキュメントを参考にします。

[matplotlib.pyplot.plot — Matplotlib 3.0.2 documentation](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.plot.html)

（カスタマイズ例）

- 線の色を青と赤以外にする。
- 線を太くする。
- 線を点線にする。
- 値のフォントサイズを変更する。

上記のページに載っていないカスタマイズも可能です。

`サンプルコード`

```py
"""
軸の値を大きく表示する。
"""
plt.title("thickness of folded paper")
plt.xlabel("number of folds")
plt.ylabel("thickness[m]")
plt.tick_params(labelsize=20) # 軸の値に関する設定を行う
plt.plot(配列名)
```

この`plt.tick_params()`に関しては以下のページで説明されています。

[matplotlib.pyplot.tick_params — Matplotlib 2.1.1 documentation](https://matplotlib.org/2.1.1/api/_as_gen/matplotlib.pyplot.tick_params.html)

様々なカスタマイズ方法を調べて見やすいグラフを作成してみましょう。

## （オプション課題）Pythonが使われる理由

今回の例は他のプログラミング言語（C言語、Java、Rなど）や、Excel、電卓でも計算できるものでした。しかし、機械学習分野ではPythonが広く使われています。学びはじめる前に、何故Pythonを使うのかを確認しておきましょう。

`説明`

機械学習の分野ではPythonが使われる理由を調査して説明してください。

（検索例）

「Python 機械学習 なぜ」「Python vs R」
