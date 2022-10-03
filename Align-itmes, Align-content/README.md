# 4. Align-items, Align-content

## 4.1. align-items

align의 사전적 정의는 ‘일직선으로 맞추다’이다. 즉, flex에서 align이란 축의 수직 방향 정렬을 의미하며, 부모요소(컨테이너) 안에서 교차 축에 따라 자식요소(아이템)가 정렬되는 속성이다.

**속성**

-   **stretch**

align-items의 기본값이다. 부모요소(컨테이너)의 높이만큼 자식요소(아이템) 높이가 같이 늘어난다.

![alignitems-stretch.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/7393e971-4ee2-4f44-92ad-f31169ae6040/alignitems-stretch.png)

```css
.container {
    display: flex;
    align-items: stretch;
}
```

-   **flex-start**

자식요소(아이템)는 교차 축 시작점에서 정렬된다. 기본적으로 가로축은 수직을 의미하며, 자식요소(아이템)는 상단에서 수직으로 정렬된다.

![alignitems-flexstart.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e104da32-1572-476b-ae5f-62cef7dd954d/alignitems-flexstart.png)

```css
.container {
    display: flex;
    align-items: flex-start;
}
```

-   **flex-end**

자식요소(아이템)는 교차 축 끝점에서 정렬된다. 기본적으로 가로축은 수직을 의미하며, 자식요소(아이템)는 하단에서 수직으로 정렬된다.

![alignitems-flex-end.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/a1838b3e-d3d2-4c95-9319-6fd68bd815f6/alignitems-flex-end.png)

```css
.container {
    display: flex;
    align-items: flex-end;
}
```

-   **center**

자식요소(아이템)는 교차 축 중앙으로 정렬된다.

![alignitems-center.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/80e7cc6d-12b6-4cae-803c-3c31988c6bdc/alignitems-center.png)

```css
.container {
    display: flex;
    align-items: center;
}
```

-   **baseline**

자식요소(아이템)는 교차 축의 기준선에 정렬이 된다. 텍스트의 기준선이 수평선을 따라 아이템이 정렬된다.

![alignitems-baseline.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/f355f9bd-c541-4779-abff-f0c0db66824e/alignitems-baseline.png)

```css
.container {
    display: flex;
    align-items: baseline;
}
```

**3. align-self와 다른 점은?**

align-items는 부모 요소(컨테이너) 내에 있는 자식 요소를 대상으로 적용하는 반면에, align-self는 부모 요소(컨테이너) 안에서 특정 아이템만 교차 축으로 정렬된다. 즉, 특정 아이템의 정렬을 따로 하고 싶다면 이 속성을 사용하면 된다.

![align-self와 비교.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/4899f71e-72bf-47eb-b20c-8dc00c062387/align-self와_비교.png)

```css
.container {
    display: flex;
    align-items: flex-start;
}

.third_item {
    align-self: center;
}
```

플렉스 박스 컨테이너에 `align-items : flex-start`를 적용하고 ‘third_item’ 이름을 가진 특정 아이템만 `align-self : center`를 적용했다. 위와 같이 3번 아이템만 중앙정렬 속성이 적용되는 것을 볼 수 있다.

## 4.2. align-content

`align-items`는 한 줄을 기준으로 정렬하지만, align-content는 `flex-wrap : wrap;` 이 설정된 경우 두 줄부터 기준으로 정렬한다. 아래 예시를 보면, 더 쉽게 알 수 있다.

![captures_chrome-capture-2022-4-21 (1).png](<https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e97342dd-71a6-4aa2-9cf3-5eb7376b2b9f/captures_chrome-capture-2022-4-21_(1).png>)

![captures_chrome-capture-2022-4-21 (2).png](<https://s3-us-west-2.amazonaws.com/secure.notion-static.com/182176c2-a605-4385-b8ca-ef9bd9139e38/captures_chrome-capture-2022-4-21_(2).png>)

좌측은 `align-items : center;` , 우측은 `align-content : center;` 로 정렬한 결과화면이다. align-items는 아이템 한 줄마다 속성이 적용되었기 때문에 두 줄 사이에 간격이 생겨 정렬된 것을 볼 수 있다. 반면에, align-content는 두 줄 이상의 아이템을 수직축 방향으로 라인 자체를 정렬하기 때문에 두 줄 사이에 간격이 생기지 않은 것을 볼 수 있다.

**속성**

-   **stretch**

부모요소(컨테이너)의 높이만큼 자식요소(아이템) 높이가 같이 늘어난다.

![align-content-stretch.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/fbce8b90-0774-4731-81ba-11b175ba17e6/align-content-stretch.png)

```css
.container {
    display: flex;
    flex-wrap: wrap;
    align-content: stretch;
}
```

-   **flex-start**

부모요소(컨테이너)의 최상단에서부터 정렬을 시작한다.

![align-content-flex-start.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/8683af11-717d-4a51-8abd-7673803acd8d/align-content-flex-start.png)

```css
.container {
    display: flex;
    flex-wrap: wrap;
    align-content: flex-start;
}
```

-   **flex-end**

부모요소(컨테이너)의 최하단에서부터 정렬을 시작한다.

![align-content-flex-end.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/180f4fc0-1951-433e-8d2f-b9102ae58b91/align-content-flex-end.png)

```css
.container {
    display: flex;
    flex-wrap: wrap;
    align-content: flex-end;
}
```

-   **center**

부모요소(컨테이너) 교차 축의 중앙에 정렬합니다.

![align-content-center.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/21dca6e7-32a1-4c77-b3ac-206602ee1600/align-content-center.png)

```css
.container {
    display: flex;
    flex-wrap: wrap;
    align-content: center;
}
```

-   **space-between**

부모요소(컨테이너) 교차 축의 양 끝(시작점, 종료점)에 맞춰 아이템 간에 일정한 간격을 두고 정렬한다.

![align-content-space-between.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/429d7796-a9cc-4517-b5cc-50e37727d6c5/align-content-space-between.png)

```css
.container {
    display: flex;
    flex-wrap: wrap;
    align-content: space-between;
}
```

-   **space-around**

space-between과 마찬가지로 부모요소(컨테이너) 교차 축의 양 끝(시작점, 종료점)에 맞춰 아이템 간에 일정한 간격을 두고 정렬한다. 이때 첫 아이템 앞 여백과 마지막 아이템 뒤 여백은 각 아이템 간 거리의 절반 크기를 차지하여 정렬된다.

![align-content-space-around.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/c03605e1-7345-485b-99d8-065f28c67ca7/align-content-space-around.png)

```css
.container {
    display: flex;
    flex-wrap: wrap;
    align-content: space-around;
}
```

-   **space-evenly**

space-between과 마찬가지로 부모 요소(컨테이너) 교차 축의 양 끝(시작점, 종료점)에 맞춰 아이템 간에 일정한 간격을 두고 정렬한다. 이때 아이템 간의 거리, 첫 아이템 앞 여백과 마지막 아이템 뒤 여백의 크기가 모두 동일하게 정렬된다. 본 속성은 IE, Edge에서는 지원되지 않는다.

![align-content-space-evenly.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/740b02a8-2cd0-4563-874f-61925ff11095/align-content-space-evenly.png)

```css
.container {
    display: flex;
    flex-wrap: wrap;
    align-content: space-evenly;
}
```
