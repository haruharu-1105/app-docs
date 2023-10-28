# app-docs
初期導入
必要なもの

## Flutterのセットアップ
- [Flutter](https://docs.flutter.dev/get-started/install/windows) をインストールする。
  
## Android Studioのセットアップ
- [Android Studio](https://docs.flutter.dev/get-started/install/windows#android-setup) をインストールする。
- 環境変数に`ANDROID_HOME`を追加する。  
`C:\Users\ユーザー名\AppData\Local\Android\Sdk`  
※環境変数が反映されないため、環境変数を追加時は、PowerShellを再起動する。
- android-studio-dirを追加する。  
 `flutter config --android-studio-dir=<directory>`
- `flutter doctor --android-licenses`を実行する。

## リポジトリのforkする。
- リポジトリをforkする
## コード生成
- `dart run build_runner build`
## roverをインストールする。(管理者権限でPowerShellを実行)
- [rover](https://www.apollographql.com/docs/rover/getting-started/#windows-powershell-installer)  
※PowerShellの[実行ポリシー](https://learn.microsoft.com/ja-jp/powershell/module/microsoft.powershell.core/about/about_execution_policies)を変更する必要がある。  
  `Set-ExecutionPolicy RemoteSigned -Scope Process`
## 開発者モードを有効にする。(管理者権限でコマンドプロンプトを実行)  
`start ms-settings:developers`

## key.propertiesの作成
