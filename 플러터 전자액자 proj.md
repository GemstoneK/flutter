# Image Carousel

## 프로젝트 목표

1. 이미지 사용법
2. PageView 사용법
3. Timer 사용법
4. map() 함수 실전
5. initState(), dispose() 실전
6. 상태바 테마 변경

## Timer 이론

Timer는 지정한 시간이 지난 뒤 한번 또는 주기적으로 무언가를 실행 할 수 있게 해준다.

Timer는 플러터에 기본 제공되는 dart:async 패키지를 불러오면 사용 할 수 있다.

```
import 'dart.async';

void main(){
print('main 함수 실행');

int number = 0;

Timer(
  Duration(기간 입력),
  (){실행할 함수 입력},
);

Timer.periodic(
  Duration(seconds:1),
  (Timer timer){ // timer.cancel()을 사용하기 위해서 Timer 인스턴스를 매개변수로 받는다.
    number ++;
    print('1초 뒤에 실행한다!');

    if(number == 5){
      timer.cancel();
      }
    }
  )
}
```

## 이미지 등록

이미지를 에셋 폴더에 넣은 후 Pub get을 누른 후 Image.asset('이미지 경로')

## PageView 위젯

여러개의 위젯을 슬라이드로 사용할 수 있다.

## 이미지 확대

이미지 파라미터에 fit : BoxFit.cover을 사용한다.
