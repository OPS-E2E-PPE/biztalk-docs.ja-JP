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
# <a name="examples-for-select-statement"></a><span data-ttu-id="8c0f7-103">SELECT ステートメントの例</span><span class="sxs-lookup"><span data-stu-id="8c0f7-103">Examples for SELECT Statement</span></span>
<span data-ttu-id="8c0f7-104">このトピックでは、さまざまな SELECT ステートメントの構文の例を示します。</span><span class="sxs-lookup"><span data-stu-id="8c0f7-104">This topic shows example syntax for various SELECT statements.</span></span>

## <a name="sample-statements"></a><span data-ttu-id="8c0f7-105">サンプル ステートメント</span><span class="sxs-lookup"><span data-stu-id="8c0f7-105">Sample statements</span></span> 
  
-   <span data-ttu-id="8c0f7-106">SPFLI をという名前のテーブルに記載のフライトの詳細を一覧表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="8c0f7-106">To list details about flights listed in the table named SPFLI, use the following syntax:</span></span>  
  
    ```  
    Select * from SPFLI  
    ```  
  
-   <span data-ttu-id="8c0f7-107">Flight.txt という名前のファイルに抽出されたデータを格納する\\\SAPServer\Extracts、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="8c0f7-107">To store extracted data into a file named flight.txt at \\\SAPServer\Extracts, use the following syntax:</span></span>  
  
    ```  
    Select * Into file '\\SAPServer\Extracts\flight.txt' from SPFLI  
    ```  
  
-   <span data-ttu-id="8c0f7-108">ニューヨークからサンフランシスコへのすべてのフライトの詳細を一覧表示には、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="8c0f7-108">To list details of all flights from New York to San Francisco, use the following syntax:</span></span>  
  
    ```  
    Select * from SPFLI where cityfrom='NEW YORK' and cityto='SAN FRANCISCO'  
    ```  
  
-   <span data-ttu-id="8c0f7-109">すべての詳細を一覧表示のフライト ニューヨークから持つ`connid`フィールドの値は 1000 ~ 5000、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="8c0f7-109">To list details of all flights from New York whose `connid` field values are between 1000 and 5000, use the following syntax:</span></span>  
  
    ```  
    Select * from SPFLI where cityfrom='NEW YORK' and (connid>1000 and connid<5000)  
    ```  
  
-   <span data-ttu-id="8c0f7-110">ユーザーが指定した市区町村をニューヨークからすべてのフライトの詳細を一覧表示には、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="8c0f7-110">To list details of all flights from New York to a user-specified city, use the following syntax:</span></span>  
  
    ```  
    Select * from SPFLI where cityfrom='NEW YORK' and cityto=@variable  
    ```  
  
     <span data-ttu-id="8c0f7-111">このインスタンスで名前付き SAP パラメーターを作成`@variable`の値を指定して、対応するコマンド オブジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="8c0f7-111">In this instance, create an SAP parameter named `@variable`, specify the value, and add it to the corresponding command object.</span></span>  
  
-   <span data-ttu-id="8c0f7-112">選択クエリの LIKE 句では、パーセント記号、(0 個以上の文字の文字列) の「%」および「_」(の任意の 1 文字)、アンダー スコアのみ、使用できる特殊文字とは。</span><span class="sxs-lookup"><span data-stu-id="8c0f7-112">In the LIKE clause of a SELECT query, only the percent sign, "%" (for any string of zero or more characters), and underscore, "_" (for any single character), are allowable special characters.</span></span> <span data-ttu-id="8c0f7-113">他のすべてのユーザーは、文字列値と見なされますが、無視されます。</span><span class="sxs-lookup"><span data-stu-id="8c0f7-113">All others are considered string values and are ignored.</span></span>  
  
    -   <span data-ttu-id="8c0f7-114">示すパーセント「%」の使用例</span><span class="sxs-lookup"><span data-stu-id="8c0f7-114">Example to demonstrate the use of percentage "%"</span></span>  
  
        ```  
        SELECT NAME1, PSTLZ  from KNA1 where (MANDT between 596 AND 999) AND NAME1 LIKE '%MODE%'  
        ```  
  
         <span data-ttu-id="8c0f7-115">ここでは、% モードではすべてのレコードがフェッチ Name1 に文字列「モード」が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8c0f7-115">Here, %MODE% fetches all records where Name1 contains the string "MODE".</span></span>  
  
    -   <span data-ttu-id="8c0f7-116">アンダー スコア「_」の使用を示す例</span><span class="sxs-lookup"><span data-stu-id="8c0f7-116">Example to demonstrate the use of underscore "_"</span></span>  
  
        ```  
        SELECT NAME1  AS [MYANME],  LAND1, KUNNR  from KNA1 where (NAME1 LIKE 'D_' )  
        ```  
  
         <span data-ttu-id="8c0f7-117">ここでは、"d"の _ Name1 が"D"で始まるし、2 つの文字を含むすべてのレコードをフェッチします。</span><span class="sxs-lookup"><span data-stu-id="8c0f7-117">Here, "D_" fetches all records where Name1 starts with "D" and contains two characters.</span></span>  
  
-   <span data-ttu-id="8c0f7-118">"Between"の述語句を示す例</span><span class="sxs-lookup"><span data-stu-id="8c0f7-118">Example to demonstrate a "between" predicate clause</span></span>  
  
    ```  
    SELECT NAME1, PSTLZ  from KNA1 where (MANDT between 596 AND 999) AND NAME1 LIKE '%MODE%'  
    ```  
  
-   <span data-ttu-id="8c0f7-119">"Not between"述語句を示す例</span><span class="sxs-lookup"><span data-stu-id="8c0f7-119">Example to demonstrate a "not between" predicate clause</span></span>  
  
    ```  
    SELECT NAME1, PSTLZ  from KNA1 where (MANDT not between 596 AND 599) AND NAME1 LIKE '%MODE%'  
    ```  
  
-   <span data-ttu-id="8c0f7-120">結合および TOP 句を使用して SELECT ステートメントの例</span><span class="sxs-lookup"><span data-stu-id="8c0f7-120">Example for SELECT statement using Join and a TOP clause</span></span>  
  
    ```  
    SELECT TOP 1 * FROM spfli INNER JOIN sflight ON spfli.mandt = sflight.mandt  
    ```  
  
-   <span data-ttu-id="8c0f7-121">OPTION 句を使用する SELECT ステートメントの例</span><span class="sxs-lookup"><span data-stu-id="8c0f7-121">Example for SELECT statement using the OPTION clause</span></span>  
  
    ```  
    SELECT top 50000 * from bseg option 'batchsize 20000'  
    ```  
