---
layout: default
title: 01 NULL 값 처리 (COALESCE)
parent: SQL
nav_order: 1
---

# 01 NULL 값 처리 (COALESCE)

```sql
COALESCE(value1, value2, ..., valueN)
```

COALESCE 함수는 일반적으로 NULL 값 처리에 사용되며, 위와 같은 형태로 사용됨


> ex
> ```sql
> SELECT SUM(COALESCE(sales_amount, 0)) AS total_sales
> FROM sales_table;
> ```
> 위의 쿼리는 sales_amount 컬럼의 값이 NULL인 경우에는 0으로 대체한 뒤, 그 값을 모두 더한 결과를 반환한다.