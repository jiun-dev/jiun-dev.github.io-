---
layout: post
title: Dart에서 Python isInstance사용하기
tags: [frontpage, jekyll, blog, Til, dart]
image: "/images/posts/6.jpg"
cateories: ["TIL", "flutter", "dart"]
---

Dart에서 Python isInstance사용하기

파이썬을 공부하던 도중 isInstance라는 타입비교를 다트에서는 사용할수 없을까 하는 의문을 가지고 알아보게 되었습니다.

다트에선 is, !is 로 사용할 수 있습니다.

```dart

class Garen  {
  Garen() {
    name = '가렌';
    hp = 40;
    damage = 5;
    speed = 5;
  }

  justice() {
    if (hp > 10) {
      hp -= 10;
      print("$name : 심판을 사용합니다. (HP 10 감소)");
    } else {
      print("$name : 체력이 부족하여 심판을 사용할 수 없습니다.");
    }
  }
}

class Katarina  {
  Tank() {
    name = '카타리나';
    hp = 100;
    damage = 10;
    speed = 3;
  }

  bool skillReady = true;

  blade() {
    if (skillReady == false) {
      seizeDeveloped = true;
      print('스킬을 사용합니다.');
    }
  }
}

```

카타리나와 가렌이라는 두 유닛을 클래스를 통해 정의했고

각각 justice와 blade라는 기술이 있고 두 기술에 조건이 걸려있습니다.

```dart

void main() {
  gameStart();

  var garen = Garen();
  var katarina = Katarina();

  List attackUnits = [];
  attackUnits.add(garen);
  attackUnits.add(katarina);

  for (Unit unit in attackUnits) {
    if (unit is Garen) {
      unit.justice();
    } else if (unit is Katarina) {
      unit.blade();
    }
  }

  gameOver();
}

```

변수를 선언해서 가렌과 카타리나를 만들어줍니다.

이후 attackUnits이라는 리스트를 만들고 리스트에 가렌과 카타리나를 넣어 관리해줍니다.

for문을 이용하여 unit이 가렌인 경우엔 justice를 실행

katarina인 경우엔 blade를 실행하도록 해주었습니다.

이처럼 파이썬의 isinstance를 다트에선 is를 활용해줄 수 있습니다.
