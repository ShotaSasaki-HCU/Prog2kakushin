# 【プログラム１について】Pandasによる2020年4月1日〜2022年3月11日のNetflix視聴ランキング分析アプリ
## アプリの概要
　本アプリは、当該期間の各日付におけるNetflix視聴ランキングトップ１０についてのデータが記載されたCSVファイルを読み込み、それらに基づいて分析を行うアプリです。データの処理には、主にPandasライブラリを用いています。

## アプリの用途
　本アプリは、Netflixの長期的な視聴動向を分析することができます。個人がNetflix作品の選択を行う際や、コンテンツの製作者が人気な作品の共通点を研究する際に役立つ知見を引き出すことができます。

## 分析内容について（出力について）
　本アプリで得られる分析結果は以下の通りです。
### 1. トップ１０入り合計日数ランキング
　この機能では、当該期間について各作品が合計何日間ランクインしたかを、降順のランキング形式でユーザに表示する機能です。ユーザは、表示件数の指定を求められます。ユーザが、表示件数を入力するとランキングが表示されます。

### 2. 最大連続トップ１０入り日数ランキング
　この機能では、各作品が当該期間中に最大で何日連続ランクインしたかを、降順のランキング形式でユーザに表示する機能です。ユーザは、表示件数の指定を求められます。ユーザが、表示件数を入力するとランキングが表示されます。

### 3. 「Netflix上でのリリース日からの年数」と「トップ１０タイトル中の順位」の関係
　この機能では、記録されている全てのランキングについて、「Netflix上でのリリース日からの年数」と「トップ１０タイトル中の順位」の関係を散布図として表示します。

### 4. ランキング枠に対するNetflix独占配信の割合
　この機能では、記録されている全てのランキングの内、Netflix独占配信の割合・非独占配信の割合を円グラフで表示します。

## 使い方（入力について）
　Google Colaboratory上で本アプリを実行すると、各種ライブラリのインポート処理が表示されてクリアされた後、以下の様な表示に切り替わります。

<img src="https://github.com/ShotaSasaki-HCU/Prog2kakushin/blob/main/Attached%20File/work1_main_menu.png?raw=true" width="50%">

　ユーザが選択肢に一致する数字を入力した場合、一度表示がクリアされて新たな表示に遷移した後、各機能が実行されます。ユーザが選択肢以外の数字を入力した場合、その旨を伝えるエラー文が表示され、再度入力を求められます。各機能の実行が終わった後にエンターキーを押下すると、再びこの表示へ戻ってくることができます。選択肢の内、「5. 終了」が選択されると本アプリは終了します。

## 分析に使用したCSVファイルについて
　本アプリのデータ分析に使用した`netflix daily top 10.csv`は、下記のURLより入手しました。Licenseは、CC0: Public Domainに指定されており、本アプリで使用することに問題は生じません。

<https://www.kaggle.com/datasets/prasertk/netflix-daily-top-10-in-us>

---
# 【プログラム２について】リニアフェーズドアレイ方式による平面波送信シミュレーター
## アプリの概要
　本アプリは、リニアフェーズドアレイ方式での平面波の振る舞いをシミュレートするものです。そもそもリニアフェーズドアレイ方式とは、一直線上に任意の間隔で送信素子（波源）を並べ、それぞれの送信する波の位相（タイミング）をずらすことで、特定の方向や位置に強い波を集中させることができる手法の事です。

　特定の方向に指向性のある波を形成する事は、ビームフォーミング（Beam Forming）と呼ばれます。フェーズドアレイによるビームフォーミングでは、意図する方向に形成されるメインローブと呼ばれる最も強いビームと、意図しない方向に形成されるサイドローブと呼ばれる有害なビームの両方が形成されます。また、ビームフォーミングで形成したビームの方向を時間的に変化させることは、ビームステアリング（Beam Steering）と呼ばれます。

　一方、特定の位置に指向性のある波を形成する事は、ビームフォーカシング（Beam Focusing）と呼ばれます。任意の位置にピンポイントで強い波を形成する事が可能であるという点が、この方式の特徴です。

　これらの技術は、各種レーダー・通信アンテナ・非破壊検査・医療用診断機器・空中触覚デバイスなどに広く活用されています。フェーズドアレイの設計では、意図する条件をクリアする波が形成できるのかどうかを検討する事が大切であり、それに役立つのがシミュレーションです。本アプリでは、ユーザが設定する任意のパラメータに基づき、送信されて重ね合わされた平面波の振幅をシミュレートし、ヒートマップで可視化する事ができます。

## アプリの用途
　本アプリのシミュレーションは正確性を欠いているため、個人でフェーズドアレイソナーなどを製作する場合の大まかなシミュレーションや、高校物理における波の重ね合わせについての発展的な教育などにのみ役立ちます。しかし、高価で知識が無ければ操作できない専門のソフトウェアを使わずとも、フェーズドアレイを高い自由度で簡易的にシミュレートできるという点に本アプリの意義があります。

　なお、本アプリにおけるシミュレーションの不正確性について、以下の３点に特に注意を払う必要があります。
* シミュレーションにおいては波動方程式を用いず、単純な正弦波を平面波と定義しています。波動方程式を使用していないため、境界条件は無反射となっています。
* 平面波は、波源から放射状に広がるため、送信したエネルギーがより長い円周上に分散していき、波の振幅は小さくなっていきます。その波の振幅の減衰を本アプリのシミュレーションでは考慮せず、振幅は一定としています。
* パラメータで指定する送信素子の指向性は、波が全く存在しないか存在するかの２状態で不連続に考えます。これは現実的な考え方ではありません。

## シミュレーションの種類（出力について）
　本アプリによるシミュレーションの結果は、ユーザによる位相制御方式・表示形式・保存形式それぞれについての設定、合計３つが統合・反映された状態で保存されます。設定の違いを比較し易いように、以下にシミュレーション結果の例を示します。設定の仕様は、後述の「使い方（入力について）」で詳しく説明します。
- 位相制御方式　
  - ビームフォーミングモード
  - ビームフォーカシングモード（集束モード）
    <p>
      <img src="https://github.com/ShotaSasaki-HCU/Prog2kakushin/blob/main/Attached%20File/beam_forming.png?raw=true" width="300">
      <img src="https://github.com/ShotaSasaki-HCU/Prog2kakushin/blob/main/Attached%20File/beam_focusing.png?raw=true" width="300">
    </p>
    （左）ビームフォーミングモード，（右）ビームフォーカシングモード（集束モード）
- 表示形式
  - グラフ情報付き形式
    - 送信素子位置表示マーカーの有無・大きさ
  - シミュレーション結果の要素数と画素数一致形式
    <p>
      <img src="https://github.com/ShotaSasaki-HCU/Prog2kakushin/blob/main/Attached%20File/beam_forming.png?raw=true" width="250">
      <img src="https://github.com/ShotaSasaki-HCU/Prog2kakushin/blob/main/Attached%20File/beam_forming_nomarker.png?raw=true" width="250">
      <img src="https://github.com/ShotaSasaki-HCU/Prog2kakushin/blob/main/Attached%20File/grid2image.png?raw=true" width="150">
    </p>
    （左）グラフ情報付き形式＆送信素子位置表示マーカーあり，（中）グラフ情報付き形式＆送信素子位置表示マーカーなし，（右）シミュレーション結果の要素数と画素数一致形式
- 保存形式
  - PNG画像形式
  - GIFアニメーション形式
    - 周期ループ
    - ステアリング
      <p>
        <img src="https://github.com/ShotaSasaki-HCU/Prog2kakushin/blob/main/Attached%20File/beam_forming_nomarker.png?raw=true" width=240">
        <img src="https://github.com/ShotaSasaki-HCU/Prog2kakushin/blob/main/Attached%20File/beam_forming_periodic_loop.gif?raw=true" width="240">
        <img src="https://github.com/ShotaSasaki-HCU/Prog2kakushin/blob/main/Attached%20File/beam_forming_steering.gif?raw=true" width="240">
      </p>
      （左）PNG画像形式，（中）GIFアニメーション形式＆周期ループ，（右）GIFアニメーション形式＆ステアリング

## 使い方（入力について）
　本アプリには、`linear_phased_array()`という関数のみが含まれており、この関数の２１個の引数をユーザが指定することで全ての機能を制御できます。以下に各引数の設定方法を説明します。

### シミュレートする波の性質を設定する。
　本アプリでは、時刻$` t `$における原点からの距離$` x `$の地点の波の式を、

$$ 変位y = A\sin 2\pi f\left (t - \frac{x}{v} + 制御による位相差\right ) $$

と定義しています。
#### 1. A：送信波の振幅(mm)
　平面波は、波源から放射状に広がるため、送信したエネルギーがより長い円周上に分散していき、波の振幅は小さくなっていきます。前述した様に、その波の振幅の減衰を本アプリのシミュレーションでは考慮せず、振幅は一定としています。

#### 2. f：送信波の周波数(Hz)
#### 3. v：送信波の速さ(mm/s)
#### 4. t：時間(s)

### 計算範囲と計算精度を設定する。
　計算範囲は、XY平面上で各軸に対して下限と上限を指定します。計算精度は、計算幅`calc_width`により決定します。各軸の計算範囲が計算幅で割り切れない場合は、計算結果が計算範囲を満たす様にユーザの指定より少し広い範囲まで計算を行います。

#### 5. range_x_R：x軸上限(mm)
#### 6. range_x_L：x軸下限(mm)
#### 7. range_y_T：y軸上限(mm)
#### 8. range_y_B：y軸下限(mm)
#### 9. calc_width：計算幅(mm)
　計算幅は、大きすぎると合成波の様子が正しく描画できず、小さすぎると計算時間が掛かり過ぎます。波長$`\lambda = \frac{v}{f}`$の８分の１程度の値を推奨します。また、各軸の計算範囲を割り切ることができる様な値に設定しておくと、「指定した計算範囲ピッタリまでシミュレートできる」「結果表示の際に軸目盛りが見やすく表示される」というメリットを得られます。

### 送信素子の設定をする。
　ユーザが任意に送信素子の個数`tr_num`を指定すると、送信素子はx軸上に等間隔`tr_clearance`で、y軸対称となるように配置されてリニアアレイを構成します。

#### 10. tr_num：送信素子数（個）
#### 11. tr_directivity：送信素子指向性(rad)
　現実での送信素子(波源)は、強い波を送信できる方向が限定されている、つまり指向性を持ちます。この変数では、その範囲をy軸の正の方向を中心に指定します。正確には、指向性は波が全く存在しないか存在するかの２状態で不連続に考えて良いものではありませんが、本アプリでは計算を簡素にするためにその様に指定します。以下に指向性の値がどのように適用されるか分かり易いように、指向性を指定した送信素子を１つだけ表示した例を示します。
<p>
  <img src="https://github.com/ShotaSasaki-HCU/Prog2kakushin/blob/main/Attached%20File/tr_directivity_90.png?raw=true" width="240">
  <img src="https://github.com/ShotaSasaki-HCU/Prog2kakushin/blob/main/Attached%20File/tr_directivity_360.png?raw=true" width="240">
</p>

（左）`tr_directivity = np.deg2rad(90)`の場合，（右）`tr_directivity = np.deg2rad(360)`の場合

#### 12. tr_clearance：送信素子間隔(mm)
　ビームフォーミングモードの場合、送信素子間隔が波長$`\lambda = \frac{v}{f}`$の半分以下でないと、サイドローブが強く形成されます。

#### 13. tr_marker：送信素子マーカー描写の有無
　表示形式がグラフ情報付き形式の時、送信素子の位置を示す三角形のマーカーを表示するかどうかを指定します。`True`で表示、`False`で非表示となります。このマーカーは、全ての送信素子の位置が計算範囲内に入っていないと正しく表示されません。

#### 14. tr_marker_s：送信素子マーカーの大きさ

### ビームフォーミングモード用の設定をする。
　後述する１６番目の変数である`use_focusing_mode`が`False`の時、位相制御方式はビームフォーミングモードに設定されます。

#### 15. beam_direction：合成波の指向方向(rad)
　ビームフォーミングモードでは、振幅を最大にしたい方向を指定する必要があります。ここでの方向とは、x軸の正の方向となす角とし、x軸の正の方向からy軸の正の方向へ向かう回転を正とします。
<p>
  <img src="https://github.com/ShotaSasaki-HCU/Prog2kakushin/blob/main/Attached%20File/beam_forming.png?raw=true" width="240">
  <img src="https://github.com/ShotaSasaki-HCU/Prog2kakushin/blob/main/Attached%20File/beam_forming_45.png?raw=true" width="240">
</p>

（左）`beam_direction = np.deg2rad(90)`の場合，（右）`beam_direction = np.deg2rad(45)`の場合

### 位相制御方式の設定をする。
#### 16. use_focusing_mode：ビームフォーカシングモード（集束モード）の有効／無効
　この変数が`True`の時、位相制御方式はビームフォーカシングモード（集束モード）に設定されます。この変数が`False`の時、位相制御方式はビームフォーミングモードに設定されます。

#### 17. focusing_point：集束点の座標(mm)
　ビームフォーカシングモードでは、波を集中させたい座標を指定する必要があります。座標は、例えば`focusing_point = (0,50)`のようにタプルで指定します。

### 表示形式の設定をする。
#### 18. use_grid2image：シミュレーション結果の要素数と画素数一致形式の有効／無効
　この変数が`True`の時、表示形式はシミュレーション結果の要素数と画素数一致形式に設定されます。グラフタイトル・軸目盛り・カラーバーなど、ヒートマップ以外の一切の要素は表示されず、計算要素数がそのまま画素数になります。この機能を使うと、ヒートマップの情報が保存時に欠損したり、不適切に引き延ばされたりする事を防ぐことができ、指定条件通りのシミュレーション結果を観察することができます。この変数が`False`の時、表示形式はグラフ情報付き形式に設定されます。

### 保存形式の設定をする。
#### 19. use_gif：GIFアニメーション形式の有効／無効
　この変数が`'disabled'`の時、保存形式はPNG画像形式に設定されます。

　この変数が`'periodic_loop'`の時、保存形式はGIFアニメーション形式の周期ループに設定されます。周期ループでは、波の１周期内で少しずつ時間をずらしながら計算を行なっていき、それらをGIFアニメーションにすることで波の進行を可視化します。

　この変数が、`'steering'`の時、保存形式はGIFアニメーション形式のステアリングに設定されます。変数`beam_direction`は、45（度）より大きな値に設定してください。ステアリングのGIFアニメーションは、実用的な意味を全く持ちませんが、フェーズドアレイレーダー・ソナーなどにおいてどのように機械的可動部無しで走査しているのかを理解するのに役立ちます。この機能は、位相制御形式がビームフォーミングモードの場合のみ有効であり、ビームフォーカシングモード時にこの記述を行うと、その旨を伝えるエラー文が表示されます。

#### 20. name：結果を保存する際に内部的に使用されるファイル名の変数
#### 21. dura：GIFアニメーションの画像１枚あたりの表示時間(ms)
　この変数は、$`20\leq dura`$の範囲で指定してください。

---
# 【プログラム３について】漢字間違い探し
## アプリの概要
　本アプリは、たくさん並んだ同一の漢字の中に紛れ込んでいる似た漢字１文字を見つけ出す、漢字間違い探しゲームです。間違い発見までのプレイヤーのタイムが計測されて開発者のタイムと比較されるため、競争性を楽しむことができます。

## アプリの用途
　漢字間違い探しゲームをプレイすることによって、正確かつ迅速な判断力を養うことを目的としています。

## 操作方法（入力と出力）
　プログラムを実行すると、以下の様な説明文が順次ゆっくりと表示されていきます。

<img src="https://github.com/ShotaSasaki-HCU/Prog2kakushin/blob/main/Attached%20File/description.png?raw=true" width="450">

「それでは始めます。画像が表示されたらスタートです。」と表示されると、数秒後に間違い探しの画像が提示されます。

<img src="https://github.com/ShotaSasaki-HCU/Prog2kakushin/blob/main/Attached%20File/tan.png?raw=true" width="350">

<img src="https://github.com/ShotaSasaki-HCU/Prog2kakushin/blob/main/Attached%20File/below.png?raw=true" width="300">
