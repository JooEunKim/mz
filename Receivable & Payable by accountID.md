# Project : Receivable & Payable by accountID 

## Goal
  - 최상위 로그 기준으로 매입매출을 알아보자.

## KeyActivity
  - 원본 및 가공 데이터를 3.1 데이터 검색 Query를 이용하여 다운로드 한다.
  - 다운받은 데이터를 엑셀 또는 Jupyter 에 업로드 한다.
  - 원본 데이터와 가공 데이터를 조인하여 계정별, product 별 마진 데이터를 생성한다.
  - 시각화 한다.

## Key Reference
  - 데이터 검색 Query

       	select o.payeraccount, o.productcode
              sum(o.unblendedcost) as o_cost,
              sum(m.unblendedcost) as m_cost,	
        from invoice.original_lineitem as o
       	 inner join invoice.modified_lineitem as m 
          on o.payeraccountid = m.payeraccountid
       	 where o.billingperiodstartdate = '2017-12-01 00:00:00'
       	  group by o.payeraccount, o.productcode

  - 시각화 Python Script

  - [본링크](http://support.typora.io/Markdown-Reference/#reference-links) 를 참고하세요.
  - [아래링크](C:\Users\kje\Google_Drive\megazone\DataGatheringVisualization\visualization.py) 를 참고하세요.


