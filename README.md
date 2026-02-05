# homelab-compose

自宅ラボ環境の Docker Compose 定義。Portainer の Repository スタック機能で管理する。

## 構成

```
homelab-compose/
├── infra/          → NPM + Pi-hole（基盤サービス）
├── ops/     → Uptime Kuma + Flame（運用支援）
└── app/            → アプリケーション群（ghcr.io からの pull）
```

## Portainer スタック設定

| Stack | Compose path |
|-------|-------------|
| infra | `infra/compose.yaml` |
| ops | `ops/compose.yaml` |
| app | `app/compose.yaml` |

## セットアップ

各ディレクトリの `.env.example` を `.env` にコピーし、値を設定する。
Portainer の Repository スタック使用時は、Portainer UI の環境変数設定で値を入力する。

## 前提条件

- Docker ネットワーク `homelab-net` が作成済みであること
- `/opt/homelab/volumes/` 配下にデータディレクトリが存在すること
- `/opt/homelab/shared/certs/` に SSL 証明書が配置済みであること
