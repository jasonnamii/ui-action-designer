# Material Design 3 Patterns

태스크별 인덱싱. 해당 태스크 관련 섹션만 참조. WebSearch("MD3 [컴포넌트] guidelines")로 최신 확인.

---

## 내비게이션

| 패턴 | 설명 | SHE |
|------|------|-----|
| Navigation bar (bottom) | 3~5개 최상위 목적지 | S: 핵심만 노출 |
| Navigation drawer | 사이드 드로어 | H: 전체 메뉴 숨김, 햄버거/스와이프 |
| Navigation rail | 태블릿/폴더블 사이드 | S: 아이콘+레이블 최소 |
| Top app bar | 제목+액션 | H: 스크롤 시 축소/숨김 |
| Bottom sheet | 하단 시트 | H: 스와이프 업 확장 |
| Dialog | 중앙 다이얼로그 | E: 의사결정 시만 |
| Side sheet | 사이드 패널 (대형) | H: 보조 정보 숨김 |

## 입력

| 패턴 | 설명 | SHE |
|------|------|-----|
| Filled text field | 배경 채움 | S: 명확한 입력 영역 |
| Outlined text field | 테두리 | S: 폼 내 구분 |
| Search bar | 검색 전용 | H: 탭→확장, 해제→축소 |
| Chip (filter/input/suggestion) | 태그 선택 | S: 상태 즉시 표현 |
| Switch | on/off | S: 즉각 상태 |
| Slider | 범위 값 | E: 드래그 이해 |
| Date/Time picker | 날짜 시간 | H: 탭 시 캘린더 노출 |
| Menu | 드롭다운 | H: 탭 시만 옵션 |

## 목록·콘텐츠

| 패턴 | 설명 | SHE |
|------|------|-----|
| List item (1/2/3-line) | 밀도별 리스트 | S: 정보량별 밀도 선택 |
| Swipe actions | 스와이프 액션 | H: 삭제·보관 숨김 |
| Expansion panel | 접기/펼치기 | H: 상세 숨김 |
| Card (elevated/filled/outlined) | 카드 컨테이너 | S: 관련 콘텐츠 묶음 |
| Carousel | 가로 스크롤 | H: 추가→스크롤 발견 |
| Tabs | 콘텐츠 분류 | H: 비활성 탭 숨김 |

## 피드백·액션

| 패턴 | 설명 | SHE |
|------|------|-----|
| Snackbar | 일시적 메시지 | E: 행동 결과 피드백 |
| Banner | 지속적 메시지 | E: 상태 변화 시 |
| Progress indicator | 진행 상태 | E: 작업 중만 |
| Tooltip | 짧은 설명 | E: 롱프레스/호버 시 |
| FAB (regular/small/large/extended) | 주요 액션 | S: 핵심 1개 집중 |
| Extended FAB | 텍스트 포함 | E: 스크롤→아이콘만 축소 |
| Icon button | 아이콘 액션 | H: 보조 액션 |
| Segmented button | 2~5 토글 | S: 상태 구분 |

## MD3 vs iOS SHE 차이

| 축 | MD3 | iOS |
|----|-----|-----|
| 정보 밀도 | 높음 허용 (다양한 리스트 밀도) | 낮음 지향 (여백 중시) |
| 숨김 방식 | drawer·bottom sheet 중심 | 제스처·상태 변화 중심 |
| 드러남 방식 | 명시적 (탭→열림) | 암시적 (스와이프→발견) |
| S 등급 | 판정 그대로 | 1단계↓ (더 숨김) |
