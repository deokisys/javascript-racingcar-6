# 자동차 경주

## 기능 요구사항
- 주어진 횟수 동안 n대의 자동차는 전진 또는 멈출 수 있다.
- 각 자동차에 이름을 부여할 수 있다. 전진하는 자동차를 출력할 때 자동차 이름을 같이 출력한다.
- 자동차 이름은 쉼표(,)를 기준으로 구분하며 이름은 5자 이하만 가능하다.
- 사용자는 몇 번의 이동을 할 것인지를 입력할 수 있어야 한다.
- 전진하는 조건은 0에서 9 사이에서 무작위 값을 구한 후 무작위 값이 4 이상일 경우이다.
- 자동차 경주 게임을 완료한 후 누가 우승했는지를 알려준다. 우승자는 한 명 이상일 수 있다.
- 우승자가 여러 명일 경우 쉼표(,)를 이용하여 구분한다.
- 사용자가 잘못된 값을 입력한 경우 throw문을 사용해 "[ERROR]"로 시작하는 메시지를 가지는 예외를 발생시킨 후, 애플리케이션은 종료되어야 한다.


## 구현 기능 목록
`요구사항에 없는 추가적인 예외는 하이라이트로 작성하였습니다.`

- 입력받기
    - 자동차 이름을 쉼표를 기준으로 구분하여 입력
        - 자동차 이름을 해쉬 형태로 받는다.
    - 시도할 횟수를 숫자로 입력

- 입력 예외 처리
    - 자동차 이름 예외
        - 자동차 이름은 1글자 이상 5글자 이하
        - 빈글자 및 6글자 이상은 오류
        - `자동차 이름은 대소문자 구분을 한다.`
            - 'aA'와 'Aa'는 다른 자동차
        - `자동차 이름은 영어, 숫자 전부 가능하다.`
        - `중복된 이름 입력시 오류로 처리한다.`
    - 시도 횟수
        - 1이상의 숫자만 가능
        - `0 또는 빈숫자는 오류로 처리한다.`
        - 숫자가 아닌 문자가 입력되면 오류 처리

- 레이싱 진행하기
    - 시도 횟수만큼 레이싱을 진행
    - 각 자동차마다 0-9사이 무작위 숫자를 받는다.
        - 4이상인 경우에만 이동횟수를 1더해준다.
    - 레이싱 진행상황을 출력한다.
        - 입력된 자동차 순서대로 출력한다.
    - 레이싱이 종료되었을때 우승자들을 출력한다.
        - 공동우승자는 입력 순서를 기준으로 순서대로 출력한다.
        - 공동우승자는 ,로 구분하여 출력한다.