---
layout: post
title: 플러터 에러 This function has a return type of 'Widget', but doesn't end with a return statement 해결하기
tags: [frontpage, blog, flutter]
image: "/images/posts/6.jpg"
cateories: ["flutter"]
---

## This function has a return type of 'Widget', but doesn't end with a return statement 를 해석해보면

## 이 함수는 위젯을 반환해야 하지만 아무것도 반환하지 않고 있다는 오류입니다.

##

itemBuilder: (ctx, i) {
Container(
child: Column(
children: [
Image(
image: NetworkImage(posts[i].postImage),
),
],
),
);
},

## 위 코드에서 itemBuilder 위젯은 리턴이 필요한데 리턴이 없습니다.

##

itemBuilder: (ctx, i) {
return Container(
child: Column(
children: [
Image(
image: NetworkImage(posts[i].postImage),
),
],
),
);
},

## 이런 식으로 컨테이너에 리턴을 붙여준다면 오류가 해결됩니다.
