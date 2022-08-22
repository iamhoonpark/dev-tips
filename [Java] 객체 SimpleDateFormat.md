```yml
public void register(SampleVO entity) {
  Usr100 usr100 = new Usr100();
  
  Date now = new Date();
  SimpleDateFormat fromDate = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss");
  SimpleDateFormat toDate = new SimpleDateFormat("yyyy-MM-dd 23:59:59.999");

  Timestamp usrFromDate = Timestamp.valueOf(fromDate.format(now);
  Timestamp usrToDate = Timestamp.valueOf(toDate.format(now);
  
  try {
      usr100.setSequence(new BigDecimal(0));
      usr100.setUsrFromDate(usrFromDate);
      usr100.setUsrToDate(usrToDate);
      this.usr100Store.create(usr100);
  } catch (Exception e) {
    e.printStackTrace();
  }


}
```