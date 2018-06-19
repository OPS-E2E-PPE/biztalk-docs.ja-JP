---
title: SELECT ステートメントの例は、BizTalk での mySAP アダプターで |Microsoft ドキュメント
description: 例と、mySAP アダプターを BizTalk アダプター パック (BAP) を使用してサンプルを選択します。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 54a5a4ac-a994-4706-9735-a5a1a82b893b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 140e895bf8ec2fb65a848c8752dc8e141530bd85
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216130"
---
# <a name="examples-for-select-statement"></a>SELECT ステートメントの例
このトピックでは、さまざまな SELECT ステートメントの構文例を示します。

## <a name="sample-statements"></a>ステートメントの例 
  
-   SPFLI をという名前のテーブルに表示されているフライトの詳細を一覧表示するには、次の構文を使用します。  
  
    ```  
    Select * from SPFLI  
    ```  
  
-   Flight.txt をという名前のファイルに抽出されたデータを格納する\\\SAPServer\Extracts、次の構文を使用します。  
  
    ```  
    Select * Into file '\\SAPServer\Extracts\flight.txt' from SPFLI  
    ```  
  
-   ニューヨークからサン フランシスコへのすべてのフライトの詳細を一覧表示には、次の構文を使用します。  
  
    ```  
    Select * from SPFLI where cityfrom='NEW YORK' and cityto='SAN FRANCISCO'  
    ```  
  
-   すべての詳細を一覧表示のフライト ニューヨークからの`connid`フィールド値が 1000 ~ 5000 では、次の構文を使用します。  
  
    ```  
    Select * from SPFLI where cityfrom='NEW YORK' and (connid>1000 and connid<5000)  
    ```  
  
-   ユーザー指定の居住地にニューヨークからすべてのフライトの詳細を一覧表示には、次の構文を使用します。  
  
    ```  
    Select * from SPFLI where cityfrom='NEW YORK' and cityto=@variable  
    ```  
  
     このインスタンスで作成という SAP パラメーター`@variable`の値を指定し、対応するコマンド オブジェクトに追加します。  
  
-   LIKE 句で SELECT クエリのパーセント記号、(任意の文字列に 0 個以上の文字)、「%」および「_」(の任意の 1 文字)、アンダー スコアのみ使用できる特殊文字がします。 他のすべてにより、文字列値が考慮され、無視されます。  
  
    -   パーセント「%」の使用をデモ例  
  
        ```  
        SELECT NAME1, PSTLZ  from KNA1 where (MANDT between 596 AND 999) AND NAME1 LIKE '%MODE%'  
        ```  
  
         ここでは、% モード レコードをフェッチすべて Name1 に文字列「モード」が含まれています。  
  
    -   アンダー スコア「_」の使用をデモ例  
  
        ```  
        SELECT NAME1  AS [MYANME],  LAND1, KUNNR  from KNA1 where (NAME1 LIKE 'D_' )  
        ```  
  
         ここでは、「d _」は、Name1 が"D"で始まるし、2 つの文字を含むすべてのレコードをフェッチします。  
  
-   "Between"の述語句を示す例  
  
    ```  
    SELECT NAME1, PSTLZ  from KNA1 where (MANDT between 596 AND 999) AND NAME1 LIKE '%MODE%'  
    ```  
  
-   「間ではなく」述語句を示す例  
  
    ```  
    SELECT NAME1, PSTLZ  from KNA1 where (MANDT not between 596 AND 599) AND NAME1 LIKE '%MODE%'  
    ```  
  
-   結合と TOP 句を使用する SELECT ステートメントの例  
  
    ```  
    SELECT TOP 1 * FROM spfli INNER JOIN sflight ON spfli.mandt = sflight.mandt  
    ```  
  
-   OPTION 句を使用する SELECT ステートメントの例  
  
    ```  
    SELECT top 50000 * from bseg option 'batchsize 20000'  
    ```  
