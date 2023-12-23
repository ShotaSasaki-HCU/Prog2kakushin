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

　なお、本アプリにおけるシミュレーションの不正確性について、以下の２点に特に注意を払う必要があります。
* シミュレーションにおいては波動方程式を用いず、単純な正弦波を平面波と定義しています。波動方程式を使用していないため、境界条件は無反射となっています。
* 平面波は、波源から放射状に広がるため、送信したエネルギーがより長い円周上に分散していき、波の振幅は小さくなっていきます。その波の振幅の減衰を本アプリのシミュレーションでは考慮せず、振幅は一定としています。

## シミュレーションの種類（出力について）
　本アプリによるシミュレーションの結果は、ユーザによる位相制御方式・表示形式・保存形式それぞれについての設定、合計３つが統合・反映された状態で保存されます。設定の違いを比較し易いように、以下にシミュレーション結果の例を示します。設定の仕様は、後述の「使い方（入力について）」で詳しく説明します。
- 位相制御方式　
  - ビームフォーミングモード
  - ビームフォーカシングモード（集束モード）
    <p>
      <img src="https://github.com/ShotaSasaki-HCU/Prog2kakushin/blob/main/Attached%20File/beam_forming.png?raw=true" width="300">
      <img src="https://github.com/ShotaSasaki-HCU/Prog2kakushin/blob/main/Attached%20File/beam_focusing.png?raw=true" width="300">
    </p>
    （左）ビームフォーミングモード，（右）ビームフォーカシングモード
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
#### 5. range_x_R
