---
title: SELECT ステートメントの例は、BizTalk での mySAP アダプターで |Microsoft Docs
description: 例と mySAP アダプターの BizTalk アダプター パック (BAP) を使用してサンプルを選択します。
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
ms.openlocfilehash: 982ed09e93a43169a3b0b376fba862176a01745c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373464"
---
# <a name="examples-for-select-statement"></a>SELECT ステートメントの例
このトピックでは、さまざまな SELECT ステートメントの構文の例を示します。

## <a name="sample-statements"></a>サンプル ステートメント 
  
-   SPFLI をという名前のテーブルに記載のフライトの詳細を一覧表示するには、次の構文を使用します。  
  
    ```  
    Select * from SPFLI  
    ```  
  
-   Flight.txt という名前のファイルに抽出されたデータを格納する\\\SAPServer\Extracts、次の構文を使用します。  
  
    ```  
    Select * Into file '\\SAPServer\Extracts\flight.txt' from SPFLI  
    ```  
  
-   ニューヨークからサンフランシスコへのすべてのフライトの詳細を一覧表示には、次の構文を使用します。  
  
    ```  
    Select * from SPFLI where cityfrom='NEW YORK' and cityto='SAN FRANCISCO'  
    ```  
  
-   すべての詳細を一覧表示のフライト ニューヨークから持つ`connid`フィールドの値は 1000 ~ 5000、次の構文を使用します。  
  
    ```  
    Select * from SPFLI where cityfrom='NEW YORK' and (connid>1000 and connid<5000)  
    ```  
  
-   ユーザーが指定した市区町村をニューヨークからすべてのフライトの詳細を一覧表示には、次の構文を使用します。  
  
    ```  
    Select * from SPFLI where cityfrom='NEW YORK' and cityto=@variable  
    ```  
  
     このインスタンスで名前付き SAP パラメーターを作成`@variable`の値を指定して、対応するコマンド オブジェクトに追加します。  
  
-   選択クエリの LIKE 句では、パーセント記号、(0 個以上の文字の文字列) の「%」および「_」(の任意の 1 文字)、アンダー スコアのみ、使用できる特殊文字とは。 他のすべてのユーザーは、文字列値と見なされますが、無視されます。  
  
    -   示すパーセント「%」の使用例  
  
        ```  
        SELECT NAME1, PSTLZ  from KNA1 where (MANDT between 596 AND 999) AND NAME1 LIKE '%MODE%'  
        ```  
  
         ここでは、% モードではすべてのレコードがフェッチ Name1 に文字列「モード」が含まれています。  
  
    -   アンダー スコア「_」の使用を示す例  
  
        ```  
        SELECT NAME1  AS [MYANME],  LAND1, KUNNR  from KNA1 where (NAME1 LIKE 'D_' )  
        ```  
  
         ここでは、"d"の _ Name1 が"D"で始まるし、2 つの文字を含むすべてのレコードをフェッチします。  
  
-   "Between"の述語句を示す例  
  
    ```  
    SELECT NAME1, PSTLZ  from KNA1 where (MANDT between 596 AND 999) AND NAME1 LIKE '%MODE%'  
    ```  
  
-   "Not between"述語句を示す例  
  
    ```  
    SELECT NAME1, PSTLZ  from KNA1 where (MANDT not between 596 AND 599) AND NAME1 LIKE '%MODE%'  
    ```  
  
-   結合および TOP 句を使用して SELECT ステートメントの例  
  
    ```  
    SELECT TOP 1 * FROM spfli INNER JOIN sflight ON spfli.mandt = sflight.mandt  
    ```  
  
-   OPTION 句を使用する SELECT ステートメントの例  
  
    ```  
    SELECT top 50000 * from bseg option 'batchsize 20000'  
    ```  
