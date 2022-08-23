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
```yml
onGridReady = (dataGrid) => {
  this.gridApi = dataGrid.api;
}
  
onRowSelected = () => {
  const data = this.gridApi.getSelectedRows();
  this.props.mes440Store.setCheckedRows(data);
}

<DataGrid 
  columnDefs={columnDefs(params())}
  rowData={list}
  onGridReady={this.onGridReady}
  onRowSelected={this.onRowSelected}
  rowSelection='multiple'
/>
```

## Html 코드 추가하는 방법

```yml
async componentDidMount() {
  const {findPldg} = this.props.mes010Store;
  findPldg();
}

render() {
  
  const {pldgContent} = this.props.mes010Store;
  
  return (
    <>
      <p>
        <div dangerouslySetInnerHTML={{ __html: pldgContent.passPldgContent }}></div>
      </p>
    </>
  )
}
```