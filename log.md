# Operations Log

## [2026-08-21] LAUNCH | Niche C pipeline (Irish Gaelic Self-Study Progress Tracker)

- Selected niche: Irish Gaelic (Gaeilge) Self-Study Progress Tracker (see decisions/niche-selection.md) — broadened from an initial TEG-exam-only framing after review found the exam-only addressable market too small; final scope serves all self-taught Irish learners with TEG prep as one supported use case
- Gumroad product live: https://kimnet8.gumroad.com/l/kanmzp ($15.99, tracker CSV + guide, cover image included)
- Site live: https://ghengoy.github.io/gaeilge-tracker/
- 7 posts published, all passed content-safety validation (word count, no denylisted phrases, real product link); content independently reviewed to confirm the collection reads as broad-audience (not TEG-only) and contains no language-learning misinformation
- Gumroad has no confirmed public API for product creation as of this launch (see decisions/gumroad-integration-decision.md) — product was listed manually by the user; future updates will follow the same manual-assist path unless that changes
- Success metric being tracked going forward: first paid sale (no fixed deadline — organic SEO/discovery takes time)

## [2026-08-26] FEATURE | 뉴스레터 레이어 도입 (beehiiv, 니치 A 패턴 복제)

- `templates/base.html` 푸터에 beehiiv 구독 링크 추가 (https://gaeilge-tracker.beehiiv.com/subscribe)
- 전체 10개 페이지(포스트 9개 + index)에 자동 반영, 별도 콘텐츠/스크립트 변경 없음
- 니치 A(multi-cat-tracker)에서 검증된 패턴을 그대로 복제 — 별도 검증 기간 없음

## [2026-09-01] FEATURE | Amazon 제휴 링크 도입 (니치 A 패턴 복제)

- 신규 포스트 게시: irish-study-tools-essentials (학습 교재/도구 14개, 카테고리 검색형 Amazon Associates 링크)
- 허브-스포크 연결: pillar-guide.html에서 링크, 새 포스트에서 pillar-guide.html로 역링크
- 니치 A(multi-cat-tracker)에서 검증된 패턴을 그대로 복제 — 별도 검증 기간 없음

## [2026-09-03] FEATURE | 홈페이지 전환율 개선 (헤드라인 + 상품 하이라이트)

- `build_site.py`에 `homepage.json` 기반 히어로/상품 블록 렌더링 기능 추가(파일 없으면 기존과 동일하게 동작 — 하위 호환)
- 홈페이지(index.html)에 헤드라인/태그라인/상품 이미지/가격/구매 버튼 노출, 기존 포스트 목록은 "Latest Posts" 아래로 이동
- 개별 포스트 페이지는 이번 변경으로 영향받지 않음

## [2026-09-06] FEATURE | sitemap.xml 자동 생성

- `build_site.py`에 `site.json` 기반 sitemap.xml 생성 기능 추가(파일 없으면 기존과 동일 동작 — 하위 호환)
- Search Console 제출용 URL: https://ghengoy.github.io/gaeilge-tracker/sitemap.xml
- 개별 포스트/홈페이지 히어로 출력은 이번 변경으로 영향받지 않음

## [2026-09-07] CONTENT | 신규 포스트: 아일랜드어 학습 기간

- 검색 의도형 포스트 추가(목표별 소요 시간, 난이도 요인, 누적 시간의 중요성)
- pillar-guide에 링크 섹션 추가

## [2026-10-03] SEO | 메타 설명, canonical, Open Graph 태그 추가

- 모든 포스트 JSON에 `description` 추가, `build_site.py`가 base.html의 `{{HEAD_META}}` 자리에 description/canonical/og 태그 렌더링
- `site.json`에 `title`, `description`, `og_image` 추가 — 홈페이지 제목이 "Home" 대신 사이트 이름으로 표시
- `build_site.py`를 3개 니치 저장소에서 동일 코드로 통일(unlisted 포스트, 홈 히어로, Paddle/URL 구매 버튼 지원)
- 배경: Search Console에서 홈페이지 1개만 색인, 사이트맵 "가져올 수 없음" 상태 확인 — 2026-10-03 사이트맵 재제출 및 색인 요청

## [2026-10-09] CONTENT | 신규 포스트: 학습 중단 후 복귀 가이드

- 검색 의도형 포스트 추가: 몇 주/몇 달 중단 후 아일랜드어 학습을 어떻게 재개할지(수동적 능력 vs 능동적 능력의 차이, 정직한 실력 점검, 습관 재건 우선순위, 복귀 시 트래커 기록의 가치)
- 기존 9개 포스트와 중복 없음 확인(동기부여/정체기/빈도 질문은 다뤘지만 "중단 후 복귀"는 신규 주제)
- pillar-guide.html에 링크 섹션 추가, 역링크 포함

## [2026-10-16] CONTENT | 신규 포스트: 기본 대화에 필요한 어휘 수

- 검색 의도형 포스트 추가: "아일랜드어로 기본 대화를 하려면 단어를 몇 개나 알아야 하나" (목표별 어휘 목표, 빈도 기반 핵심 단어 우선순위, 수동적/능동적 어휘 구분, 트래커로 어휘 수 기록하는 법)
- 기존 11개 포스트와 중복 없음 확인(소요 시간, 학습량 등은 다뤘지만 "어휘 수" 자체는 신규 주제)
- pillar-guide.html에 링크 섹션 추가

## [2026-10-23] CONTENT | 신규 포스트: 듣기 이해력 격차 극복하기

- 검색 의도형 포스트 추가: "읽기는 되는데 왜 말하는 아일랜드어는 안 들리나" (연음/변이(mutation)/방언 차이가 듣기를 어렵게 만드는 이유, 속도/방언/어휘 문제 구분법, 단계별 듣기 사다리, 섀도잉 등 구체적 훈련법, 트래커로 듣기 시간과 체감 이해도를 함께 기록하는 법)
- 기존 12개 포스트와 중복 없음 확인(네 가지 기술 균형 포스트는 전반적 배분을, FAQ는 짧게만 다뤘지만 "듣기 격차"를 전담하는 포스트는 신규)
- pillar-guide.html에 링크 섹션 추가, 역링크 포함
- 리드 이미지: 관련성 있는 워터마크 없는 사진 없음(검색 결과 부족) — 이미지 없이 게시

## [2026-10-29] CONTENT | 신규 포스트: 듀오링고만으로 아일랜드어가 충분한가

- 짧은 코믹 스토리 형식 포스트 추가: "Is Duolingo enough to learn Irish?" (400일 연속 기록에도 실제 대화에서 막히는 상황, 스트릭은 습관이지 실력이 아님, 듣기/말하기 시간 별도 확보, 기술별 분 단위 기록으로 앱이 빠뜨리는 기술 확인)
- 기존 13개 포스트와 중복 없음 확인(FAQ에서 유료 앱을 짧게 언급했을 뿐, "앱 하나로 충분한가"를 전담하는 포스트는 신규)
- pillar-guide.html에 링크 섹션 추가, 역링크 포함
- 리드 이미지: 이미지 검색 API 타임아웃(2회) — 이미지 없이 게시

## [2026-10-29] CONTENT | 기존 포스트 12편을 4컷 만화+핵심 3줄 형식으로 변환

- 기존 포스트 12편을 4컷 만화+핵심 3줄 형식으로 변환 (제목/날짜/설명/URL은 그대로, 본문 html만 교체; 기존 긴 본문은 git 히스토리에 보존)
- 변환 대상: daily-study-routine-for-busy-learners, four-skills-balance-listening-speaking-reading-writing, how-long-does-it-take-to-learn-irish, how-many-words-for-a-basic-irish-conversation, how-to-use-the-tracker, irish-study-faq, irish-study-tools-essentials, reconnecting-with-irish-as-a-heritage-learner, restarting-irish-study-after-a-break, teg-exam-prep-tracking-your-readiness, why-cant-you-understand-spoken-irish-yet, why-tracking-your-irish-study-matters
- 제외: pillar-guide(허브), is-duolingo-enough-to-learn-irish(이미 신형식)
- validate_post 12편 모두 OK, 사이트 빌드 및 단위 테스트 59개 통과
