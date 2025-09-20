# PR: プライバシーポリシー／利用規約の更新（AdMob + RevenueCat）

## 概要
- プライバシーポリシーと利用規約を、以下の運用に合わせて更新しました。
  - 広告配信：Google AdMob（パーソナライズ広告、ATT実装）
  - 課金管理：RevenueCat（匿名ユーザーID＋購入レシートの検証／復元のみ）
  - ログイン機能なし・メール等の連絡先情報は不取得
  - 日本向け配信、一般（混合）向け、機微データ（HealthKit等）不使用

## 変更内容
- docs/privacy-policy.md
  - 第三者SDK（AdMob/RevenueCat）のデータカテゴリ・利用目的を追記
  - ATT（トラッキング許諾）と同意拒否時のNPA/コンテキスト広告を明記
  - 端末内保存データを「運動実施の有無のみ」に修正
  - HealthKit等の機微データへアクセスしない旨を明記
- docs/terms-of-service.md
  - Apple課金＋RevenueCatでの処理・復元を明記
  - 無料トライアルあり／広告のパーソナライズ（同意時）を明記

## App Store Connect: 「Appのプライバシー」回答マトリクス（日本向け）

前提
- 対象地域：日本
- オーディエンス：一般（混合）。子ども向け専用設定は未使用
- 広告：パーソナライズ広告（同意時）。ATTダイアログ表示
- ログイン・連絡先情報：なし
- 機微データ（HealthKit等）：不使用

1) 追跡（Tracking）
- 「このAppはユーザーをトラッキングしますか？」→ Yes
  - 理由：AdMobでIDFA等を用いた第三者広告の計測/最適化を行うため

2) 収集するデータタイプ（Collected Data）
- Location（位置情報）
  - Coarse Location（概ねの位置）※IPベース推定
- Identifiers（識別子）
  - Device ID（IDFA/IDFV）
  - User ID（RevenueCatの匿名ユーザーID）
- Purchases（購入）
  - Purchase History（サブスクリプション状態、取引ID、有効期限 等）
- Usage Data（利用データ）
  - Advertising Data（広告表示、インプレッション、クリック 等）
  - Product Interaction（アプリ内広告の閲覧/操作 等）
- Diagnostics：なし
- Contact Info：なし
- Health & Fitness：なし
- その他のカテゴリ：なし

3) データの関連付け（Linked to the User）
- 「このデータはユーザーに関連付けられますか？」→ Yes（以下は関連付け）
  - Identifiers：Device ID（広告/不正対策）、User ID（課金機能）
  - Purchases：Purchase History（購読の管理/復元）
  - Usage Data：Advertising Data, Product Interaction（広告配信/計測）
  - Location：Coarse（広告配信/計測）

4) データの用途（Purposes）
- Third-Party Advertising：Identifiers（Device ID）、Usage Data（Advertising Data, Product Interaction）、Location（Coarse）
- App Functionality：Purchases（購読の処理・復元）、Identifiers（User ID/RevenueCat）
- Fraud Prevention, Security, Compliance：Identifiers（Device ID/User ID）、Purchases（レシート検証）
- Developer’s Advertising or Marketing：使用しない
- Analytics：明示的な解析SDKは未使用（広告計測は第三者広告の範囲で実施）

5) 追跡・同意（ATT）
- ATTダイアログ：表示（Yes）
- 同意あり：パーソナライズ広告を表示
- 同意拒否：非パーソナライズ/コンテキスト広告、もしくは広告機能の一部制限

補足リンク
- Google プライバシーポリシー：https://policies.google.com/privacy?hl=ja
- Google の広告に関するポリシー：https://policies.google.com/technologies/ads?hl=ja
- RevenueCat Apple App Privacy ガイド：
  https://www.revenuecat.com/docs/platform-resources/apple-platform-resources/apple-app-privacy

## 確認事項
- 文面・マトリクスは現行実装（日本配信、ATT実装、パーソナライズ広告、混合オーディエンス）と整合しています
- 差異がある場合は、該当箇所を更新してください

## チェックリスト
- [ ] 文章と実装の一致を確認
- [ ] App Store Connectの「Appのプライバシー」に反映
- [ ] ストア申請前に最終確認

