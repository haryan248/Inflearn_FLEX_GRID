## 9.2. order

`order` 속성은 아이템 요소들의 순서를 결정하는 속성이다. 기본적으로 `flex`는 작성한 순서대로 나열되지만, `order` 속성을 사용하여 아이템들의 순서를 변경할 수 있다.

**order의 특징**

-   기본값은 0이며, 음수와 양수를 사용할 수 있다. 값이 작을수록 우선순위가 적용되어 `음수 → 0 → 양수` 순서로 표시된다.
-   `flex-direction` 속성의 방향값(row, row-reverse, column, column-reverse)을 기준으로 낮은 숫자를 먼저 배치한다.
-   HTML 구조와 상관없이 순서를 시각적으로 변경할 수 있지만, HTML 자체의 구조를 바꾸는 것은 아니다. 따라서 스크린리더가 읽을 때는 `order`값이 적용되지 않고 HTML 마크업 순서대로 읽힌다.

아래는 `flex-direction: row;` 와 `flex-direction: column;`에서 `order` 값을 적용하지 않았을 때와 적용했을 때의 모습이다.

`flex-direction: row;`

-   order 값을 적용하지 않은 모습

![2022-05-13 22 14 06.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/b52d5154-289b-4a6e-84ef-7dbaf6d23a8d/2022-05-13_22_14_06.png)

-   order값을 적용한 모습

![2022-05-13 22 15 44.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/a3ede0ea-3ebd-4c19-9f5d-52b44f3d97f5/2022-05-13_22_15_44.png)

```css
.item:nth-child(1) {
    order: 2;
}
.item:nth-child(2) {
    order: 3;
}
.item:nth-child(3) {
    order: 1;
}
```

`flex-direction: column;`

-   order 값을 적용하지 않은 모습

![2022-05-13 22 18 40.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/6c513448-1be7-4abf-b52a-cad28666f87b/2022-05-13_22_18_40.png)

-   order값을 적용한 모습

![2022-05-13 22 19 11.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/625c97dd-d4a5-46aa-b855-18de247a00f9/2022-05-13_22_19_11.png)

**order의 사용 예시**

1. 날짜와 제목, 내용이 있는 카드 디자인을 만든다고 가정하자. 아래의 이미지처럼 날짜가 제목보다 먼저 위치하게 할 때, 기본 순서로 배치한다면 스크린 리더는 날짜, 제목, 내용 순으로 읽을 것이다. 하지만 사용자는 가장 중요한 제목을 먼저 읽은 후 날짜를 읽기를 선호한다. 이럴 경우, 날짜에 `order:-1`을 주어 시각적 순서만 바꿔서 스크린 리더가 읽는 순서를 변경하지 않도록 할 수 있다.

![Group 1-1.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/6973191e-6b16-40db-b093-4a45e182f7a0/Group_1-1.png)

1. 아래와 같은 경우에도 order 속성을 사용할 수 있다.

이미 만들어진 모듈을 사용하여 웹을 구성한다면 초기에는 아래와 같은 배치가 된다. 마크업 순서가 header부터 footer까지 차례대로 되어있으므로, 각 요소의 크기를 조정해주어도 기본적으로 순서는 바뀌지 않는다.

![flex_기타01.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/8ed0406d-7d9a-4a2c-af48-dbb34ab4282e/flex_기타01.png)

-   **order 속성을 주지 않았을 때**

요소들의 크기를 조정해주었지만, 마크업 순서대로 배치되기 때문에 order 속성을 주지 않는다면 기본적인 순서를 변경할 수 없다.

![flex_기타02.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/c27099bd-36f3-491d-b5fa-9f1ee732932c/flex_기타02.png)

-   **order 속성을 주었을 때**

현재 main 부분을 가운데로 옮기려고 한다. 그러므로 aside-a, main, aside-b 요소에 각각 order를 주면 배치가 되지만, 기본적으로 order 값을 1이라도 주게 되면, order 값이 없는 속성이 더 우선시되기 때문에 마크업상 아래에 있는 footer 부분에도 order 값을 주어야 한다. 즉 우리가 원하는 순서대로 각 요소에 order를 1, 2, 3, 4를 주게 되면, 우리가 원하는 레이아웃을 만들 수 있다.

![flex_기타03.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/69840b7c-c28f-446d-bec4-80337687f21c/flex_기타03.png)

```css
.main {
    width: 60%;
    order: 2;
}

.aside {
    width: 20%;
}

.aside.aside-a {
    order: 1;
}

.aside.aside-b {
    order: 3;
}

.footer {
    order: 4;
}
```

## 9.3. z-index

flex에서도 z-index 속성을 사용할 수 있다. 어떤 요소에 z-index의 값이 1이라도 주어진다면 마치 다른 요소를 덮어 씌우는 것과 같은 모습을 표현할 수 있다.

![z-index.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/3a909e77-d006-4cee-9d4b-6c4501101101/z-index.png)

```css
.main {
    width: calc(60% - 16px);
    order: 2;
    z-index: 1;
    transform: scale(1.5);
    opacity: 0.8;
}
```
