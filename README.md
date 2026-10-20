# PRESALES AI Plugins

![PRESALES](./codex/assets/logo.png)

프리세일즈의 검토된 작성 가이드·체크리스트·페이지 템플릿을 사용자의 Codex·ChatGPT·Claude에 연결하는 플러그인입니다. 업종과 관계없이 한국어 제안서·RFP 대응·사업 제안 PPT를 준비할 때 활용합니다. 완성 문서는 사용자의 AI가 작성합니다.

이 공개 저장소에는 연결 설정, 스킬 지침, 설치 설명과 기존 브랜드 이미지만 있습니다. 프리세일즈 제품 사이트의 소스, 유료 제안서·템플릿·노하우 본문, 고객 데이터, 인증 키나 토큰은 포함하지 않습니다. 저장소 공개·로컬 설치·공식 심사 접수·디렉터리 공개 등재는 각각 별개 상태입니다.

PRESALES provides reviewed Korean proposal writing guides and page templates to your own AI assistant. These integration packages use a remote OAuth-protected MCP server. They do not host a writing model, purchase credits, process payments, or grant access to other members' data. A PRESALES account and explicit connection permission are required.

## 패키지

| 폴더 | 용도 |
|---|---|
| [codex](./codex/README.md) | OpenAI portable Agent Plugins 설정·스킬 |
| [claude](./claude/README.md) | Claude 플러그인·로컬 마켓플레이스 설정·스킬 |

연결할 MCP 주소는 `https://presales.co.kr/api/presales-knowhow/mcp`입니다. OAuth 자동 발견·DCR·S256 PKCE를 사용하고 `knowhow:read`, `knowhow:write` 권한만 요청합니다. 비밀번호나 개인 API 키를 채팅에 붙여넣지 않습니다. 사이트에서 기존 로그인 또는 회원가입·필수 동의를 마친 뒤 연결 요청을 직접 승인합니다.

## Claude Code 로컬 설치

```sh
git clone https://github.com/maruAI-git/presales-ai-plugins.git
claude plugin marketplace add ./presales-ai-plugins/claude
claude plugin install presales-proposal-knowhow@presales
```

`/mcp`에서 프리세일즈 서버를 연결하고 “프리세일즈 자료 목록만 보여줘. 아직 크레딧은 쓰지 마”라고 요청합니다. Codex·ChatGPT 설치와 공식 디렉터리 이용 여부는 [연결 안내](https://presales.co.kr/proposals/connect)와 실제 클라이언트 화면에서 확인합니다.

## 크레딧과 데이터

목록·잔액 조회는 무료입니다. 회원이 이미 보유한 작성 크레딧을 사용자의 승인한 한도 안에서 예약하고, 페이지 자료 이용권을 발급할 때 **1페이지당 작성 1크레딧**을 차감합니다. 같은 페이지 재수령은 중복 차감하지 않고, 프로젝트 종료 시 미사용 예약만 해제합니다. OAuth 동의는 유료 자료 발급 승인과 다릅니다. 플러그인에서 가격표·판매·업그레이드를 홍보하거나 거래 페이지로 연결하지 않습니다.

프로젝트 제목과 페이지 작성 목적은 서버에 전달됩니다. 개인정보나 RFP 원문 전체를 해당 입력에 넣지 않습니다. 발급받은 가이드·템플릿은 사용 중인 AI가 초안을 작성하는 데 이용합니다. 연결 해제는 [프리세일즈 AI 연결 관리](https://presales.co.kr/proposals/connect/manage)와 클라이언트의 연결 관리에서 진행합니다. 프로젝트의 미사용 예약은 별도로 종료할 수 있습니다.

## 라이선스와 권리 범위

공개 연결 코드·설정·스킬 지침과 해당 설명 문서는 [MIT License](./LICENSE)로 제공합니다. **프리세일즈의 유료 제안서·템플릿·노하우, 원격 API가 반환하는 자료, 제품 사이트 소스와 고객 데이터는 이 MIT 공개 범위에 포함하지 않습니다.** 브랜드 이름과 이미지를 사용할 권리나 상표 사용 권한도 MIT로 부여하지 않습니다. 해당 자료의 이용은 프리세일즈의 별도 이용약관과 부여된 자료 이용권에 따릅니다.

[연결 안내](https://presales.co.kr/proposals/connect) · [보유 이용권·차감 안내](https://presales.co.kr/proposals/connect/usage) · [개인정보처리방침](https://presales.co.kr/privacy) · [이용약관](https://presales.co.kr/terms) · [문의](https://presales.co.kr/consulting)

개발자용 API 형식은 [API 가이드](https://presales.co.kr/proposals/api-guide)를 참고합니다. 연결과 이용 권한 안내는 위 전용 페이지를 사용합니다.
