# DateTime

날짜를 표시하는 클래스

년, 월, 일, 시, 분, 초, 밀리 초, 마이크로 초에 해당되는 값들을 순서대로 입력하면 된다.

년도만 필수 입력이고, 나머지는 옵셔널이다.

옵셔널 값을 입력하지 않을 경우 월, 일은 기본값이 1로 입력되고 나머지는 0이 입력된다.

DataTime.utc

coordinate universal time의 약자

# Duration

기간을 표시하는 클래스

날, 시, 분, 초, 밀리초, 마이크로 초를 Named Parameter로 입력할 수 있다.

값을 입력하지 않으면 모든 값들은 0으로 초기화가 된다.

## 메소드

.add

.substract

.isAfter

.isBefore

.isAtSameMomentAs 전부 똑같은가?

.toUtc

.toLocal
