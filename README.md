# 開発者向け　アプリ開発環境の構築手順書

前提知識: デスクトップPC(Windows)を使用するソフトウェア開発経験者  
前提条件:  [Git](https://git-scm.com/)と[VSCode](https://code.visualstudio.com/)がインストール済。GitHubのアカウントが存在する。  
必要ディスク容量：22GB  
到達目標: ピクターズのアプリ開発環境の構築  
<!-- 容量計算
Flutter…2.07 GB  
Android Studio…8 GB  
https://developer.android.com/studio/install?hl=ja#windows  
Android avd…8.64 GB  
リポジトリ…20.4 MB  
-->
## 作業手順  
1. [ソフトウェアのインストール](#1-ソフトウェアのインストール)  
1. [設定](#2-設定)  
1. [実行](#3-実行)  

> **NOTE**  
> [エラー発生時の解決方法](#エラー発生時の解決方法)

---

## 1. ソフトウェアのインストール
- ### Flutterのインストール
  -  [Flutter SDK](https://docs.flutter.dev/get-started/install/windows) をダウンロードしてインストールする。  
  -  環境変数`PATH`にFlutterを追加する。  
      ~~~
      <install directory>\flutter\bin
      ~~~
  -  `PowerShell`より以下コマンドを実行し、開発に必要なソフトウェアをインストールする。  
     ~~~
     flutter doctor
     ~~~
  -  `flutter doctor`はNo issues found!が表示されるまで繰り返し実行する。  

- ### Android Studioのインストール
  - [Android Studio](https://docs.flutter.dev/get-started/install/windows#android-setup) をインストールする。  
  - 環境変数`ANDROID_HOME`を追加する。  
     ```
     C:\Users\%USERNAME%\AppData\Local\Android\Sdk
     ```
     パスを`explorer`で開き、実際のパスに置き換える。

     > **NOTE**
     > 環境変数を追加時は、PowerShellを再起動する。  
     > 理由:実行中のPowerShellには、環境変数の変更反映されないため。  

  - Android SDK のライセンスを承諾する。  
    `PowerShell`より以下コマンドを実行する。  
      ```
      flutter doctor --android-licenses
      ```

- ### roverのインストール
  - [rover](https://www.apollographql.com/docs/rover/getting-started/#windows-powershell-installer)  をインストールする。
  > **NOTE**
  > 管理者権限のPowerShellより以下のコマンドを実行します。
  > ```
  > Set-ExecutionPolicy RemoteSigned -Scope Process
  > ```
  > PowerShellの[実行ポリシー](https://learn.microsoft.com/ja-jp/powershell/module/microsoft.powershell.core/about/about_execution_policies)を一時的に変更する必要があるため。 
- ### リポジトリをfork
  - [aipictors/app](https://github.com/aipictors/app)のリポジトリの右側のforkの▽を押し、`Create a new fork`を実行する。
  -  ローカルにリポジトリを作成する。

---

## 2. 設定
- ### 開発者モードを有効化
  -  管理者権限のPowerShellより、以下を実行します。
    ```
    start ms-settings:developers
    ```
- ### key.propertiesの作成
> **NOTE**  
> フォルダ構成図
> ```
> C:\GitHub\aipictors\app\android\
>                                  ├ key.jks
>                                  └ key.properties
> ```

  -   `keytool`を実行する。  
  ```
  "C:\Program Files\Android\Android Studio\jbr\bin\keytool.exe"
  ```

  -   作成した`key.jks`ファイルを`C:\GitHub\aipictors\app\android`フォルダに設置する。

  -   `key.properties`を作成し、`C:\GitHub\aipictors\app\android`フォルダに設置する。
key.properties
```key.properties
storePassword=<入力したパスワード>
keyPassword=<入力したパスワード>
keyAlias=key  
storeFile=key.jks  
```
> **NOTE**  
> ファイルの文字コード形式はUTF-8で保存する。

- ### Androidエミュレータを作成

  1. Android Studioを実行する。  
`C:\Program Files\Android\Android Studio\bin\studio64.exe`を実行する。  
  1. Device Managerを開き、Create Deviceを選択し、ダイアログの指示に従ってエミュレータを作成する。  

- ### 本家の手順書を実行
1. [本家の手順書](https://github.com/aipictors/app/blob/main/README.md)を参考に実行する。  

- ### VSCodeの設定
1. VSCodeで拡張機能の`Flutter`をインストールする。  
1. ファイル→フォルダを開く、`C:\GitHub\aipictors\app`を選択する。  

---

## 3. 実行
- ### VSCode
1. Android エミュレータを起動します。
画面右下のステータスバーの`Windows(windows-x64)`をクリックし、作成した[エミュレータ](#Androidエミュレータを作成)を選択する。  
Android エミュレータが起動し、Android エミュレータの画面が表示されます。
> **NOTE**
> 1. VSCodeのステータスバーの表示が`android emulator`に変わる。
> 2. Android エミュレータの起動に成功すると、タイトル名が「Android Emulator」のウィンドウが立ち上がります。

1. `VSCode`の左側の`実行とデバック`(Ctrl + Shift + D)より`Develop`を実行する。

お疲れ様でした。作業終了です。

---

## 参考情報
### エラー発生時の解決方法
  1. [Bard](https://bard.google.com/)を開き、エラーメッセージを貼り付ける。  
  2. `日本語で解決してください`を追加しチャット送信する。  
  3. Bardが解決方法を教えてくれる。  

[作業手順に戻る](#作業手順)
