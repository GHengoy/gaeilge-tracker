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
