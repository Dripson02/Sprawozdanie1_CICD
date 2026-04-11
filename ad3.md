# Zbudować obrazy dla poszczególnych mikroserwisów i przesłać je do dedykowanych, swoich repozytoriów publicznych na DockerHub. <br/> Obrazy powinny być obrazami wieloarchitekturowymi i wspierać dwie architektury: linux/arm64 oraz linux/amd64. <br/> Dodatkowo, obrazy powinny zwierać wbudowane informacje SBOM. 

## Frontend
```
docker buildx build \
  --platform linux/amd64,linux/arm64 \
  -t TWOJ_LOGIN/tasklite-frontend:latest \
  --sbom=true \
  --push ./frontend
- backend
docker buildx build \
  --platform linux/amd64,linux/arm64 \
  -t TWOJ_LOGIN/tasklite-backend:latest \
  --sbom=true \
  --push ./backend
```
## Baza danych
```
docker buildx build \
  --platform linux/amd64,linux/arm64 \
  -t TWOJ_LOGIN/tasklite-db:latest \
  --sbom=true \
  --push ./database
```
