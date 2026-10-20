# 프리세일즈 제안서 노하우

![프리세일즈](./assets/logo.png)

프리세일즈의 실무 노하우·체크리스트·페이지 템플릿으로 한국어 제안서, RFP 대응 문서, 사업 제안 PPT를 준비합니다. 작성은 사용자의 Claude가 수행합니다. 프리세일즈가 별도 작성 모델을 호출하는 방식이 아닙니다. 기존 문서 구매·판매와 회원의 작성 크레딧은 프리세일즈 사이트에서 계속 이용합니다.

PRESALES connects reviewed writing knowhow and page templates to your own Claude workflow. You need a PRESALES account, browser sign-in, and OAuth permission. Listing available materials is free. A project reserves only your approved writing budget, and issuing one page material grant spends one writing credit. The plugin cannot charge a card, buy credits, or access another member's materials.

## Claude Code 설치

공식 등재 전의 로컬 검증은 압축을 푼 폴더에서 아래처럼 실행합니다. 공식 디렉터리의 공개 여부와 로컬 설치는 서로 다릅니다.

```sh
claude --plugin-dir ./presales-claude
```

로컬 마켓플레이스 방식도 사용할 수 있습니다. 경로는 이 README와 `.claude-plugin`이 있는 플러그인 폴더로 바꿉니다.

```sh
claude plugin marketplace add ./presales-claude
claude plugin install presales-proposal-knowhow@presales
```

실제 공개 저장소 URL은 공개 후의 릴리스 안내에서 확인하세요. 존재하지 않는 저장소나 아직 심사 중인 목록을 공식 설치 경로로 안내하지 않습니다.

## Claude의 연결·로그인

1. Claude Code의 `/mcp`에서 플러그인에 포함된 `presales` 서버를 선택하고 인증합니다. Claude 웹·Cowork에서는 공식 디렉터리나 사용자 지정 원격 MCP 연결에서 `https://presales.co.kr/api/presales-knowhow/mcp`를 사용합니다. 웹·Cowork에서 사용할 수 있는 연결 방식은 해당 계정의 실제 화면을 확인합니다.
2. OAuth 자동 발견·DCR·S256 PKCE를 사용합니다. 수동 API 키나 클라이언트 비밀키는 필요하지 않습니다. 요청 권한은 `knowhow:read knowhow:write`로 제한합니다.
3. 브라우저에서 기존 회원으로 로그인하거나 회원가입·필수 정보·동의를 완료한 뒤, 연결 앱과 권한을 직접 확인하고 승인합니다. 비밀번호나 인증 코드를 채팅에 입력하지 않습니다.
4. “프리세일즈 연결을 확인하고 자료 목록만 보여줘”라고 요청해 실제 조회를 확인합니다. setup 스킬도 같은 절차를 안내합니다.

설치한 스킬은 제안서·RFP·PPT 요청이 설명에 맞을 때 활용할 수 있습니다. 모든 대화에 추천되는 것을 보장하지 않으며 무관한 요청에는 도구를 사용하지 않습니다.

## 예시 요청과 비용

- “이 RFP의 평가항목에 맞는 목차와 프리세일즈 자료 목록을 제안해줘. 아직 크레딧은 쓰지 마.”
- “작성 100크레딧 예약에 동의해. 100페이지 프로젝트를 만들고 첫 2페이지 자료로 초안을 작성해줘.”
- “지금 프로젝트를 종료하고 미사용 예약을 해제해줘.”

회원이 이미 보유한 작성 크레딧의 승인한 한도 안에서 사용하며, 분석 크레딧과는 다릅니다. **페이지 자료 이용권 발급 시 1페이지당 작성 1크레딧**을 차감하고 동일 pageId 재수령은 중복 차감하지 않습니다. 완성 문서 페이지 수로 사후 과금하지 않습니다. OAuth 연결 동의만으로 유료 자료를 발급하지 않습니다. 부족한 이용 권한은 사실과 동작 정보만 안내하고 가격표·판매·업그레이드를 제안하거나 거래 페이지로 연결하지 않습니다. 종료는 미사용 예약만 돌려줍니다.

## 데이터·권한·해제

회원별 노하우 목록·작성 잔액·프로젝트 조회와 승인한 한도의 예약·자료 발급·미사용 예약 해제를 지원합니다. 프로젝트 제목과 페이지 목적은 서버에 전달되므로 개인정보나 RFP 원문 전체를 넣지 않습니다. 받은 가이드·템플릿은 Claude가 초안을 작성하는 데 사용합니다. 문서 원문 전체 덤프·다른 회원 정보·API 키 발급·결제·회원 수정은 지원하지 않습니다.

이 패키지에는 유료 원문·고객 데이터·키·토큰이 없습니다. 연결 해제는 사이트의 [AI 연결 관리](https://presales.co.kr/proposals/connect/manage)와 Claude의 연결 관리에서 진행합니다. Claude Code에서는 `/mcp`에서 실제 표시된 서버 이름을 확인해 인증을 해제할 수 있습니다. 진행 프로젝트의 예약 해제는 별도 작업입니다. 인증 오류는 OAuth 재연결로, 시간 초과는 동일 requestId·projectId·pageId 재조회로 복구합니다.

[연결 안내](https://presales.co.kr/proposals/connect) · [보유 이용권·차감 안내](https://presales.co.kr/proposals/connect/usage) · [개인정보처리방침](https://presales.co.kr/privacy) · [이용약관](https://presales.co.kr/terms) · [문의](https://presales.co.kr/consulting)

개발자용 API 형식 참고: [API 가이드](https://presales.co.kr/proposals/api-guide). 플러그인의 연결·권한 안내는 위 전용 안내 페이지를 사용합니다.

## 라이선스 범위

연결 코드·설정·스킬 지침·설명 문서는 [MIT License](./LICENSE)로 공개합니다. 유료 제안서·템플릿·노하우, 원격 API의 자료, 프리세일즈 제품 사이트 소스·고객 데이터와 브랜드·상표 권리는 MIT 범위에서 제외합니다. 원격 자료는 부여된 자료 이용권과 사이트 약관에 따라 이용합니다.
