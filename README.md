# -
여행 지출 계산기 어플

```
개발 의도
여행을 갔는데, 한 명이 다 긁고 정리할 수 있다면 베스트.

하지만 경우에 따라서는 잔고가 부족하거나 여러 명이 긁다 보면 얼마를 줘야 하는지 난감해짐.

특히 3명일때는 분배가 편하지만, 그 이상으로 올라갈 경우 누가 얼마씩 줘야하는 지 난감해짐.

따라서 지출 내역만 넣으면 자동으로 얼마 줘야하는 지 출력해주는 프로그램을 개발한다.

(임시) 초기 버전에는 배분률을 전부 n빵, 즉 사용한 금액의 배분을 동일하게 가져간다고 본다.
```

```
개발 의도
여행을 갔는데, 한 명이 다 긁고 정리할 수 있다면 베스트.

하지만 경우에 따라서는 잔고가 부족하거나 여러 명이 긁다 보면 얼마를 줘야 하는지 난감해짐.

특히 3명일때는 분배가 편하지만, 그 이상으로 올라갈 경우 누가 얼마씩 줘야하는 지 난감해짐.

따라서 지출 내역만 넣으면 자동으로 얼마 줘야하는 지 출력해주는 프로그램을 개발한다.

(임시) 초기 버전에는 배분률을 전부 n빵, 즉 사용한 금액의 배분을 동일하게 가져간다고 본다.
```

```
변수 넣을거
Travel 클래스 (여행 전체 관리) 여행의 메타 데이터와 전체 리스트를 담는 최상위 클래스입니다.

title: 여행 제목 (예: "삿포몽 함께하겠습니다")

startDate / endDate: 여행 시작일과 종료일

participants: 참여자 리스트 (List 타입)

dayPlans: n일차 일정 리스트 (List 타입)

baseCurrency: 기준 화폐 (예: "KRW")

totalBudget: 설정한 총 예산 (선택 사항)

totalExpense: 현재까지 계산된 총 지출

calledExchangeRate: 현재 환율 반영함 dayPlans: n일차 일정 리스트 (List 타입)

baseCurrency: 기준 화폐 (예: "KRW")

totalBudget: 설정한 총 예산 (선택 사항)

totalExpense: 현재까지 계산된 총 지출

calledExchangeRate: 현재 환율 반영함

Participant 클래스 (참여자) 각 인원의 정보와 정산 상태를 관리합니다.

id: 참여자 고유 식별자 (중복 방지용 UUID 등)

name: 이름 혹은 별명 (예: "여우", "고양이")

profileEmoji: 프로필 아이콘 (이모지 혹은 이미지 경로)

totalSpent: 이 사람이 해당 여행에서 쓴 총금액 (계산 결과값)

isSettled: 정산 완료 여부 (Boolean)

DayPlan 클래스 (일정/n일차) 특정 날짜나 특정 테마의 지출 묶음입니다.

dayNumber: n일차 (숫자)

date: 실제 날짜

label: 일정 별칭 (예: "교토 당일치기", "2일차 돈키호테 쇼핑")

expenses: 해당 일정에 포함된 지출 항목 리스트

dailyTotal: 해당 일자의 지출 합계

Expense 클래스 (개별 지출 내역) 실제 소비 데이터가 담기는 가장 중요한 클래스입니다.

id: 지출 항목 고유 ID

description: 지출 내용 (예: "이치란 라멘")

amount: 결제 금액

currency: 결제 통화 (JPY, USD 등)

exchangeRate: 적용 환율

payerId: 결제한 사람의 ID (누가 먼저 카드를 긁었나?)

involvedParticipantIds: 비용을 나눠낼 사람들 ID 리스트

category: 지출 카테고리 (FOOD, TRANSPORT 등)

paymentMethod: 결제 수단 (CASH, CARD)

createdAt: 지출 입력 시간 (자동 생성용)

```

```
## 기능 점검1

여행 하나 생성하고

일정 하나 생성하고

사람 생성하고

지출 생성하기까지

```
