# 開発者向け　セットアップ導入手順書

前提知識: デスクトップPC(Windows)を使用するソフトウェア開発者  
前提条件:  [Git](https://git-scm.com/)がインストール済み。GitHubのアカウントが存在する。   
必要ディスク容量：8GB
到達目標: ピクターズの開発環境の構築 

## 手順の大まかな流れ
ソフトウェアのインストール→設定→実行です。


> **NOTE**
> 問題発生時、
[bing-chat](https://www.microsoft.com/ja-jp/edge/features/bing-chat?form=MT00D8)
にエラーメッセージを貼り付け後、「解決方法を教えてください」で質問すると対処方法を教えて貰えます。

---

## ソフトウェアのインストール
### Flutterのインストール
1. [Flutter](https://docs.flutter.dev/get-started/install/windows) をインストールする。
1.  環境変数`PATH`に`Flutter`を追加する。   
   `<install directory>\flutter\bin`
1. `PowerShell`より`flutter doctor`を実行し、開発に必要なソフトウェアをインストールする。
> **NOTE**
> `flutter doctor`は`No issues found!`が表示されるまで繰り返し実行する。

### Android Studioのインストール
1. [Android Studio](https://docs.flutter.dev/get-started/install/windows#android-setup) をインストールする。
1. 環境変数`ANDROID_HOME`を追加する。  
`C:\Users\<ユーザー名>\AppData\Local\Android\Sdk`  
> **NOTE**
> 起動中の`PowerShell`には、環境変数の変更反映されません。  
> →環境変数を追加時は、`PowerShell`を再起動する。 
3. Android SDK のライセンスを承諾する。  
  `PowerShell`より`flutter doctor --android-licenses`を実行する。

## roverのインストール
- [rover](https://www.apollographql.com/docs/rover/getting-started/#windows-powershell-installer)  
> **NOTE**
> 管理者権限でPowerShellを実行する。  
> PowerShellの[実行ポリシー](https://learn.microsoft.com/ja-jp/powershell/module/microsoft.powershell.core/about/about_execution_policies)を一時的に変更する必要がある。    
> `Set-ExecutionPolicy RemoteSigned -Scope Process`

---

## 設定
### 開発者モードを有効にする。
`PowerShell`より`start ms-settings:developers`を実行する。
> **NOTE**
> 管理者権限でコマンドプロンプトを実行する。 

## リポジトリのforkする。
- リポジトリを`fork`する
## コード生成
- `dart run build_runner build`

## key.propertiesの作成
1. `keytool`を実行する。  
`C:\Program Files\Android\Android Studio\jbr\bin\keytool.exe`
2. 作成した`key.jks`ファイルを以下のフォルダに設置する。
`C:\GitHub\aipictors\app\android`

3. key.propertiesを作成する。  
```
storePassword=<入力したパスワード>
keyPassword=<入力したパスワード>
keyAlias=key  
storeFile=key.jks  
```
> **NOTE**  
> ファイルの文字コード形式はUTF-8で保存する。

---

## 実行
