---
layout: post
title: dart에서의 class 정리
tags: [frontpage, jekyll, blog, Til, dart]
image: "/images/posts/6.jpg"
cateories: ["TIL", "flutter"]
---

dart에서의 class 정리

flutter를 능숙하게 사용하기 위해 dart언어에서의 class를 제가 공부한 대로 정리해보겠습니다.

Car라는 class를 만들어 보겠습니다.

이 차에는 필요한 바퀴수와 차의 색상이 필요하다고 가정 해 보겠습니다.

```dart
class Car {
    String color;
    int tire;

    Car({this.color, this.tire});
}
```

Car라는 class를 생성한 후 색과 타이어 갯수를 넣어야 하도록 만들었습니다.

dart는 프로그램을 실행할 때 main함수를 먼저 찾도록 되어 있습니다.

밑에 main함수를 활용해서 newCar라는 차를 만들어 보겠습니다.

```dart
void main() {
  var newCar = Car(color: 'black', tire: 4);

  print('newCar tire number = ${newCar.tire}');
}
```

이 때 main 앞에 void를 적어 주셔도 됩니다. 색상이 까맣고 타이어 갯수가 4개인 차를 만들었습니다.
print를 활용하여 타이어의 갯수를 찍어보면 결과는

<em>newCar tire number = 4</em>

이렇게 찍히게 됩니다.
