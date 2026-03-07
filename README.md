# ALICE-Archive

Long-term data archival with compression, versioning, and history tracking

## License

AGPL-3.0

## Architecture

```
Frontend :3000  -->  API Gateway :8080  -->  Core Engine :8081
```

| Layer | Port | Technology |
|-------|------|-----------|
| Frontend | 3000 | Next.js 14, Tailwind CSS |
| API Gateway | 8080 | Rust, Axum |
| Core Engine | 8081 | Rust, Axum |

## ALICE Crate Integration

alice-zip, alice-text-compression, alice-vcs, alice-history, alice-db

## Endpoints

| Method | Path | Description |
|--------|------|-------------|
| `POST` | `/api/v1/archive` | データアーカイブ（圧縮保存） |
| `POST` | `/api/v1/restore` | アーカイブ復元 |
| `GET ` | `/api/v1/versions` | バージョン履歴一覧 |
| `GET ` | `/api/v1/stats` | ストレージ統計 |
| `GET ` | `/health` | ヘルスチェック |

## Quick Start

```bash
cd services/core-engine
cargo run --release
curl http://localhost:8081/health
```

## Author

Moroya Sakamoto
