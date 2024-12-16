# kotlin-blackjack

### Step1: 코틀린 DSL
- [x] 코틀린 DSL 실습

##### Hint
```kotlin
introduce {
   name("name")
   company("company")
   skills {
     soft("A passion for problem solving")
     soft("Good communication skills")
     hard("Kotlin")
   }
   languages {
     "Korean" level 5
     "English" level 3
   }
}
```

### Step2: 블랙잭

##### `규칙`
- 블랙잭 게임을 변형한 프로그램을 구현한다. 
- 블랙잭 게임은 딜러와 플레이어 중 카드의 합이 21 또는 21에 가장 가까운 숫자를 가지는 쪽이 이기는 게임이다.
- 카드의 숫자 계산은 카드 숫자를 기본, 
- 예외로 Ace는 1 또는 11로 계산할 수 있으며, 
- King, Queen, Jack은 각각 10으로 계산한다.
- 게임을 시작하면 플레이어는 두 장의 카드를 지급 받으며, 
- 두 장의 카드 숫자를 합쳐 21을 초과하지 않으면서 21에 가깝게 만들면 이긴다. 
- 21을 넘지 않을 경우 원한다면 얼마든지 카드를 계속 뽑을 수 있다.

##### `실행 결과`
```text
게임에 참여할 사람의 이름을 입력하세요.(쉼표 기준으로 분리)
pobi,jason

pobi, jason에게 2장의 나누었습니다.
pobi카드: 2하트, 8스페이드
jason카드: 7클로버, K스페이드

pobi는 한장의 카드를 더 받겠습니까?(예는 y, 아니오는 n)
y
pobi카드: 2하트, 8스페이드, A클로버
pobi는 한장의 카드를 더 받겠습니까?(예는 y, 아니오는 n)
n
jason은 한장의 카드를 더 받겠습니까?(예는 y, 아니오는 n)
n
jason카드: 7클로버, K스페이드

pobi카드: 2하트, 8스페이드, A클로버 - 결과: 21
jason카드: 7클로버, K스페이드 - 결과: 17
```

##### `요구사항 정리`
- 카드
  - [ ] 카드는 각각 총 13개의 랭크와, 4개의 무늬(mark or suits)가 있다
    - [x] rank : 2, 3, 4, 5, 6, 7, 8, 9, 10, A(Ace), K(King), Q(Queen), J(Jack)
    - [x] suits : spade(♠️), heart(🖤), diamond(♦️), club(♣️)
  - [x] rank 는 포인트를 가진다 
    - [x] 숫자 : 각 숫자, Ace : 1 또는 11, King, Queen, Jack : 10
  - [x] 총 52개의 카드가 무작위 순서로 생성 할 수 있다
  - [x] 카드들의 포인트를 더할 수 있다
- 플레이어
  - [ ] 게임에 참여하는 사람을 직접 입력 받는다
  - [ ] 첫번째 라운드는 랜덤한 두개의 카드를 지급 받는다
  - [ ] 다음 라운드부터 카드를 더 받을지 선택 할 수 있다
- 승리자
  - [ ] 카드들의 점수들을 비교하여 21점에 근접한 사람이 승리한다
     