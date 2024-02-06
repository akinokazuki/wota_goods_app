# wota_goods_app
## サービス概要
オタ活に特化したCGMです。人の推し活グッズなどのアイデアを参考にしたり、自分の作品を他のオタクに自慢したりできます。

## このサービスへの思い・作りたい理由
サービス作成者の私もオタクで、推し活グッズを作ることがあります。制作物のアイデアは他の適当な制作物から得ることが多いですが、ネットで能動的にそれを探すのは結構難しいです（名前を知らないものは検索できないので）。twitterからアイデアを得ることもありますが、これも決まったタグや検索ワードがない限り検索しづらく、能動的に情報を得にくいです。そこで、制作意欲のあるオタクが集まり情報を交換し合う場があればいいなと思いこのサービスを作るに至りました。

## ユーザー層について
オタク（好きなコンテンツへの愛を物で表現しようとする人）
年齢や性別などは問いません
アニメ作品やアイドルが好きなオタクがメインです

## サービスの利用イメージ
ユーザーは自分の推しグッズを投稿することができます。
- 自作推し活グッズ（痛バ、うちわなど）
- 既製品グッズなどの展示（アクスタなど、　"オタク 祭壇"）
- 推しをイメージした既製品（服や靴など）
これらの投稿は物によってジャンル分けされ、ユーザーはそれを閲覧できます。
また、タグ付けによって、ユーザーは自分の好きなコンテンツに絞って投稿を検索できます。
ブックマークによりお気に入りの投稿を保持できます。

## ユーザーの獲得について
投稿をtwitterで共有できるようにし、拡散してもらって認知を深めたいです。

## サービスの差別化ポイント・推しポイント
- オタ活特化であること
- 物によってのジャンル分けを主とすることで、コンテンツの幅を超えてアイデアを共有できること

## 機能候補
### MVP
- 会員登録
- ログインなし
  - 一覧表示
  - 詳細表示
  - SNS共有
  - マルチ検索、オートコンプリート
- ログインあり
  - 簡易投稿
    - 題名
    - タグ付け
    - 画像（複数枚、1枚目をサムネ ）
    - 説明文
  - カスタム投稿（ActionText）
  - ブックマーク
  - プロフィール
    - 登録、編集
    - 閲覧（他のユーザー）

### その後
- コメント投稿
- プロフィールから、その人の投稿一覧の表示
- オススメ表示（レコメンド、閲覧数、ブックマーク数）

## 追加サービス、追加機能案
- ワードミュート、タグミュート、ユーザーミュート機能
- ユーザー、ジャンル、タグのお気に入り機能
- 通知機能
- ダイレクトメッセージ機能
- インプレッションなどの情報確認機能

## 昨日の実施方針予定
画像表示　Carrierwave, MiniMagick
ブックマーク　非同期処理
カスタム投稿　ActionText
検索　ransack stimilus-autocomplete
レコメンド　Amazon Personalize

## 画面遷移図
https://www.figma.com/file/bHJqGh3h68FvM1UsTawON6/wota_goods_app_UI?type=design&node-id=0%3A1&mode=design&t=k7lKKexKA04T6O8o-1

## テーブル説明
Users                   ユーザーのログイン情報を保存
Profiles                ユーザーのマイページに表示するプロフィール情報を保存
Posts                   投稿の情報を保存
Bookmarks               ブックマーク機能のためのテーブル
TagRelationships        タグと投稿を紐づけるテーブル
Tags                    タグを保存

## 開発環境
- サーバーサイド: Ruby on Rails 7系
　Ruby 3.3.0 Rails 7.0.8
- フロントエンド: Hotwire
- CSSフレームワーク: bootstrap5系
- インフラ:
  - Webアプリケーションサーバ: Fly.io
  - ファイルサーバ: AWS S3
  - セッションサーバ: Redis（Redis by Upstash）
  - データベースサーバ: PostgreSQL（Fly Postgres）
