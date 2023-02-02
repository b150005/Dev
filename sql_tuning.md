# 参考

- [Oracle Database 21c - 公式ドキュメント](https://docs.oracle.com/cd/F39414_01/index.html)
- [OracleのSQLチューニングの考え方についてまとめてみた - Qiita](https://qiita.com/tbtakhk/items/2b48b3185ef192c8d730)
- [「Oracle SQLチューニング講座」関連の最新 ニュース・レビュー・解説 記事 まとめ - ITmedia](https://atmarkit.itmedia.co.jp/ait/kw/oracle_sql_tuning.html)

# SQLチューニングの手順

1. パフォーマンスの現状確認
   - システム環境
   - 問題の発生状況
2. 問題点の切り分け
   - OSリソース
   - プログラム
   - DBMS(インスタンス・SQL)
3. 目標設定
   - 実行時間
   - アプリケーションの反応時間
4. パフォーマンス検証
   - SQL詳細情報
   - DBMS稼働状況
   - OSリソース
   - 処理時間
5. SQLチューニング

# パフォーマンスへの影響度

上に行けば行くほど効果が大きい

1. ビジネスルール(システム要件)
2. データ設計(ER, CRUD)
3. SQLチューニング(SQL, 索引, テーブル定義)
4. アプリケーション設計(UI / UX, プログラムロジック, スレッド設計, APサーバ)
5. DBの物理構造(リソース)
6. OS, ネットワーク, H/W

# アクセスパス

# SQLチューニング

> SQLチューニングは、高負荷SQL文の効率を識別、チューニングおよび向上させる反復プロセス
> (2日でパフォーマンス・チューニング・ガイド - Oracleパフォーマンス・メソッドの使用)

## 主なパフォーマンス低下の要因

- CPUのボトルネック
- メモリ構造のサイズ不足
- I/O使用率の上昇
- アプリケーション側の問題
- 同時アクティビティ(同時実行)
- DB構成
- 短期間・断続的なパフォーマンス低下
- 時間経過によるDBパフォーマンスの低下
- 非効率・高負荷なSQL文
- オブジェクト競合
- SQLチューニングによる実行計画の変更

## 準備

1. ユーザからのフィードバック
2. H/W, OSのチェック
3. AWR(Automatic Workload Repository; 自動パフォーマンスチューニング)機能の有効化
   - `STATISTICS_LEVEL` = `TYPICAL(default)` or `ALL`
4. ADDM(Automatic Database Diagnostic Monitor; 自動データベース診断モニタ)機能の有効化
   - `CONTROL_MANAGEMENT_PACK_ACCESS` = `DIAGNOSTIC+TUNING(default)` or `DIAGNOSTIC`

## 事前チューニング

1. ADDMの自動監視結果を確認
2. Cloud Controlのリアルタイム監視結果を確認
3. Cloud Controlのアラート監視結果を確認

## 事後チューニング

1. ADDMを手動実行し、現状パフォーマンスを診断
2. ASH(Active Session History; アクティブセッション履歴)レポートを参照し、一時的なパフォーマンスの問題を解決
3. AWRの期間比較レポートで時間経過によるパフォーマンスを比較

## SQL文チューニング

1. ADDMの検出結果・上位SQLセレクションを用いて高負荷SQL文を識別
2. 高負荷SQL文をチューニング
3. データアクセスパスを最適化
4. SQLパフォーマンスアナライザによるSQLパフォーマンス影響を分析

