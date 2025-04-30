# 쓸데없이 이쁜 랜덤 숫자 생성기

난수 생성

하나 이상의 페이지 사용

Slider 사용

복잡한 map() 함수 사용

# 중간 코드
```
import 'package:flutter/material.dart';
import 'package:random_number_generator/constant/color.dart';
import 'dart:math'; // 난수 생성을 위해 dart:math를 import 해준다.

class HomeScreen extends StatefulWidget {
  const HomeScreen({super.key});

  @override
  State<HomeScreen> createState() => _HomeScreenState();
}

class _HomeScreenState extends State<HomeScreen> {
  List<int> numbers = [ // 난수 리스트
    123, 456, 789];
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: primaryColor, // constant 디렉토리의 color.dart 에서 primaryColor 참조
      body: SafeArea(
        child: Padding( // 패딩
          padding: EdgeInsets.symmetric(
            horizontal: 16.0
          ),
          child: Column(
            crossAxisAlignment: CrossAxisAlignment.stretch, // 위젯을 화면 끝까지 가로로 늘려준다.
            children: [
              // 제목과 아이콘 버튼이 있는 곳
              _Header(),
              // 숫자가 있는 곳
              _Body(numbers: numbers),
              // 버튼이 있는 곳
              _Footer(onPressed: generateRandomNumber)
            ],
          ),
        ),
      ),
    );
  }

// 난수 생성 함수
  generateRandomNumber(){
    final rand = Random(); // 난수생성기 인스턴스

    final List<int> newNumbers = []; // 난수를 담을 리스트

// 난수가 3개 들어오면 중단
    while(newNumbers.length < 3){
      final randomNumber = rand.nextInt(1000);

      newNumbers.add(randomNumber); // 난수 리스트에 추가
    }

    setState(() {
      numbers = newNumbers; // 난수리스트
    });
  }
}


class _Header extends StatelessWidget {
  const _Header({super.key});

  @override
  Widget build(BuildContext context) {
    return Row(
        mainAxisAlignment: MainAxisAlignment.spaceBetween, // 동일한 간격으로 떨어뜨리기
        children: [
          Text('랜덤숫자 생성기',
            style: TextStyle(
                color: Colors.white,
                fontSize: 30.0,
                fontWeight: FontWeight.w700
            ),),
          IconButton(color : redColor,
              onPressed: (){}, icon: Icon(Icons.settings))
        ],
      );
  }
}

class _Body extends StatelessWidget {
  final List<int> numbers; // 난수 리스트
  const _Body({required this.numbers, super.key});

  @override
  Widget build(BuildContext context) {
    return Expanded( // 빈 공간은 Body가 다먹음
      child: Column(
        mainAxisAlignment: MainAxisAlignment.center, // 세로축으로 가운데 정렬
        children: numbers.map((e) => e.toString().split('')).toList().map((e) =>Row(
          children: e.map((e) => Image.asset('asset/img/$e.png',
          width: 50.0,
          height: 70.0,),

          ).toList(),
        )).toList()
      )
      );
  }
}

class _Footer extends StatelessWidget {
  final VoidCallback onPressed; // onPressed 함수 받기

  const _Footer({required this.onPressed, super.key});

  @override
  Widget build(BuildContext context) {
    return ElevatedButton(onPressed: onPressed,
        style: ElevatedButton.styleFrom( // 버튼의 스타일 설정 방법
            backgroundColor: redColor,
            foregroundColor: Colors.white),
        child: Text('생성하기!'));
  }
}

```

## 버튼 스타일 설정

stlyeFrom 메소드를 사용한다.

```
ElevatedButton(onPressed: onPressed,
        style: ElevatedButton.styleFrom( // 버튼의 스타일 설정 방법
            backgroundColor: redColor,
            foregroundColor: Colors.white),
        child: Text('생성하기!'));
```


## 큐와 스택

### 스택

LIFO Last in First out


### 큐

FIFO First in First out

### 컨텍스트

컨텍스트는 위젯트리에 대한 정보를 들고 있다.

## 화면 전환하기

화면을 전환할 때는 Navigator 함수를 사용해야하는데, Navigator 함수는 context를 필요로 한다.

Stateless 위젯에서는 context가 전역으로 사용이 불가능하기 때문에 매개변수로 넘겨줘야 하지만, Stateful 위젯은 전역적으로 사용이 가능하다.

또 화면을 전환하기 위해서는 MaterialPageRoute 클래스의 도움을 받아야한다.

Navigator.of(context).push(MaterialPageRoute(builder: (BuildContext context){return 페이지()}))

Navigator.of(context).pop()

