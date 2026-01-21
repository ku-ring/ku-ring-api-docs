# 🎓 Kuring API Specification Docs

🔗 **[쿠링 API 문서 바로가기](https://ku-ring.stoplight.io/docs/ku-ring)**

## 🚦 API 상태 관리 (Status Lifecycle)

협업 효율을 위해 모든 API는 개발 단계에 따른 상태 태그를 가집니다.

* **`Draft`**: 📝 설계 초안 단계. 구조가 변경될 수 있으며 실제 호출이 불가능할 수 있습니다.
* **`Completed`**: ✅ 개발 완료. 도메인 태그가 적용되며 실제 서버 연동이 가능합니다.

## 🛠️ 개발 규칙 (Convention)

### 1. 파일 구조 및 경로

* **컴포넌트 분리**: 모든 DTO는 `components/schemas/{domain}/` 하위에 생성합니다.
* **상대 경로**: `$ref` 참조 시 `openapi.yaml` 기준의 상대 경로(`./components/...`)를 사용합니다.

### 2. 명세 작성 원칙

* **상세 정의**: `requestBody`와 `responses`를 누락 없이 정의합니다.
* **Example 필수**: 최소 1개 이상의 실제 데이터 예시(`example`)를 포함합니다.
* **Operation ID**: 직관적인 `operationId`(예: `loginUser`)를 부여하여 클라이언트 코드 생성을 지원합니다.

### 3. 예외 처리

* **구조 통일**: 성공은 `BaseResponse.yaml`, 에러는 `ErrorResponse.yaml` 구조를 따릅니다.
* **에러 명시**: 400, 401, 404 등 주요 예외 상황을 반드시 정의합니다.

## 🚀 Stoplight 관리 프로세스

[쿠링 노션 가이드 확인](https://www.notion.so/kuring/API-First-Design-Stoplight-2eefe8182edf8028bdf5eaa6fd15981e?source=copy_link)


## 🔗 Team Kuring

* **App Download**: [iOS/Android 다운로드](https://ku-ring.onelink.me/Yxhp/598c8775)
* **Instagram**: [@kuring.konkuk](https://bit.ly/3JyMWMi)
* **Email**: kuring.korea@gmail.com

**쿠링팀에 오신 것을 환영합니다!** API 명세에 관한 논의는 언제든 GitHub PR과 이슈를 통해 진행해 주세요.
