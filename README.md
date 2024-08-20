# paiza-tools

- 研究室の paiza 課題をある程度進めたが，結果をまとめるのが億劫な人向けのツール。
- 概要
  - 《シンプル版》paiza の評価結果一覧ページを手動でコピーしたものを貼り付けると，結果を HTML のテーブル（table 要素）として生成する。生成されたテーブルはコピペによって Microsoft Excel に貼り付けることができる。
  - 《Colab 版》paiza の評価結果一覧ページ（paiza 転職，paiza 新卒，などいくつかバリエーションがあるが内容はほぼ同じ）の HTML 文書を [selenium](https://www.selenium.dev/) で取得し，取得した HTML 文書を [Beautiful Soup 4](https://www.crummy.com/software/BeautifulSoup/) で解析・整形する。最終的に Microsoft Excel 形式のファイルで出力する。
- Acknowledgements
  - [paiza](https://paiza.jp/) は paiza 株式会社（旧社名:ギノ株式会社）が運営するプログラミング学習のための Web サービスです。
  - [Google Colab](https://colab.research.google.com/notebooks/welcome.ipynb) （正式名称「Colaboratory」）は Google Research が提供する Web サービスです。詳しくは [Google Colab FAQ](https://research.google.com/colaboratory/faq.html) を参照してください。

## 事前準備

- Paiza アカウントの作成する。
  - Paiza スキルチェックの問題を解く（まだ問題を多く解いていなければ，このツールは必要ない）。
- 《オプション》Colab を利用する場合は，Google アカウントを作成する。

Paiza アカウントと Google アカウントを連携する必要はない。メールアドレスも無関係のものでよい。

## 使い方（シンプル版）

### 評価結果一覧（1回目のチャレンジのみ）

1. 以下の URL をクリックして「paiza進捗状況を集計するためのツール」を開く。
   - https://ducis28.github.io/paiza-tools/paiza.html
2. 4行目くらいにある「評価結果一覧」をクリックして paiza の評価結果一覧を開く。自動的に別のタブやウィンドウで開かれるはずである。
   - まだ paiza にログインしていない場合はログインする
3. 評価結果一覧のページ全体を選択し（Ctrl + A），コピーする（Ctrl + C）。
   - Mac の場合は Ctrl でなく command キー
   - https://support.apple.com/ja-jp/HT201236
4. 「paiza進捗状況を集計するためのツール」の赤枠内をクリックしてから貼り付けする（Ctrl + V）。
5. 貼り付けると，ページ下部の「出力」にテーブルが自動生成される。
6. 研究室の所定フォーマットに近い出力が得られる。報告の際に活用するとよい。
   - 「出力」のすぐ下に「Copy to Clipboard」でテーブル全体をコピーできる。
   - テーブル全体をコピーした状態で Excel 等のスプレッドシートに貼り付けるとよい。

### 再チャレンジ結果一覧（2回目以降のチャレンジ）

使い方はほぼ同じ。

1. 以下の URL をクリックして「paiza進捗状況を集計するためのツール（再チャレンジ版）」を開く。
   - https://ducis28.github.io/paiza-tools/paiza2.html
2. 4行目くらいにある「再チャレンジ結果一覧」をクリックして paiza の再チャレンジ結果一覧を開く。自動的に別のタブやウィンドウで開かれるはずである。
   - まだ paiza にログインしていない場合はログインする
   - 再チャレンジは一度にすべて表示されるとは限らない。最初は最新の20件が表示されるはずである。ページ下部の「もっと見る」ボタンをクリックすると続きが表示される。ボタンをクリックするたびに20件ずつ追加して表示される。必要なだけ表示させた状態で次へ進むこと。
3. 再チャレンジ結果一覧のページ全体を選択し（Ctrl + A），コピーする（Ctrl + C）。
   - Mac の場合は Ctrl でなく command キー
   - https://support.apple.com/ja-jp/HT201236
4. 「paiza進捗状況を集計するためのツール（再チャレンジ版）」の赤枠内をクリックしてから貼り付けする（Ctrl + V）。
5. 貼り付けると，ページ下部の「出力」にテーブルが自動生成される。
6. 研究室の所定フォーマットに近い出力が得られる。報告の際に活用するとよい。
   - 「出力」のすぐ下に「Copy to Clipboard」でテーブル全体をコピーできる。
   - テーブル全体をコピーした状態で Excel 等のスプレッドシートに貼り付けるとよい。

## 使い方（Colab を利用する場合）

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
   - Colab の[シークレット機能](https://x.com/GoogleColab/status/1719798406195867814)を用いて認証情報が保存されている場合はそちらを優先的に利用する。
5. 最後まで実行すると，Excel ファイルがダウンロードされる。
6. 研究室の所定フォーマットに近い出力が得られる。報告の際に活用するとよい。
   - いくつかの情報が不足しているかもしれないので，貼り付ける前に確認すること。

## メモ

- 旧版: https://colab.research.google.com/drive/1Omen04HYPfxXKKrgi1ftyyLMKlKxyjb3?usp=sharing
