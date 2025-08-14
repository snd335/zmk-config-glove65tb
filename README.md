# zmk-config-glove65tb

- glove65tb用のZMKファームウェア

# Docs

## ZMKファームウェアをビルドしてキーマップを変更する

### 全体の流れ

1. GitHubアカウントを作成する
2. ZMKファームウェアのリポジトリをフォークする
3. GitHub Actionsの有効化
4. KeymapEditorとフォークしたリポジトリを連携する
5. KeymapEditorでキー配列変更してファームウェアをビルドする
6. ファームウェアをキーボードに書き込む

### 1. GitHubアカウントを作成する

- 以下のドキュメントを参考にアカウント作成すること

  > 公式ドキュメント:
  > https://docs.github.com/ja/get-started/start-your-journey/creating-an-account-on-github
  >
  > 参考ブログ:
  > https://zenn.dev/keison8864/articles/069d9be35b92c2
  >

### 2. ZMKファームウェアのリポジトリをフォークする

- 以下のリポジトリをフォークする
  - https://github.com/keebkuro/zmk-config-glove65tb
- フォーク手順は以下の記事を参考に実施すること

  > 公式ドキュメント:
  > https://docs.github.com/ja/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo
  >
  > 参考ブログ:
  > https://www.kagoya.jp/howto/rentalserver/webtrend/githubfork/
  >

### 3. GitHub Actionsの有効化

- フォークしたリポジトリの「Actions」タブに移動し、「I understand my workflows, go ahead and enable them」をクリックし、github Actionsを有効化

  ![01.jpg](docs/images/01.jpg)

### 4. KeymapEditorとフォークしたリポジトリを連携する

- [KeymapEditor](https://nickcoutsos.github.io/keymap-editor/)にアクセス
- `GitHub` を選択

  ![02.jpg](docs/images/02.jpg)

- 「Login with GitHub」からでログインし、「Authorize Keymap Editor」を選択
- 指示に従い、フォークしたリポジトリにKeymapEditorがアクセスできるように進める

### 5. KeymapEditorでキー配列変更してファームウェアをビルドする

- [KeymapEditor](https://nickcoutsos.github.io/keymap-editor/)上でキーマップが表示されたら、好きにキーマップを編集する
- 画面左上の「Save」を押すと、編集したキーマップが適用されてGitHub Actionsが走り、自動的にビルドが開始します

  ![03.jpg](docs/images/03.jpg)

- 「Save」の隣に表示される「Latest」をクリックするとGitHubに移動し、ビルドが完了するとファームウェアがダウンロードできるようになります。（ビルドには2～4分かかる場合があります。）

### 6. ファームウェアをキーボードに書き込む

- ダウンロードしたzipファイルを解凍する

  ![04.jpg](docs/images/04.jpg)

#### 6-1. 右側キーボードにファームウェアを書き込む

- `Reset Button`をダブルクリックしてブートモードに切り替える

  ![05.jpg](docs/images/05.jpg)

- ブートモードのときにPCとキーボードをUSB接続すると`XIAO-SENSE`というリムーバルディスクが見えるようになります

  ![06.jpg](docs/images/06.jpg)

- `XIAO-SENSE`に`glove65tb_R-seeeduino_xiao_ble-zmk.uf2`ファイルをドラッグアンドドロップしてください

  > 補足:
  > うまく動作しないときは、`settings_reset-seeeduino_xiao_ble-zmk.uf2`を先に書き込んでリセットしてから、上述のファームウェア書き込みを実施すると解消できます
  >

#### 6-2. 左側キーボードにファームウェアを書き込む

- 右側キーボードと同じ手順で実施可能です
- 書き込むファームウェアは左側キーボード用のものに読み替えてください（`glove65tb_L-seeeduino_xiao_ble-zmk.uf2`）

### 7. 完了

- キーボードのスイッチを入れ直して完了
- キー入力が正常に行えることを確認してください

## ZMK Studioでキーマップを変更する

- TBA

## Keyboard Layout

![glove65tb.svg](keymap-drawer/glove65tb.svg)
