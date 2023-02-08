# App and Environment

## UIApplication

[UIApplication](https://developer.apple.com/documentation/uikit/uiapplication)

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

# Views and Controls

## UICollectionView

[UICollectionView](https://developer.apple.com/documentation/uikit/uicollectionview)

[`UICollectionViewDiffableDataSource`](https://developer.apple.com/documentation/uikit/uicollectionviewdiffabledatasource)など、[`UICollectionViewDataSource`](https://developer.apple.com/documentation/uikit/uicollectionviewdatasource)プロトコルに準拠した
[`dataSource`]()プロパティが保持する

### UICollectionViewDiffableDataSource

紐付けた

[Making a Complex UICollectionView Layout With Self Sizing Cells (Part 2)](https://medium.com/@mfc83/making-a-complex-uicollectionviewlayout-with-self-sizing-cells-part-2-2652babfa4c0)

### UICollectionViewCell

[`UICollectionViewCell`](https://developer.apple.com/documentation/uikit/uicollectionviewcell)

[`contentConfiguration`](https://developer.apple.com/documentation/uikit/uicollectionviewcell/3600949-contentconfiguration)プロパティに[`UIContentConfiguration`](https://developer.apple.com/documentation/uikit/uicontentconfiguration)オブジェクトをセットすると、
[`UIContentConfiguration#makeContentView()`](https://developer.apple.com/documentation/uikit/uicontentconfiguration/3600982-makecontentview)が呼び出され、
[`contentView`](https://developer.apple.com/documentation/uikit/uicollectionviewcell/1620133-contentview)プロパティにContentViewが適用される。

また、[`backgroundConfiguration`](https://developer.apple.com/documentation/uikit/uicollectionviewcell/3600947-backgroundconfiguration)プロパティに[`UIBackgroundConfiguration`](https://developer.apple.com/documentation/uikit/uibackgroundconfiguration)オブジェクトをセットすると、
システム標準の背景スタイルをViewに対して適用することができる。
また、[`UICollectionViewCell#updateConfiguration(using:)`](https://developer.apple.com/documentation/uikit/uicollectionviewcell/3600950-updateconfiguration)をオーバーライドすることで、
背景スタイルのカスタムが可能となる。

> Thread 1: "Content view returned an invalid size {1.7976931348623157e+308, 36.333333333333336} from -systemLayoutSizeFittingSize:withHorizontalFittingPriority:verticalFittingPriority: which is not allowed. If you have implemented a custom content view, you need to add constraints inside it so that its size is not ambiguous, or you need to manually compute and return a valid size. Content view: <MeetSpot.FilterContentView: 0x143bdd5d0; frame = (0 0; 44 44); gestureRecognizers = <NSArray: 0x6000037f25e0>; backgroundColor = UIExtendedGrayColorSpace 1 1; layer = <CALayer: 0x600003a01800>>"

# View Layout

## UILayoutGuide

[UILayoutGuide](https://developer.apple.com/documentation/uikit/uilayoutguide)

View間の制約を決める際に用いる空の領域