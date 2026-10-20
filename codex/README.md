# 프리세일즈 제안서 노하우

![프리세일즈](./assets/logo.png)

프리세일즈는 실무에서 만든 제안서의 작성 노하우·체크리스트·페이지 템플릿을 제공합니다. 이 플러그인은 한국어 제안서, RFP 대응, 사업 제안 PPT를 작성하는 사용자의 Codex가 해당 자료를 활용하도록 돕습니다. 완성 문서의 작성 모델은 사용자가 이용하는 AI입니다. 기존 프리세일즈 문서 구매·판매는 사이트에서 별도로 유지됩니다.

PRESALES supplies reviewed proposal writing guides, page layouts, and checklists to your own AI assistant. A PRESALES account and explicit OAuth permission are required. Catalog and balance lookups do not spend credits. Creating a project reserves the approved writing budget, and each issued page material grant spends one writing credit. This package does not buy credits or process payments.

## 설치와 연결

1. 공식 디렉터리에 공개된 뒤에는 플러그인 목록에서 **프리세일즈 제안서 노하우**를 선택합니다. 이 저장소나 ZIP의 존재는 공식 등재를 뜻하지 않습니다. 사전 검증은 OpenAI의 [테스트 절차](https://developers.openai.com/plugins/deploy/connect-chatgpt)에 따라 이 패키지를 로컬로 설치하거나 MCP 연결을 등록해 진행합니다.
2. 연결할 MCP 주소는 `https://presales.co.kr/api/presales-knowhow/mcp`입니다. 인증 방식은 OAuth이며 자동 클라이언트 등록(DCR)과 S256 PKCE를 사용합니다. 별도 비밀키 입력이나 수동 Authorization 헤더 설정은 필요하지 않습니다.
3. 클라이언트가 여는 프리세일즈 화면에서 로그인합니다. 계정이 없으면 회원가입과 필수 정보·동의를 마친 뒤 연결 화면으로 돌아옵니다. 연결 앱·권한을 확인하고 직접 승인합니다.
4. setup 스킬을 실행하거나 “프리세일즈 연결을 확인하고 자료 목록만 보여줘”라고 요청합니다. 실제 도구 조회가 성공하면 연결을 이용할 수 있습니다.

## 사용 예

- “이 RFP에 맞는 자료를 찾아 목차를 제안해줘. 아직 크레딧은 쓰지 마.”
- “작성 크레딧 100개 한도에 동의해. 100페이지용 프로젝트를 예약하고 목차부터 보여줘.”
- “승인한 프로젝트의 첫 2페이지 자료로 초안을 작성해줘.”
- “같은 페이지 자료를 다시 받아 수정해줘. 새 페이지는 만들지 마.”
- “작업을 마치고 미사용 예약을 해제해줘.”

## 비용과 사용자 승인

작성 크레딧은 분석 크레딧과 구분됩니다. 회원이 이미 보유한 작성 크레딧 중 사용자가 승인한 한도 안에서 예약하고 **페이지 자료 이용권을 발급할 때 1페이지당 1크레딧**을 차감합니다. 같은 페이지 재수령은 중복 차감하지 않습니다. 완성 문서 페이지 수를 나중에 측정해 과금하지 않습니다.

연결 승인은 유료 자료 발급 동의와 별개입니다. 플러그인은 카드 등록·결제·자동 충전·회원정보 변경·API 키 생성 도구를 제공하지 않습니다. 플러그인에서 가격표·판매·업그레이드를 제안하거나 거래 페이지로 연결하지 않습니다. 권한이 부족하면 해당 기능을 사용할 수 없다는 사실과 동작 정보만 안내합니다. 종료 시 미사용 예약만 해제하며 이미 발급한 자료가 자동 환불되는 것은 아닙니다.

## 데이터와 권한

OAuth 권한은 `knowhow:read`와 `knowhow:write`입니다. 연결한 회원의 잔액·프로젝트, 노하우 목록, 승인된 페이지 자료를 조회하거나 프로젝트 예약·자료 발급·종료에 사용합니다. 프로젝트 제목과 페이지 작성 목적은 프리세일즈에 전달됩니다. 필요한 최소 정보만 입력하고 개인정보·RFP 전체·고객 비밀을 작성 목적에 넣지 마세요. 제공된 페이지 자료는 사용 중인 AI로 전달되어 초안 작성에 활용됩니다.

이 패키지에는 유료 원문·노하우 본문·고객 데이터·비밀번호·API 키·OAuth 토큰이 들어 있지 않습니다. 전체 원문 덤프나 다른 회원 자료 요청은 지원하지 않습니다. 보관 및 권리 행사 안내는 [개인정보처리방침](https://presales.co.kr/privacy)과 [이용약관](https://presales.co.kr/terms)을 확인하세요.

## 연결 해제와 오류 복구

프리세일즈의 [AI 연결 관리](https://presales.co.kr/proposals/connect/manage)에서 해당 연결을 해제하고 클라이언트에서도 플러그인 연결을 제거합니다. 진행 중 프로젝트의 미사용 예약은 별도로 종료할 수 있습니다. 토큰 만료는 OAuth 재연결로 복구하고, 요청 시간 초과는 동일 프로젝트·요청·페이지 ID로 다시 조회합니다. 실패했다고 새 프로젝트를 반복 생성하지 마세요.

[연결 안내](https://presales.co.kr/proposals/connect) · [보유 이용권·차감 안내](https://presales.co.kr/proposals/connect/usage) · [문의](https://presales.co.kr/consulting)

개발자용 API 형식 참고: [API 가이드](https://presales.co.kr/proposals/api-guide). 플러그인의 연결·권한 안내는 위 전용 안내 페이지를 사용합니다.

## 라이선스 범위

연결 코드·설정·스킬 지침·설명 문서는 [MIT License](./LICENSE)로 공개합니다. 유료 제안서·템플릿·노하우, 원격 API의 자료, 프리세일즈 제품 사이트 소스·고객 데이터와 브랜드·상표 권리는 MIT 범위에서 제외합니다. 원격 자료는 부여된 자료 이용권과 사이트 약관에 따라 이용합니다.
