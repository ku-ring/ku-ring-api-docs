# 🎓 Kuring API Specification

### "걱정마, 건국대 공지사항은 쿠링이 알려줄게!"

건국대학교 공지사항 알림 서비스, **쿠링(Kuring)**의 공식 API 명세 저장소입니다. 본 저장소는 Stoplight를 활용하여 설계 우선(Design-first) 방식으로 API를 관리합니다.

<p align="center">
<img src="[https://user-images.githubusercontent.com/53814741/163469327-98af5c02-efc7-4c3e-8fec-9195ca6805ad.JPG](https://user-images.githubusercontent.com/53814741/163469327-98af5c02-efc7-4c3e-8fec-9195ca6805ad.JPG)" width="30%"/>
<img src="[https://user-images.githubusercontent.com/53814741/163469357-aed6a78a-4b65-4a9a-bead-d541e7eee702.JPG](https://user-images.githubusercontent.com/53814741/163469357-aed6a78a-4b65-4a9a-bead-d541e7eee702.JPG)" width="30%"/>
<img src="[https://user-images.githubusercontent.com/53814741/163469345-503b6b50-b240-4c8d-9656-c719a5f3d9f2.JPG](https://user-images.githubusercontent.com/53814741/163469345-503b6b50-b240-4c8d-9656-c719a5f3d9f2.JPG)" width="30%"/>
</p>

---

## 📖 개요: 왜 Stoplight인가요?

우리는 문서와 개발의 시차를 줄이고 소통의 효율을 높이기 위해 Stoplight를 도입했습니다.

* **병렬 개발 가능**: 서버 구현 완료 전, 설계된 명세를 바탕으로 클라이언트 개발을 즉시 시작할 수 있습니다.
* **커뮤니케이션 비용 감소**: 노션 등에 수동으로 업데이트하는 번거로움 없이, 시각화된 도구와 GitHub을 통해 변경 이력을 관리합니다.

🔗 **[쿠링 API 문서 바로가기](https://ku-ring.stoplight.io/docs/ku-ring)**

---

## 🚦 API 상태 관리 (Status Lifecycle)

협업 효율을 위해 모든 API는 개발 단계에 따른 상태 태그를 가집니다.

* **`Draft`**: 📝 설계 초안 단계. 구조가 변경될 수 있으며 실제 호출이 불가능할 수 있습니다.
* **`Deprecated`**: ⚠️ 삭제 예정. 신규 기능 개발 시 사용을 금지합니다.
* **`Completed`**: ✅ 개발 완료. 도메인 태그가 적용되며 실제 서버 연동이 가능합니다.

---

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

---

## 🚀 Stoplight 관리 프로세스

### ① API 추가 및 수정

1. **Edit Mode** 진입: `Form`(GUI) 또는 `Code`(YAML) 모드를 선택합니다.
2. **Endpoint 추가**: 좌측 `Paths`에서 New Path/Operation을 생성합니다.
3. **작업 저장**: 좌측 상단 **Commit & Publish**를 통해 저장합니다.

### ② 협업 및 머지 (매우 중요)

1. **브랜치 생성**: `main`에 직접 푸시하지 않고, 항상 **새 브랜치를 생성**하여 작업합니다.
2. **Proposal**: Stoplight에서 작업 내용을 공유합니다.
3. **GitHub PR**: 생성된 브랜치를 GitHub PR로 올리고, 팀원 간 합의 후 `main`에 머지합니다.
4. **Linter 확인**: `.spectral.mjs` 규칙에 따라 빨간색 경고가 없는지 확인합니다.

---

## 🔗 Team Kuring

* **App Download**: [iOS/Android 다운로드](https://ku-ring.onelink.me/Yxhp/598c8775)
* **Instagram**: [@kuring.konkuk](https://bit.ly/3JyMWMi)
* **Email**: kuring.korea@gmail.com

**쿠링팀에 오신 것을 환영합니다!** API 명세에 관한 논의는 언제든 GitHub PR과 이슈를 통해 진행해 주세요.
