# App Store Connect: 「Appのプライバシー」回答マトリクス（Fit Routine）

前提
- 対象地域：日本
- オーディエンス：一般（混合）。子ども向け専用設定は未使用
- 広告：パーソナライズ広告（同意時）。ATTダイアログ表示
- ログイン・連絡先情報：なし
- 機微データ（HealthKit等）：不使用

1) 追跡（Tracking）
- 「このAppはユーザーをトラッキングしますか？」→ Yes
  - 理由：AdMob（第三者広告）のためIDFA等を利用

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
- 同意拒否：非パーソナライズ/コンテキスト広告、または広告機能の一部制限

補足リンク
- Google プライバシーポリシー：https://policies.google.com/privacy?hl=ja
- Google の広告に関するポリシー：https://policies.google.com/technologies/ads?hl=ja
- RevenueCat Apple App Privacy ガイド：
  https://www.revenuecat.com/docs/platform-resources/apple-platform-resources/apple-app-privacy

