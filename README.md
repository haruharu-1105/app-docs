# 開発者向け　セットアップ導入手順書

前提知識: デスクトップPC(Windows)を使用するソフトウェア開発者  
前提条件:  [Git](https://git-scm.com/)がインストール済み。GitHubのアカウントが存在する。   
必要ディスク容量：12GB   
到達目標: ピクターズの開発環境の構築 

## 作業手順の流れ
1. [ソフトウェアのインストール](#ソフトウェアのインストール)
1. [設定](#設定)
1. [実行](#実行)

> **NOTE**
> 問題発生時は、
[Bingチャット](https://www.microsoft.com/ja-jp/edge/features/bing-chat?form=MT00D8)
にエラーメッセージを貼り付け「解決方法を教えてください」で質問すると対処方法を教えて貰えます。

---

## ソフトウェアのインストール
### Flutterのインストール
1. [Flutter](https://docs.flutter.dev/get-started/install/windows) をインストールする。
1.  環境変数`PATH`にFlutterを追加する。   
   `<install directory>\flutter\bin`
1. `PowerShell`より`flutter doctor`を実行し、開発に必要なソフトウェアをインストールする。
> **NOTE**
> `flutter doctor`は`No issues found!`が表示されるまで繰り返し実行する。

### Android Studioのインストール
1. [Android Studio](https://docs.flutter.dev/get-started/install/windows#android-setup) をインストールする。
1. 環境変数`ANDROID_HOME`を追加する。  
`C:\Users\<ユーザー名>\AppData\Local\Android\Sdk`  
> **NOTE**
> 起動中のPowerShellには、環境変数の変更反映されません。  
> →環境変数を追加時は、PowerShellを再起動する。 
3. Android SDK のライセンスを承諾する。  
  `PowerShell`より`flutter doctor --android-licenses`を実行する。

### roverのインストール
- [rover](https://www.apollographql.com/docs/rover/getting-started/#windows-powershell-installer)  
> **NOTE**
> 管理者権限で`PowerShell`を実行する。  
> PowerShellの[実行ポリシー](https://learn.microsoft.com/ja-jp/powershell/module/microsoft.powershell.core/about/about_execution_policies)を一時的に変更する必要がある。    
> `Set-ExecutionPolicy RemoteSigned -Scope Process`

---

## 設定
### 開発者モードを有効にする。
`PowerShell`より`start ms-settings:developers`を実行する。
> **NOTE**
> 管理者権限でコマンドプロンプトを実行する。 

### リポジトリをforkする。
- [aipictors/app](https://github.com/aipictors/app)のリポジトリの右側のforkの▽を押し、`Create a new fork`をする。
### コード生成
- `dart run build_runner build`

### key.propertiesの作成
フォルダ構成図
```
C:\GitHub\aipictors\app\android\
                               ├ key.jks
                               └ key.properties
```

1. `keytool`を実行する。  
`C:\Program Files\Android\Android Studio\jbr\bin\keytool.exe`
2. 作成した`key.jks`ファイルを`C:\GitHub\aipictors\app\android`フォルダに設置する。

3. `key.properties`を作成し、`C:\GitHub\aipictors\app\android`フォルダに設置する。
```key.properties
storePassword=<入力したパスワード>
keyPassword=<入力したパスワード>
keyAlias=key  
storeFile=key.jks  
```
> **NOTE**  
> ファイルの文字コード形式はUTF-8で保存する。

### VSCodeの設定
1.VSCodeで拡張機能の`Flutter`をインストールする

---

## 実行
### VSCodeの設定
ファイル→フォルダを開く、`C:\GitHub\aipictors\app`

お疲れ様でした。
あとは、[本家の手順書](https://github.com/aipictors/app/blob/main/README.md)を参考に実行します。
