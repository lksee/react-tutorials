
## 1. Visual Studio Code 활용법
- 자동 완성 옵션 켜기: Make sure the 'TypeScript and JavaScript Language Features' extension is enabled.
- 자동 포맷팅: Prettier extension 활용.

## 2. React
리액트(React)는 일반 자바스크립트와 비교했을 때 다음과 같은 몇 가지 장점을 가지고 있습니다.

1. 컴포넌트 기반: 리액트는 컴포넌트 기반 아키텍처를 사용합니다. 이는 애플리케이션을 독립적이고 재사용 가능한 작은 컴포넌트로 나눌 수 있음을 의미합니다. 이로 인해 코드의 가독성과 유지보수성이 향상되며, 개발 작업을 단순화하고 생산성을 높일 수 있습니다.

2. 가상 DOM (Virtual DOM): 리액트는 가상 DOM을 사용하여 효율적인 UI 업데이트를 수행합니다. 가상 DOM은 실제 DOM과 동기화되는 가벼운 복사본으로, 변경된 부분만 실제 DOM에 적용하여 성능을 향상시킵니다. 이로써 애플리케이션의 성능이 향상되며, 빠른 렌더링과 반응성을 제공할 수 있습니다.

3. 단방향 데이터 흐름: 리액트는 단방향 데이터 흐름을 강조합니다. 애플리케이션의 데이터는 항상 위에서 아래로 흐르며, 컴포넌트 간의 데이터 전달이 명확해집니다. 이로 인해 데이터 관리가 용이해지고, 예측 가능한 상태 관리가 가능해집니다.

4. 재사용 가능한 컴포넌트: 리액트는 컴포넌트 중심적인 개발 방식을 채택하므로, 컴포넌트의 재사용성이 높습니다. 재사용 가능한 컴포넌트를 작성하면 코드를 최적화하고 개발 시간을 단축시킬 수 있습니다.

5. 활발한 생태계: 리액트는 매우 활발하고 거대한 커뮤니티와 생태계를 갖추고 있습니다. 다양한 개발자들이 리액트를 사용하며 도움을 주고받고, 컴포넌트 라이브러리, 개발 도구, 플러그인 등 다양한 리액트 관련 자원들을 활용할 수 있습니다.

6. JSX 문법: 리액트는 JSX(JavaScript XML)라는 문법을 도입하여 UI 컴포넌트를 작성할 수 있습니다. JSX는 자바스크립트를 확장한 문법으로, XML과 유사한 구조를 가지며, 컴포넌트의 가독성을 높여줍니다.

7. 생산성과 유지보수성: 리액트는 간결하고 명료한 문법을 제공하여 개발자의 생산성을 높여줍니다. 또한 컴포넌트 기반 아키텍처와 단방향 데이터 흐름을 통해 코드 유지보수가 용이해지고, 팀 프로젝트에서 협업을 간소화할 수 있습니다.


### 2.1. React.js 시작하기
- [ ] React.js에 대해서 설명할 수 있다.
- [ ] react-dom에 대해서 설명할 수 있다.
- [ ] 


### 2.1. React.js를 통해 하는 아주 기초적인 작업
1. 요소(Element)를 생성
2. 요소를 렌더(render), 즉 위에서 만든 요소를 HTML 문서에 위치한 특정 요소에 포함되도록 업데이트!

## 2.2. 용어 정리
- render: 데이터를 가지고 어떤 형식으로 출력할지 결정하고, 그 결과물을 사용자에게 제공하는 과정을 의미합니다. 보통은 서버에서 클라이언트로 보내는 HTML, CSS, JavaScript와 같은 웹 페이지의 요소들을 생성하거나 업데이트하는 작업을 가리키는 용어로 사용됩니다.


## 3. JSX
### 3.1. JSX를 사용하지 않고 요소를 만드는 경우
```js
// 첫 번째 인수(component): Tag name
// 두 번째 인수(props): 맵 형태로 작성하며 attribute 혹은 event(따옴표 없이 작성)를 작성한다.
// 세 번째 인수(children): innerHTML: 요소를 포함시킬 수도(배열 형태로 작성), 텍스트일 수도 있다.
/* 
예를 들어 다음과 같은 button 요소를 만들고자 하는 경우를 생각해보자.
1. id는 "super-button"
2. onClick 이벤트를 갖는데, console.log("I'm clicked")를 동작하는 콜백함수를 동작
3. 버튼의 내용은 "Click me!"
 */
const Button = React.createElement("button", {
    "id": "super-button",
    onClick: () => console.log("I'm clicked"),
}, "Click me!");
```

### 3.2. JSX 사용하기
- javascript를 확장한 것으로 요소를 만들 때 활용한다.
- 작성법은 HTML과 매우매우 흡사하다. 하지만 javascript이다.
- javascript에서 사용하는 키워드를 사용할 수 없다. 예를 들면 label 태그의 for(htmlFor로 사용)와 모든 태그에 널리 쓰이는 class(className으로 사용)가 있다.
- 자바스크립트 변수를 활용하여 값을 입력할 땐 따옴표로 입력하지않고 중괄호{}를 쓴다.
- 아래의 코드는 위의 createElement와 같은 결과를 만드는 JSX이다.
**html과 구분하기 위해서 PascalCase 형태로 작성한다.**
```js
const Button = () => (
    <button 
        id="super-button" 
        onClick={() => console.log("I'm clicked")}>
        Click me!
    </button>
    )
```

## 4. State
### 4.1. State를 안 쓰는 경우
- render를 값이 바뀔 때마다 다시 해줘야 한다.
- 이는 모양도 코드 유지보수성도 영 좋지 못하다.


### 4.2. State 사용하기
- State는 기본적으로 데이터가 저장되는 곳
- React.js는 변경된 부분만 업데이트됩니다.
- 일반 자바스크립트 코드로 작성한 페이지는 노드 정보가 바뀔때마다 5단계에 걸쳐서 노드 트리를 처음부터 다시 생성
- 리액트는 가상돔을 써서 우리 시야에 보이는 부분만 수정해서 보여주고 모든 업데이트가 끝나면 일괄로 합쳐서 실제 돔에 던져준다고 합니다.

```js
[value, setValue] = React.useState(초기값) // React.useState는 [value, modifier] 배열을 반환한다. 이를 배열 형태로 할당 받으면 언패킹되어 value와 setValue로 할당 받을 수 있다.
```

#### 4.2.1. modifier를 사용하는 방법
1. 리터럴 값으로 할당하는 경우
```js
setValue(리터럴 값) // 리터럴을 할당하면 끝.
```

2. 현재 값을 기준으로 변경이 필요한 경우
> 예를 들어 현재 값을 기준으로 1을 증가해야하는 경우라면
```js
setValue(value => value + 1) // 함수 형태로 작성한다.
```

React 코드에서 Event Listener의 콜백함수의 첫 인수에 받아오는 객체: Synthetic Event(합성 이벤트)
이 SyntheticEvent는 JS가 아닌 React에서 발생시키는 이벤트로 React가 동작하는데 있어 최적화된 이벤트라고 생각하면 된다. 원래의 JS의 native event를 얻기 위해선 nativeEvent라는 속성을 찾으면 된다.

참고로 SyntheticEvent 하위 속성에 target이 존재하고 그 속성을 살펴보면 value를 찾을 수 있다. 이 SyntheticEvent.target.value는 input 태그의 속성인 value에 해당되는 값이다.
```js
const onChange = (event) => { // 첫 인수의 event가 React에서 제공하는 SyntheticEvent 객체
    console.log(event.target.value) // onChange 이벤트가 발생한 태그의 value 속성을 콘솔에 출력
}
```

> 지금까지 isolation과 encapsulation 적용해서 모든 JSX를 분리된 컴포넌트로 생성
> -> 이는 컴포넌트 단위로 재사용 가능
> 컴포넌트는 함수를 통해 작성하고 이 함수는 JSX를 반환

## 5. Props
- 부모 컴포넌트로부터 자식 컴포넌트에 데이터를 보낼 수 있게 해주는 방법
- 함수 정의부에 소괄호 안에 arguments로 React가 값을 전달한다.
- 이때 이 인자를 props라고 한다. 즉 React는 JSX로 작성한 attributes 모두를 하나의 객체에 담아 props 인자로 전달한다.
```js
function Component(props) {
    return (
        <tag value={props.value}>{props.text}</tag>
    )
}

function App() {
    return (
        <div>
            <Component text="텍스트" value="1" />
        </div>
    )
}
```

- 컴포넌트를 작성한 함수 정의부에 인자는 단 하나만 갖는다.
- 보통은 props라는 하나의 인자만 정의해서 사용하지 않고 중괄호{}로 작성하여 변수에 언패킹해서 바로 받을 수 있다.
```js
function Component({text, value}) {
    return (
        <tag value={value}>{text}</tag>
    )
}

function App() {
    return (
        <div>
            <Component text="텍스트" value="1" />
        </div>
    )
}
```

- 함수로 정의한 컴포넌트는 onClick과 같은 이벤트를 직접 다는 것이 아니라 props로 전달된다.
```js
function Component({text, value, onClick}) {
    return (
        <tag value={value} onClick={onClick}>{text}</tag> // onClick 함수가 여기서 이벤트의 콜백 함수로 등록된다.
    )
}

function App() {
    return (
        <div>
            <Component text="텍스트" value="1" onClick={() => console.log("I'm clicked")} />
            // 위 코드에서 onClick은 props로 전달되고, 이를 Component에서는 onClick으로 받아서 사용한다.
        </div>
    )
}
```

- javascript는 일급 객체이므로 함수를 인자로 전달할 수 있다.
- 일급 객체: 변수에 할당할 수 있고, 함수의 인자로 전달할 수 있고, 함수의 반환값으로 사용할 수 있다.


### 5.1. Memoization
- 부모 요소가 state가 변경되어 다시 렌더링되면 자식 요소도 다시 렌더링됩니다.
- 자식 요소가 state와 관련o이 없다면 불필요한 렌더링이 발생합니다.
- 이를 방지하기 위해 React.memo를 사용합니다.
- React.memo는 컴포넌트를 렌더링할 때 이전에 렌더링한 결과를 재사용합니다.
- 이전에 렌더링한 결과를 재사용하기 때문에 불필요한 렌더링을 방지할 수 있습니다.
- React.memo는 컴포넌트의 props가 변경되었을 때만 렌더링을 수행합니다.
- 성능 최적화를 위해 사용합니다.

### 5.2. Props Type
- 컴포넌트의 props를 검증하기 위해 사용합니다.
- 컴포넌트의 props가 올바른 값인지 확인할 수 있습니다.
- 컴포넌트의 props가 올바른 값이 아닌 경우, 콘솔에 경고 메시지를 출력합니다.
- 컴포넌트의 props를 검증하기 위해 prop-types 라이브러리를 사용합니다.
- prop-types 라이브러리는 컴포넌트의 props를 검증할 때 사용합니다.
- prop-types 라이브러리를 설치합니다.
```js
npm install prop-types
```
- prop-types 라이브러리를 사용하여 컴포넌트의 props를 검증합니다.
```js
import PropTypes from 'prop-types';

function Component({text, value, onClick}) {
    return (
        <tag value={value} onClick={onClick}>{text}</tag>
    )
}

Component.propTypes = {
    text: PropTypes.string.isRequired,
    value: PropTypes.number.isRequired,
    onClick: PropTypes.func.isRequired,
}
```


## 6. Effect
- Effect Hook은 함수형 컴포넌트에서 side effect를 수행할 수 있게 해줍니다.
- side effect는 컴포넌트의 상태(state)를 변경하는 작업을 의미합니다.
- Effect Hook은 컴포넌트가 렌더링될 때마다 특정 작업을 수행하도록 설정할 수 있습니다.
- Effect Hook은 클래스형 컴포넌트의 componentDidMount와 componentDidUpdate, componentWillUnmount 메서드와 같은 역할을 합니다.
- Effect Hook은 함수형 컴포넌트에서만 사용할 수 있습니다.
- Effect Hook은 함수형 컴포넌트의 렌더링 결과가 실제 돔에 반영된 후에 실행됩니다.
- Effect Hook은 렌더링 직후마다 실행됩니다.
- Effect Hook은 렌더링 직후마다 실행되기 때문에, 렌더링 결과가 실제 돔에 반영된 후에 실행됩니다.

### 6.1. state의 변경마다 전체가 다시 렌더링되는 이유
- state가 변경되면 컴포넌트가 다시 렌더링됩니다. 즉 컴포넌트의 모든 코드가 다시 실행됩니다.
```js
function App() {
    const [counter, setCounter] = useState(0);
    const onClick = () => {
        setCounter((prev) => prev + 1);
    }
    console.log("rendered");
    return (
        <div>
            <h1>{counter}</h1>
            <button onClick={onClick}>Click me!</button>
        </div>
    )
}
```
- 위 코드에서 버튼을 클릭하면 state가 변경되고, 컴포넌트가 다시 렌더링됩니다. 이때 컴포넌트의 모든 코드가 다시 실행됩니다. 따라서 console.log("rendered")가 state가 변경될 때마다 실행됩니다.
- console.log("rendered")가 엄청 무거운 코드이고 단 1회만 실행돼야 하는 부분이라고 상상해봅시다. 즉 state가 변경될 때마다 실행하는 것이 불필요하다고 상상해봅시다.
- console.log("rendered")가 state가 변경될 때마다 실행되지 않도록 하려면 어떻게 해야 할까요? 이때 Effect Hook을 사용합니다.

### 6.2. Effect Hook 사용하기
```js
function App() {
    const [counter, setCounter] = useState(0);
    const onClick = () => {
        setCounter((prev) => prev + 1);
    }
    useEffect(() => {
        console.log("just once");
    }, []); // 두 번째 인수로 빈 배열을 전달하면, 컴포넌트가 처음 렌더링될 때만 실행됩니다.
    console.log("rendered");
    return (
        <div>
            <h1>{counter}</h1>
            <button onClick={onClick}>Click me!</button>
        </div>
    )
}
```

### 6.3. Effect Hook의 두 번째 인수
- Effect Hook의 두 번째 인수로 빈 배열을 전달하면, 컴포넌트가 처음 렌더링될 때만 실행됩니다.
- Effect Hook의 두 번째 인수로 배열을 전달하면, 배열에 포함된 값(state)이 변경될 때마다 첫 번째 인수의 함수가 실행됩니다.
- 특정 state가 변경될 때만 실행되도록 하려면, Effect Hook의 두 번째 인수로 배열을 전달하면 됩니다.
```js
function App() {
    const [counter, setCounter] = useState(0);
    const [name, setName] = useState("");
    const onClick = () => {
        setCounter((prev) => prev + 1);
    }
    useEffect(() => {
        console.log("counter changed");
    }, [counter]); // counter가 변경될 때만 실행됩니다.
    useEffect(() => {
        console.log("name changed");
    }, [name]); // name이 변경될 때만 실행됩니다.
    console.log("rendered");
    return (
        <div>
            <h1>{counter}</h1>
            <button onClick={onClick}>Click me!</button>
            <input value={name} onChange={(e) => setName(e.target.value)} />
        </div>
    )
}
```

### 6.4. Effect Hook의 반환값
- Effect Hook의 첫 번째 인수로 전달한 함수는 반환값으로 cleanup 함수를 반환할 수 있습니다.
- cleanup 함수는 컴포넌트가 언마운트될 때 실행됩니다.
- Effect Hook의 반환값으로 콜백 함수를 반환하면, 컴포넌트가 언마운트될 때 콜백 함수가 실행됩니다.
```js
function App() {
    function Hello() {
        useEffect(() => {
            console.log("Hello mounted");
            return () => {
                console.log("Hello unmounted");
            } // cleanup 함수
        }, []);
        return <div>Hello</div>
    }
    const [visible, setVisible] = useState(false);
    return (
        <div>
            <button onClick={() => setVisible((prev) => !prev)}>Toggle</button>
            {visible && <Hello />}
        </div>
    )
}
```
