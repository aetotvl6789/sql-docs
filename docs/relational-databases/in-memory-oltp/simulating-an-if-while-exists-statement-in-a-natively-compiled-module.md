---
title: "Simulating IF-WHILE EXISTS - natively compiled module"
description: Learn how to simulate the EXISTS clause in conditional statements, which is not supported by natively compiled stored procedures in SQL Server.
ms.custom: seo-dt-2019
ms.date: "03/01/2017"
ms.prod: sql
ms.prod_service: "database-engine, sql-database"
ms.reviewer: ""
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: c0e187c1-cbd9-463c-b417-8a734574f102
author: LitKnd
ms.author: kendralittle
monikerRange: "=azuresqldb-current||>=sql-server-2016||>=sql-server-linux-2017||=azuresqldb-mi-current"
---
# Simulating an IF-WHILE EXISTS Statement in a Natively Compiled Module
[!INCLUDE [SQL Server Azure SQL Database](../../includes/applies-to-version/sql-asdb.md)]

  Natively compiled stored procedures do not support the **EXISTS** clause in conditional statements such as IF and WHILE.  
  
 The following example illustrates a workaround using a BIT variable with a SELECT statement to simulate an EXISTS clause:  
  
```sql  
DECLARE @exists BIT = 0  
SELECT TOP 1 @exists = 1 FROM MyTable WHERE ...  
IF @exists = 1  
```  
  
## See Also  
 [Migration Issues for Natively Compiled Stored Procedures](./a-guide-to-query-processing-for-memory-optimized-tables.md)   
 [Transact-SQL Constructs Not Supported by In-Memory OLTP](../../relational-databases/in-memory-oltp/transact-sql-constructs-not-supported-by-in-memory-oltp.md)  
  
