# user-service

## 서비스 이름

| 항목           | 값                  |
|--------------|--------------------|
| 구현/PR/런타임 이름 | `user-service`     |
| Gradle group | `com.userservice` |
| 서비스 포트       | `8082`             |

## Contract Source

- 공통 계약 레포: `https://github.com/jho951/service-contract`
- 계약 동기화 기준 파일: [contract.lock.yml](contract.lock.yml)
- 계약 변경 절차: [contract-change-workflow.md](docs/contract-change-workflow.md)
- PR에서는 `.github/workflows/contract-check.yml`이 lock 파일과 계약 영향 변경 여부를 검사합니다.
- 인터페이스 변경 시 본 저장소 구현보다 계약 레포 변경을 먼저 반영합니다.

## 빠른 시작

GitHub Packages 의존성을 받으려면 `GH_TOKEN`이 필요합니다.

```bash
export GITHUB_ACTOR=jho951
export GH_TOKEN=<github-token-with-read-packages>
```

### Docker 개발 스택 실행:

```bash
./scripts/run.docker.sh up dev
```

### 로컬 직접 실행:

```bash
./scripts/run.local.sh
```

### 빌드와 테스트:

```bash
./gradlew build
```

### 상태 확인:

```bash
curl -i http://localhost:8082/actuator/health
curl -i http://localhost:8082/actuator/prometheus
```

## 문서

- [문서 홈](docs/README.md)
