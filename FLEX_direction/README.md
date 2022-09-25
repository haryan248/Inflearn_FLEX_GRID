# 2. Flex-direction

`flex-direction` 이란 flex container 내의 item들의 정렬 방향을 결정하는 속성이다. `flex-direction`은 자식요소(아이템)의 부모요소인 (컨테이너)에 적용하여 사용하며 종류는 `row`, `row-reverse`, `column`, `column-reverse` 네 가지가 있다.

## 2.1. flex-direction : row

왼쪽에서 오른쪽으로 글씨가 써지는 **행 방향 정렬**이며, `flex-direction`을 따로 설정하지 않으면 초깃값으로 설정된다. 

![image](https://user-images.githubusercontent.com/51049245/192127217-7dd61120-17ae-4949-aa82-9fd1ffc1c60a.png)

```css
.container {
    display: flex;
    flex-direction: row;
}
```

## 2.2. flex-direction : row-reverse

`row`와 동일하게 보여지지만 시작점과 끝점이 반대로 위치한다.

![image](https://user-images.githubusercontent.com/51049245/192127219-757ec8ec-6770-40b4-a247-8d6f143a2003.png)

```css
.container {
    display: flex;
    flex-direction: row-reverse;
}
```

컨테이너 내에 위치한 아이템들을 유연하게 정렬 할 수 있으며, 역순으로 정렬한다. 컨테이너에게 `display: flex` 속성을 부여하지 않으면 아이템은 유연하게 움직이지 않는다.

## 2.3. flex-direction : column

Flex 내 box들을 수직으로 정렬한다. 컨테이너 내부의 요소들이 아이템이 아닌 경우 해당 속성의 값은 적용되지 않는다. `flex-direction : column;`일 때 주축은 세로 방향이 되고, 교차 축은 가로 방향이 된다. 아이템을 추가하는 경우 마크업 순서에 맞게 위에서 아래로 흐르듯이 정렬된다.

![image](https://user-images.githubusercontent.com/51049245/192127220-0190f5ca-c09c-4fdf-8666-901571168210.png)

```css
.container{
	  display : flex;
	  flex-direction : column;	
}
```

## 2.4. flex-direction : column-reverse

`column` 과 동일하게 보여지지만 시작 점과 끝 점이 반대로 위치한다.

![image](https://user-images.githubusercontent.com/51049245/192127226-654c2856-ebcb-4910-b76f-100e03342a3d.png)

```css
.container{
	  display : flex;
	  flex-direction : column-reverse;	
}
```
