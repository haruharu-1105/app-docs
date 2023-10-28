# 開発者向け　セットアップ導入手順書
- 前提
  Windowsを利用している開発者
- 目的
  開発環境の構築

## ソフトウェアのインストール
### Flutterのインストール
1. [Flutter](https://docs.flutter.dev/get-started/install/windows) をインストールする。
1. `flutter doctor`を実行し、開発に必要なソフトウェアをインストールする。

### Android Studioのインストール
1. [Android Studio](https://docs.flutter.dev/get-started/install/windows#android-setup) をインストールする。
1. 環境変数に`ANDROID_HOME`を追加する。  
`C:\Users\ユーザー名\AppData\Local\Android\Sdk`  
  ※起動中の`PowerShell`には、環境変数の変更反映されません。  
　　→環境変数を追加時は、`PowerShell`を再起動してください。
1. android-studio-dirを追加する。  
 `flutter config --android-studio-dir=<directory>`
1. Android SDK のライセンスを承諾する。  
   `flutter doctor --android-licenses`を実行する。
## 設定
### 開発者モードを有効にする。(管理者権限でコマンドプロンプトを実行)  
`start ms-settings:developers`

## リポジトリのforkする。
- リポジトリを`fork`する
## コード生成
- `dart run build_runner build`
## roverをインストールする。(管理者権限でPowerShellを実行)
- [rover](https://www.apollographql.com/docs/rover/getting-started/#windows-powershell-installer)  
※PowerShellの[実行ポリシー](https://learn.microsoft.com/ja-jp/powershell/module/microsoft.powershell.core/about/about_execution_policies)を変更する必要がある。  
  `Set-ExecutionPolicy RemoteSigned -Scope Process`

## key.propertiesの作成
