# 3. Justify-content

justify-content는 main-axis로 어떻게 정렬할지 정하는 코드이다.

## 3.1. flex-start

부모 요소(컨테이너)에 display: flex, justify-content: flex-start 값을 주면 된다.

```css
.container {
    display: flex;
    justify-content: flex-start;
}
```

`**justify-content: flex-start;**`는 기본값으로 Flex 아이템들을 시작점을 기준으로 정렬한다. 기본값일 때, 기준이 되는 점은 왼쪽 축의 상단이다.

**`flex-direction: row;`**인 경우에는 가로(row=행)로 정렬 하며 왼쪽 상단이 기준점이 되어서 왼쪽 상단부터 차례대로 1, 2, 3번 순으로 아이템이 배치된다.

![image](https://user-images.githubusercontent.com/51049245/192127233-5e05e688-f79a-4682-88e9-7580322f6da2.png)

그렇지만 **`flex-direction: column;`**을 준 경우에는, 컨테이너의 상단이 기준점인 것은 같지만 flex 방향이 row(행)가 아닌 column(열)이기 때문에 세로(열)로 아이템이 배치된다.

![image](https://user-images.githubusercontent.com/51049245/192127239-062d4e32-6251-4ba6-b235-0581a539c2e7.png)

```css
.container {
	  display: flex;
	  justify-content: flex-start;
	  flex:-direction: column;
}
```

## 3.2. flex-end

부모 요소(컨테이너)에 display: flex;, justify-content: flex-end; 값을 주면 된다.

```css
.container {
    display: flex;
    justify-content: flex-end;
}
```

`**justify-content: flex-end;**`는 자식 요소(아이템)를 맨 끝점으로 배치하는데, 기본값(왼쪽 축)의 반대인 오른쪽 축의 상단이 기준이 된다.

**`flex-direction: row;`**인 경우일 때에는 row(행)로 정렬하기 때문에 자식 요소(아이템)인 1, 2, 3번의 아이템들이 오른쪽 축에 붙어 배치된다.

![image](https://user-images.githubusercontent.com/51049245/192127243-8ff30880-af02-4a67-93c4-8608189b6cc2.png)

**`flex-direction: column;`** 을 준 경우에는, flex 방향이 row(행)가 아닌 column(열)이 되기 때문에 세로(열)로 자식 요소(아이템)가 배치된다.

그리고 **`justify-content: flex-end;`** 의 경우, 자식 요소(아이템)를 배치하는 기준이 기본값(상단 축)의 반대인 하단 축이 되기 때문에 1, 2, 3번의 아이템이 세로로 정렬되어 하단에 붙어 배치된다.

![image](https://user-images.githubusercontent.com/51049245/192127245-07344965-4c7a-4bc9-abc8-875d215f722c.png)

```css
.container {
    display: flex;
    justify-content: flex-end;
    flex-direction: column;
}
```

## 3.3. center

`justify-content: center`를 준 경우, Flex-box 내의 요소들을 주축(main-axis)의 중앙을 기준으로 정렬한다. 즉, 요소들을 가운데 정렬해준다. 이때 요소의 간격은 균등 분할된다. 개별적으로 빈 공간을 제어하고 싶다면 해당 요소에 별도의 margin 값을 주어야 한다. `space-between`, `space-around` 역시 동일하다.

```css
.container {
    display: flex;
    justify-content: center;
}
```

![image](https://user-images.githubusercontent.com/51049245/192127247-d6cd2437-f1e0-4673-9437-92190eeb67c1.png)

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

![image](https://user-images.githubusercontent.com/51049245/192127251-b65b1beb-7205-409d-b3ff-3d37e15060c7.png)

```css
.container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}
```

## 3.4. space-between, space-around, space-evenly

다음으로 `space-between`, `space-around`, `space-evenly`의 비슷하면서도 다른 점들을 알아보자. 위 셋의 공통점은 자식 요소들을 메인 축으로 정렬하며, 일정한 간격을 준다는 것이다. between, around, evenly의 뜻은 차례로 ‘사이에’, ‘둘레에’, ‘균등하게’라는 뜻이다. 그럼 뜻을 생각하며 아래 그림으로 차이점을 확인해 보자.

![image](https://user-images.githubusercontent.com/51049245/192127254-60858e96-936b-4c00-aa87-4e38998cc019.png)

```css
.container {
    display: flex;
    justify-content: flex-start;
}
```

아무 정렬도 지정해주지 않았을 때의 기본값이다.

### 3.4.1. space-between

![image](https://user-images.githubusercontent.com/51049245/192127255-eb8ed8ea-9921-4bf4-a104-6d0f7cf23bcd.png)

```css
.container {
    display: flex;
    justify-content: space-between;
}
```

`justify-content: space-between;`을 주었을 때 자식 요소들의 ‘사이에' 같은 간격이 들어간 것을 볼 수 있다. 컨테이너의 패딩 값을 제외하면 컨테이너의 너비에 꽉 차게 배치된다.

### 3.4.2. space-around

![image](https://user-images.githubusercontent.com/51049245/192127260-8bc8a990-2413-40e1-89d3-88b5c6161e00.png)

```css
.container {
    display: flex;
    justify-content: space-around;
}
```

아이템의 ‘둘레에' 같은 간격이 들어간 것을 볼 수 있다. 아이템 사이에는 같은 간격이 2번씩 들어가게 되므로 양 끝 컨테이너 사이의 간격은 아이템 사이의 간격의 1/2이 된다.

### 3.4.3. space-evenly

![image](https://user-images.githubusercontent.com/51049245/192127261-5d8a50a9-2686-4a9b-8e75-d7a67b3a5b30.png)

```css
.container {
    display: flex;
    justify-content: space-evenly;
}
```

모든 간격이 ‘균등하게' 배치된 것을 볼 수 있다. space-around와 비슷하게 보이지만 양 끝의 간격과 자식 요소 사이의 간격이 같은 것을 확인할 수 있다.

## 3.5. 자주 사용하지 않는 속성들

### 3.5.1. justify-content : normal

값이 설정되지 않은 것처럼 기본 위치에 정렬한다. 기본값이므로 생략 할 수 있다.

![image](https://user-images.githubusercontent.com/51049245/192127265-896d0397-8529-4e7c-82c1-e5a4bf0af00a.png)

```css
.container {
    display: flex;
    justify-content: normal;
    align-items: flex-start;
}
```

### 3.5.2. justify-content : initial

기본값으로 정렬한다. justify-content의 기본값은 normal이므로 위의 justify-content:normal과 결과가 동일하게 나온다.

![image](https://user-images.githubusercontent.com/51049245/192127267-f82e4220-962c-4d09-a394-96543b4087b7.png)

```css
.container {
    display: flex;
    justify-content: initial;
    align-items: flex-start;
}
```

### 3.5.3. justify-content : inherit

상속되는 값에 따라 정렬한다. container에 class 명이 “wrap-container”인 부모 요소를 만들어 주었다. wrap-container의 justify-content:center 속성이 상속되어 자식 요소인 container의 justify-content도 center로 적용된다.


![image](https://user-images.githubusercontent.com/51049245/192127271-dc2d0231-2e6d-4812-98e4-7db6a466d2dd.png)

```css
.wrap-container {
    display: flex;
    justify-content: center;
}

.container {
    display: flex;
    justify-content: inherit;
}
```

```html
<body>
    <div class="wrap-container">
        <div class="container">
            <div class="item">1</div>
            <div class="item even">2</div>
            <div class="item">3</div>
        </div>
    </div>
</body>
```

### 3.5.4. justify-content : revert

상속된 속성으로부터 기본값으로 되돌린다. 특정 사이트만의 css 속성이 지정되어 있거나 사용자가 정의한 스타일이 적용된 속성을 부모 속성 또는 사용자 에이전트의 기본 스타일로 되돌린다. 사용자 에이전트란 브라우저마다 정해놓은 css 기본 규칙이다.

### 3.5.5. justify-content : unset

부모 요소로부터 상속받는 값이 있으면 inherit로 적용되고 상속되는 값이 없다면 initial 속성으로 정렬한다.

### 3.5.6. firefox에서만 지원하는 속성

`justify-content: revert-layer;`

이전 레이어에 지정된 스타일로 되돌릴 수 있다. revert와 달리 작성자 원본에 적용된 스타일을 제거하고 사용자 원본 또는 사용자 에이전트의 기본값으로 되돌린다.

`justify-content: safe;`

다른 정렬 속성과 함께 사용된다. 항목이 컨테이너를 오버플로 하여 데이터가 손실된다면 항목이 start 속성처럼 정렬된다.

`justify-content: unsafe;`

다른 정렬 속성과 함께 사용된다. 컨테이너의 상대적 크기와 관계없이, 데이터 손실을 일으키는 오버플로가 발생할 수 있는지와 관계없이 지정된 정렬 값이 적용됩니다.
