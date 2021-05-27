# React redux tip

## Redux typescript useSelector tip

- redux type 만들기

```ts
import { combineReducers } from "redux";
import * as modules from "store/modules";

const rootReducer = combineReducers({
  ...modules,
});

export type RootState = ReturnType<typeof rootReducer>;

export default rootReducer;
```

- useSelecor Hook 만들기

```ts
import { useSelector } from "react-redux";
import { RootState } from "store";

type StateSelector<T> = (state: RootState) => T;
type EqualityFn<T> = (left: T, right: T) => boolean;

export function useRootState<T>(
  selector: StateSelector<T>,
  equalityFn?: EqualityFn<T>
) {
  return useSelector(selector, equalityFn);
}
```
