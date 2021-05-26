# Vscode 스니펫

## typescript

### 1.redux toolkit

```ts
"typescript redux toolkit": {
		"prefix": "tsredux",
		"body": [
			"import { createSlice } from \"@reduxjs/toolkit\";",
			"",
			"export interface ${1:${TM_FILENAME_BASE/(.*)/${1:/capitalize}/}}State {",
			"  loading: boolean;",
			"}",
			"",
			"const initialState: ${1:${TM_FILENAME_BASE/(.*)/${1:/capitalize}/}}State = {",
			"  loading: false,",
			"};",
			"",
			"const ${2:${TM_FILENAME_BASE}}Slice = createSlice({",
			"  name: \"${2:${TM_FILENAME_BASE}}\",",
			"  initialState,",
			"  reducers: {",
			"    get${1:${TM_FILENAME_BASE/(.*)/${1:/capitalize}/}}Request(state: ${1:${TM_FILENAME_BASE/(.*)/${1:/capitalize}/}}State, action) {",
			"      state.loading = true;",
			"    },",
			"  },",
			"});",
			"",
			"const { reducer, actions } = ${2:${TM_FILENAME_BASE}}Slice;",
			"",
			"export const { get${1:${TM_FILENAME_BASE/(.*)/${1:/capitalize}/}}Request} = actions;",
			"",
			"export default reducer;",
			""
		],
		"description": ""
	},
```

### 2.saga

```ts
"typescript saga": {
		"prefix": "tssaga",
		"body": [
			"import { PayloadAction } from \"@reduxjs/toolkit\";",
			"import { call, delay, fork, put, takeLatest } from \"redux-saga/effects\";",
			"",
			"function* get${1:${TM_FILENAME_BASE/(.*)/${1:/capitalize}/}}(action: PayloadAction<string>) {",
			"  try {",
			"    yield put({ type: \"\", payload: \"\" });",
			"  } catch (e) {}",
			"}",
			"",
			"function* watch${1:${TM_FILENAME_BASE/(.*)/${1:/capitalize}/}}() {",
			"  yield takeLatest(\"\", get${1:${TM_FILENAME_BASE/(.*)/${1:/capitalize}/}});",
			"}",
			"",
			"export default function* ${2:${TM_FILENAME_BASE}}Saga() {",
			"  yield fork(watch${1:${TM_FILENAME_BASE/(.*)/${1:/capitalize}/}});",
			"}",
			""
		],
		"description": ""
	}
```

### 3. 함수형 컴포넌트

```ts
"typescript hook": {
		"prefix": "tshook",
		"body": [
			"import { useState, useEffect } from 'react';",
			"",
			"function ${1:${TM_FILENAME_BASE}}() {",
			"",
			"  return {}",
			"}",
			"",
			"export default ${1:${TM_FILENAME_BASE}};",
			""
		],
		"description": ""
	},
```
