## 1.1. Flex의 특징

Flex는 부모와 자식 태그가 필요하고, 부모 요소(`flex-container`)와 자식 요소(`flex-item`)에 적용하는 속성이 구분되어 있다.

이때 속성의 영향은 **컨테이너의 직계자식까지만 영향**을 준다는 특징이 있으니 주의해야 한다. 

flex-container에는 정렬 방식과 item의 배치 흐름을 정의하고, flex-item에는 크기, 속성, 순서를 정의한다. 

- `flex-container`의 속성 : **flex-direction, flex-wrap, justify-content, align-items, align-content** 등
- `flex-item`의 속성 : **flex, flex-grow, flex-shrink, flex-basis, align-self, order, z-index** 등

어떠한 속성을 적용해야 하는지 헷갈리는 경우, 컨테이너에 flex 속성을 적용한 뒤 크롬 개발자 도구의 스타일 탭을 확인하면 좋다. 주요한 속성 다섯 가지를 GUI 기능으로 제공하여 적용된 모습을 확인해볼 수 있기 때문이다.

![image](https://user-images.githubusercontent.com/51049245/192127184-b6191f2b-b7a4-4ba5-b5a5-c64676ca6ff2.png)


## 1.2. axis와 cross-axis

### 1.2.1. axis란?

axis로 자식 요소의 정렬 방향을 제어할 수 있다. 행방향, 열방향으로 각각 반대 방향도 지원한다.

![1.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/2364a6ba-e991-4e6c-a961-eea1ee9f17b3/1.png)

### 1.2.2. 주축과 교차축

- **Main Axis**

Flex의 주축이 되는 main axis의 방향은 `flex-direction` 이라는 속성에 의해 결정된다. 이는 다음과 같이 **네 가지의 경우**가 있다.

`flex-direction` 속성에 `row-reverse` 또는 `column-reverse` 값을 사용하면 DOM 구조와 시각적 표현에 차이가 발생하여 스크린 리더로 접근하는 사용자에게 잘못된 정보를 전달 할 가능성이 있으니 주의를 요한다.

1. `flex-direction: row` : `flex-direction` 의 기본값으로 아이템들이 행 방향, 가로로 배치된다. 
2. `flex-direction: row-reverse` : 아이템들이 역순으로 가로로 배치된다.  
3. `flex-direction: column` : 아이템들이 열 방향으로, 세로로 배치된다. 
4. `flex-direction: column-reverse` : 아이템들이 역순으로 세로로 배치된다. 

![flex-direction:row](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/1202e917-4e9f-46d0-b08d-81f8dc11d779/Untitled.png)

flex-direction:row

![flex-direction:column](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/83563037-6b0c-416a-a49e-a9ff7e2795e0/Untitled.png)

flex-direction:column

- **Cross Axis**

Cross axis는 Main axis 방향의 수직 방향이다. Main axis가 `flex-direction` 에 의해 결정되었다면, Cross axis는 main axis 방향에 따라 결정이 된다.
