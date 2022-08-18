## Row 정보 가져오는 방법

### 1. event 객체
```yml
fn_clickRows = (e) => {
  console.log(e.colDef);
  console.log(e.colDef.colId);
  console.log(e.data);
}
```

### 2. DataGrid 컴포넌트 속성