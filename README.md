# 開発者向け　セットアップ導入手順書

前提知識: デスクトップPC(Windows)を使用するソフトウェア開発者  
到達目標: 開発環境の構築  

## ソフトウェアのインストール
### Flutterのインストール
1. [Flutter](https://docs.flutter.dev/get-started/install/windows) をインストールする。
1.  環境変数`PATH`を追加する。 
   `<install directory>\flutter\bin`
1. `flutter doctor`を実行し、開発に必要なソフトウェアをインストールする。

### Android Studioのインストール
1. [Android Studio](https://docs.flutter.dev/get-started/install/windows#android-setup) をインストールする。
1. 環境変数`ANDROID_HOME`を追加する。  
https://developer.android.com/studio/command-line/variables?hl=ja
1. 環境変数`ANDROID_HOME`を追加する。  
`C:\Users\<ユーザー名>\AppData\Local\Android\Sdk`  
> **NOTE**
> 起動中の`PowerShell`には、環境変数の変更反映されません。  
> →環境変数を追加時は、`PowerShell`を再起動してください。
1. Android SDK のライセンスを承諾する。  
   `flutter doctor --android-licenses`を実行する。

## roverのインストール
- [rover](https://www.apollographql.com/docs/rover/getting-started/#windows-powershell-installer)  
> **NOTE**
> 管理者権限でPowerShellを実行する。
> PowerShellの[実行ポリシー](https://learn.microsoft.com/ja-jp/powershell/module/microsoft.powershell.core/about/about_execution_policies)を一時的に変更する必要がある。  
> `Set-ExecutionPolicy RemoteSigned -Scope Process`

---

## 設定
### 開発者モードを有効にする。
コマンドプロンプトより`start ms-settings:developers`を実行する。
> **NOTE**
> 管理者権限でコマンドプロンプトを実行する。 

## リポジトリのforkする。
- リポジトリを`fork`する
## コード生成
- `dart run build_runner build`

## key.propertiesの作成
1. KEYTOOLのパスを通す。
　環境変数`PATH`を追加する。 
`C:\Program Files\Android\Android Studio\jbr\bin`

