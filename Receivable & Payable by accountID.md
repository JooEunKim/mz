# Project : Receivable & Payable by account ID 

## Goal
  - 최상위 로그 기준으로 매입매출을 알아보자.

## KeyActivity
  - 원본 및 가공 데이터를 데이터 검색 [Query](데이터 검색 Query)를 이용하여 다운로드 한다.
  - 다운받은 데이터를 엑셀 또는 Jupyter 에 업로드 한다.
  - 원본 데이터와 가공 데이터를 조인하여 계정별, product 별 마진 데이터를 생성한다.
  - 시각화 한다.

## Key Reference
- 데이터 검색 Query

  #### modified

  > select payeraccountid,
  > sum(unblendedcost) as cost_a
  > from invoice.modified_lineitem_201712 
  > where billingperiodstartdate = '2017-12-01 00:00:00'
  > group by payeraccountid;

  #### original
  > select payeraccountid,
  > sum(unblendedcost) as cost_a
  > from invoice.original_lineitem_201712 
  > where billingperiodstartdate = '2017-12-01 00:00:00'
  > group by payeraccountid;


  - 시각화 Python Script

     - [본링크](http://localhost:8889/notebooks/about_python/Data%20Gathering/net%20amounts%20by%20accountID.ipynb) 를 참고하세요.


