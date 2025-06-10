### 技術要件


| 項目 | 要件 |
| --- | --- |
| バックエンド | Python（Django, Django REST Framework） |
| フロントエンド | React（TypeScript, Vite, Bootstrap） |
| インフラ | Docker, Docker Compose, VPS |
| バッチ処理 | Celery, beat, Redis |
| 認証 | JWT（メール認証＋Google OAuth） |
| CI/CD | GitHub Actions（テスト自動化・CIパイプライン） |
| 外部API | Google Maps Static API |
| リバースプロキシ | Nginx： バックエンドとフロントエンド間の通信はNginxをリバースプロキシとして中継<br>CORS： セキュリティ対策 |
| その他 | Cloudflare（WAF、CDN）、Poetry（依存関係）<br>SSL/TLS証明書 |

### 工夫した点
- Dockerによる本番/開発環境の分離と環境の再現性
- 地図情報の定時バッチ保存
- CI/CDとテスト自動化の導入（pytest＋GitHub Actions）
- セキュリティ対策（WAF、IP/UA記録、API利用制限）
- マルチデバイス対応（スマホ・PC）
- Nginxを用いたリバースプロキシ構成によるマイクロサービス化（API/フロント分離）
- スムーズなデプロイ切り替え

### デモ

#### URL
https://zumi5.com

#### アカウント
| ユーザーID | パスワード |
| --- | --- |
| test@email.com | _Passw0rd |
※Googleアカウントならメール認証をスキップ可能です

#### ご利用手順
1. Journeyで旅先決定
2. Homeにクエストが追加されます
3. 到着したらスマホでHomeの"Complete Quest"ボタンを押します
4. すると、完了済みクエストに保存され、その地域のバッジを獲得します
5. 家に帰ったら早速、"あなたの冒険の記録"を書きましょう！<br>Homeの完了済みクエストをクリックすると、編集できます※画像もアップロード可能（iPhoneからでも直接アップロードできます）
6. メニューのユーザーアイコンからプロフィールやアプリ設定を変更できます
   - 共有機能"旅人の手記"を含め、これからも"冒険に出かけたくなる！"そんな機能を追加予定です）<br>
   - バッジは集めておくと後々意味があるようにしていくつもりです（企画中）
