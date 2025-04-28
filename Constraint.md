# Constraint

제약 위젯의 위치와 사이즈와 크기에 대한 제약

Singlepass

한번만 계산한다.

Constraints go down

제약은 위에서부터 아래로 내려간다.

부모에서 자식으로 전가한다.

Sizes go up

크기는 위로 올라간다.

자식부터 부모로 올라간다.

Parents Sets Position

부모가 위치를 정한다.



## Constraints

크기의 제약을 말한다.

1) Max Height

2) Min Height

3) Max Width

4) Min Width


## 제한사항

자식 위젯은 부모 위젯이 제한하고 있는 Constraints 내부에서만 크기를 가져갈 수 있다.

위젯의 위치는 부모 위젯이 지정하기 때문에 위젯은 자신이 정확히 어디에 위치될지 알 수 없다. (플러터에서 x, y 좌표로 위젯을 배치하지 않는 이유)

Column이랑, Row, Center는 지정을 하지만, Container나, IconBox 같은 경우는 자식 위젯의 위치를 신경쓰지 않아서, 자식위젯의 크기가 무시된다.

자식 위젯이 어디에 정렬돼야하는지 정확히 알 수 없는 경우에는 자식 위젯의 크기가 무시 될 수 있다.
