# 【プログラム１について】Pandasによる2020年4月1日〜2022年3月11日のNetflix視聴ランキング分析アプリ
　本アプリは、当該期間の各日付におけるNetflix視聴ランキングトップ１０についてのデータが記載されたCSVファイルを読み込み、それらに基づいて分析を行うアプリです。データの処理には、主にPandasライブラリを用いています。

## 分析内容について
　本アプリで得られる分析結果は以下の通りです。
### 1. トップ１０入り合計日数ランキング
　この機能では、当該期間について各作品が合計何日間ランクインしたかを、降順のランキング形式でユーザに表示する機能です。ユーザは、表示件数の指定を求められます。ユーザが、表示件数を入力するとランキングが表示されます。

### 2. 最大連続トップ１０入り日数ランキング
　この機能では、各作品が当該期間中に最大で何日連続ランクインしたかを、降順のランキング形式でユーザに表示する機能です。ユーザは、表示件数の指定を求められます。ユーザが、表示件数を入力するとランキングが表示されます。

### 3. 「Netflix上でのリリース日からの年数」と「トップ１０タイトル中の順位」の関係
　この機能では、記録されている全てのランキングについて、「Netflix上でのリリース日からの年数」と「トップ１０タイトル中の順位」の関係を散布図として表示します。

### 4. ランキング枠に対するNetflix独占配信の割合
　この機能では、記録されている全てのランキングの内、Netflix独占配信の割合・非独占配信の割合を円グラフで表示します。

## 使い方
　Google Colaboratory上で本アプリを実行すると、各種ライブラリのインポート処理が表示されてクリアされた後、以下の様な表示に切り替わります。
![Alt text](https://github.com/ShotaSasaki-HCU/Prog2kakushin/blob/main/Attached%20File/work1_main_menu.png?raw=true)

　ユーザが選択肢に一致する数字を入力した場合、一度表示がクリアされて新たな表示に遷移した後、各機能が実行されます。ユーザが選択肢以外の数字を入力した場合、その旨を伝えるエラー文が表示され、再度入力を求められます。各機能の実行が終わった後にエンターキーを押下すると、再びこの表示へ戻ってくることができます。選択肢の内、「5. 終了」が選択されると本アプリは終了します。

## 用途
　本アプリは、Netflixの長期的な視聴動向を分析することができます。個人がNetflix作品の選択を行う際や、コンテンツの製作者が人気な作品の共通点を研究する際に役立つ知見を引き出すことができます。

## 分析に使用したCSVファイルについて
　本アプリのデータ分析に使用した`netflix daily top 10.csv`は、下記のURLより入手しました。Licenseは、CC0: Public Domainに指定されており、本アプリで使用することに問題は生じません。

<https://www.kaggle.com/datasets/prasertk/netflix-daily-top-10-in-us>
