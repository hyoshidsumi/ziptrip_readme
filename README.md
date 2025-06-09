## 技術要件

#### バックエンド
- Python（Django, Django REST Framework）

#### フロントエンド
- React（TypeScript, Vite, Bootstrap）
#### インフラ
- Docker, Docker Compose, VPS
#### バッチ処理
- Celery beat, Redis
#### 認証
- JWT（メール認証＋Google OAuth）
#### CI/CD
- GitHub Actions（テスト自動化・CIパイプライン）
#### 外部API
- Google Maps Static API
#### リバースプロキシ
- Nginx  
  バックエンド（Django）とフロントエンド（React）間の通信はNginxをリバースプロキシとして中継
- CORS
　セキュリティ対策
#### その他
- Cloudflare（WAF）
- Poetry（依存管理）
- SSL/TLS証明書


## 工夫した点
- Dockerによる本番/開発環境の分離と環境の再現性
- 地図情報の定時バッチ保存
- CI/CDとテスト自動化の導入（pytest＋GitHub Actions）
- セキュリティ対策（WAF、IP/UA記録、API利用制限）
- マルチデバイス対応（スマホ・PC）
- Nginxを用いたリバースプロキシ構成によるマイクロサービス化（API/フロント分離）
- スムーズなデプロイ切り替え

## デモ
https://zumi5.com

