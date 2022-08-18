# React Mobx

## Local State
- Store.js Local State 명에 _(언더바)를 초기에 붙이는 이유
```yml
    @observable
    _registParam = {};

    @observable
    _commonCodeLov = [];
```
1) 관용적인 것
2) JS에서 외부에 있는 클래스 변수를 구분하지 못함
3) 언더스코어 라이브러리를 가져다 사용하는 것이 있기 때문

## Row 정보 가져오는 방법

### 1. event 객체
```yml
fn_click_a_row = (e) => {
  console.log(e.colDef);
  console.log(e.colDef.colId);
  console.log(e.data);
}
```

### 2. DataGrid 컴포넌트 속성