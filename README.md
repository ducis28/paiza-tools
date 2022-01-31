# paiza-tools

- 研究室の paiza 課題をある程度進めたが，結果をまとめるのが億劫な人向けのツール。
- 概要
  - paiza の評価結果一覧ページ（paiza 転職，paiza 新卒，などいくつかバリエーションがあるが内容はほぼ同じ）の HTML 文書を [selenium](https://www.selenium.dev/) で取得し，取得した HTML 文書を [Beautiful Soup 4](https://www.crummy.com/software/BeautifulSoup/) で解析・整形する。最終的に Microsoft Excel 形式のファイルで出力する。
- Acknowledgements
  - [paiza](https://paiza.jp/) は paiza 株式会社（旧社名:ギノ株式会社）が運営するプログラミング学習のための Web サービスです。
  - [Google Colab](https://colab.research.google.com/notebooks/welcome.ipynb) （正式名称「Colaboratory」）は Google Research が提供する Web サービスです。詳しくは [Google Colab FAQ](https://research.google.com/colaboratory/faq.html) を参照してください。

## 事前準備

- Paiza アカウントの作成する。
  - Paiza スキルチェックの問題を解く（まだ問題を多く解いていなければ，このツールは必要ない）。
- Google アカウント（Colab を実行するために必要）を作成する。

Paiza アカウントと Google アカウントを連携する必要はない。メールアドレスも無関係のものでよい。

## 使い方

1. 以下のバッジ（Open in Colab）をクリックする。
   - [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](http://colab.research.google.com/github/ducis28/paiza-tools/blob/main/paiza.ipynb)
   - クリックすると，Google Colab のノートブックが開くはず。
2. 画面上部のメニューから「ランタイム」＞「すべてのセルを実行（Ctrl+F9）」を選択する。
   - まだ Google にログインしていないは「Google へのログインが必要」というダイアログが表示される。
   - その場合は「ログイン」ボタンをクリックして何らかの Google アカウントでログインする。
   - ログインすると，Colab に自動的に転送されて戻ってくるはずだが，自動的に戻らない場合は再び上のバッジをクリックしてノートブックを開く。
   - Google にログインした状態で，再び「ランタイム」＞「すべてのセルを実行（Ctrl+F9）」を選択する。
3. 「警告: このノートブックは Google が作成したものではありません。」のようなダイアログが表示される。しっかりと読んで，問題ないことを確認したうえで「このまま実行」を押す。
   - 「すべてのセルを実行」でなく，１つずつセルを確認しながら実行してもよい。勉強のためにも，それがおススメ。
4. 途中でいくつかの情報を入力を促されるので入力する。必要なのは **paiza のメールアドレス** と **パスワード** の２つ。それぞれ入力後に Enter キーを押すと送信される。
   - パスワードは一時的に変数に格納されるが，永続的には保存されないはずである（気になる場合は，ノートブックのソースコードをじっくり読むこと）。
5. 最後まで実行すると，Excel ファイルがダウンロードされる。
6. 研究室の所定フォーマットに近い出力が得られる。報告の際に活用するとよい。
   - いくつかの情報が不足しているかもしれないので，貼り付ける前に確認すること。

## メモ

- 旧版: https://colab.research.google.com/drive/1Omen04HYPfxXKKrgi1ftyyLMKlKxyjb3?usp=sharing
