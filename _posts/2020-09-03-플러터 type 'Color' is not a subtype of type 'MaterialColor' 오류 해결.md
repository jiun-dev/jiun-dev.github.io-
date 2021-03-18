---
layout: post
title: 플러터 type 'Color' is not a subtype of type 'MaterialColor' 오류 해결
tags: [frontpage, blog, flutter]
image: "/images/posts/6.jpg"
cateories: ["flutter"]
---

# 플러터 type 'Color' is not a subtype of type 'MaterialColor' 오류 해결방법

##

    theme: ThemeData(
        primarySwatch: Colors.purple[200],
      ),

## 위코드를 사용시 type 'Color' is not a subtype of type 'MaterialColor' 라는 오류가 생겼다.

### 구글링한 결과 primarySwatch에선 사용할수 없는 컬러가 몇몇 있는것 같다.

##

    return MaterialApp(
      theme: ThemeData(
        primaryColor: Colors.purple[200],
      ),

### primarySwatch -> primaryColor 로 변경시 오류가 해결된다.
