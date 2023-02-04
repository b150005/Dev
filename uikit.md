# App and Environment

## UIApplication

[UIApplication](https://developer.apple.com/documentation/uikit/uiapplication)

### 役割

iOSアプリケーションの制御を行うシングルトンなクラス

- iOSアプリケーションのイベント(=状態変化)を[`UIApplicationDelegate`](https://developer.apple.com/documentation/uikit/uiapplicationdelegate)に伝達
イベント例 ) アプリの起動・メモリ不足・終了
- [`UIControl`](https://developer.apple.com/documentation/uikit/uicontrol)オブジェクトから転送されたメッセージをターゲットとなるオブジェクトにディスパッチ

### 使用例

- タッチイベントを一時的に無効化する
- リモート通知の有効化
- シェイク機能の有効・無効化
- `Universal Links`への対応
- ローカル通知スケジュールの管理
- 遠隔操作イベント受信の有効・無効化
- 状態のリストア

