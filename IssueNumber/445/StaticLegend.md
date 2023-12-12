
# 프롬프트


## 중첩된 TimeMachineContextConsumer
다음 리액트 컴포넌트를 중첩으로 하면 어떻게돼?

```
export const TimeMachineContextConsumer = ({children}: Props) => {
  const value = useContext(TimeMachineContext)
  if (value === undefined) {
    throw new Error(
      'Component must be wrapped with <TimeMachineContextProvider>'
    )
  }
  return children(container)
}

<TimeMachineContextConsumer>
  <예시 컴포넌트>
     <TimeMachineContextConsumer>
  <예시 컴포넌트2>
  </예시 컴포넌트2>
      </TimeMachineContextConsumer>
  </예시 컴포넌트>
</TimeMachineContextConsumer>
```