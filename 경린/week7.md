mber Diff line change
@@ -0,0 +1,158 @@

## 12.4 리액트 Hooks 패턴

Hook은 함수 컴포넌트에서 상태 관리와 생명주기 기능(lifecycle features)을 연동(hook into)할 수 있게 해주는 함수
여러 컴포넌트 간 동일한 상태 관련 로직 재사용 가능

### 12.4.1 클래스 컴포넌트

hook이전엔 컴포넌트에 상태, 라이프사이클 메서드를 추가하기 위해 클래스 컴포넌트를 써야했음

-   클래스 컴포넌트 특징
    > 생성자 함수 안의 상태 <br/>
    > 라이프 사이클 매서드 (componentDidMount, componentwillUnmount) <br/>
    > 커스텀 메서드

## 12.5 상태 Hook

useState 메서드에서 두 가지 값 추출 가능

1. 현재 상태 값, 업데이트 메서드

### 12.5.1 이펙트 Hook

useEffect 를 사용하면 컴포넌트 라이프사이클에 접근 가능
(componentDidMount,componentDidUpdate, componentwillUnmount)
를 하나로 합쳐 사용가능

### 12.5.2 커스텀 Hook

커스텀 훅은 리액트 애플리케이션의 함수 컴포넌트 내 특정 로직을 분리한 함수로, **재사용 가능**한 함수. 커스텀 훅은 순수 자바스크립트로 코드를 작성할 때 특정 로직을 함수로 분리하고 재사용해 불필요한 코드 반복을 줄이는 것과 비슷한 맥락으로 사용

커스텀 훅을 사용하는 이유는 다음과 같다.

-   여러 함수 컴포넌트에서 공통으로 사용되는 특정 컴포넌트 로직을 분리해 필요한 컴포넌트에서 호출하기 위해 사용이를 통해 반복되는 코드를 줄일 수 있음
-   리액트 프로젝트에서 특정 기능을 구현하기 위해 필요에 따라 라이브러리를 도입하기도 함. 하지만 원하는 기능을 구현하기에 적합한 라이브러리가 없는 경우 커스텀 훅을 직접 만들어 사용할 수 있음

### 12.5.4 Hook 장단점

-   장점

1. **재사용성**

    커스텀 훅을 사용하면 여러 함수 컴포넌트에서 중복되는 로직을 공유 가능. 즉, 로직의 재사용성이 높음

2. **가독성**

    커스텀 훅을 사용하면 커스텀 훅의 내부 로직을 정확히 몰라도 어떤 값이 들어가서 어떤 결과값이 반환되는지가 명확하다는 장점

### 12.5.5 Hook vs Class

훅을 쓰자아

## 12.6 정적 가져오기

-   import키워드로 타 모듈에서 내보낸 코드를 정적으로 가져와
    초기 번들에 추가

-   각 모듈은 자바스크립트 엔진이 해당 모듈을 import하는 코드에 도달하는 즉시 실행됨
-   정적으로 가져왔기 때문에 웹팩은 초기 번들에 포함시킴
-   이 때 애플리케이션 로딩 속도에 영향을 미침
    왜냐? 렌더링 전 모든 모듈을 로드하고 파싱해야하기 때문에
    한번에 정적으로 가져오지 말고 동적으로 상호작용 이후 가져오면 됨

## 12.7 동적 가져오기

### 12.7.2 상호작용 시 가져오기

-   사용자 상호작용을 통해 컴포넌트를 가져옴

> Suspense컴포넌트는 동적으로 로드되는 컴포넌트를 감싸서 클릭 이벤트 발생 시 렌더링을 시작함

### 12.7.3 화면에 보이는 순간 가져오기

-   lazy-loading

## 12.8 코드 스플리팅

-   적절한 시기에 정적 및 동적 임포트 모두 가능하도록 코드를 최적으로 스플리팅/번들링 해야함

### 12.8.1 경로 기반 분할

-   특정 경로에 대한 리소스만 요청



## 이야기거리
- 팀에서 실제 서비스 런칭하고 스와이프를 넘겨줄 때나 스크롤을 내릴 때, 리스트 가상화로 최적화했던 경험이 있어요. 
+ (즐찾이 1000명? 까지 가능하고 api에서 이미지를 전부 다 내려주는데 즐찾 많은 계정에서 profile img 에 lasy loading 안넣어서 로딩 느린 것 때문에 크게 혼남) 실제 서비스에서 문제가 생겨 개선해본 적이 있으신가요?
