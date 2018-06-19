---
title: EXECQUERY ステートメントの例は、BizTalk での mySAP アダプターで |Microsoft ドキュメント
description: EXECQUERY 例と、mySAP アダプターの BizTalk アダプター パック (BAP) を使用するサンプル
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4139af16-7c38-4ea2-b3e5-5acf8fc1f3c4
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77c5d5877ff502b8fdca620d8b92e4427d3b73b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216242"
---
# <a name="examples-for-execquery-statement"></a><span data-ttu-id="e2233-103">EXECQUERY ステートメントの例</span><span class="sxs-lookup"><span data-stu-id="e2233-103">Examples for EXECQUERY Statement</span></span>
<span data-ttu-id="e2233-104">このトピックでは、EXECQUERY ステートメントの例を示します。</span><span class="sxs-lookup"><span data-stu-id="e2233-104">This topic provides sample EXECQUERY statements.</span></span>  


## <a name="sample-statements"></a><span data-ttu-id="e2233-105">ステートメントの例</span><span class="sxs-lookup"><span data-stu-id="e2233-105">Sample statements</span></span>
-   <span data-ttu-id="e2233-106">P1 と P2 の 2 つのパラメーターを受け取るクエリを実行するコマンドです。</span><span class="sxs-lookup"><span data-stu-id="e2233-106">Command to execute a query that takes two parameters P1 and P2.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = '0000003262',@P2 = 'La Quinta Hotel & Towers'  
    ```  
  
-   <span data-ttu-id="e2233-107">P1 のパラメーターの値の範囲を受け取るクエリを実行するコマンドです。</span><span class="sxs-lookup"><span data-stu-id="e2233-107">Command to execute a query that takes a range of value for parameter P1.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 BETWEEN '0000003262' AND '0000003265'  
    ```  
  
-   <span data-ttu-id="e2233-108">特定の範囲外パラメーター P1 の値を取得するクエリを実行するコマンド。</span><span class="sxs-lookup"><span data-stu-id="e2233-108">Command to execute a query that takes values for parameter P1 outside a particular range.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', NOT @P1 BETWEEN '0000003262' AND '0000003265'  
    ```  
  
-   <span data-ttu-id="e2233-109">パラメーター P1 の 2 つの値のいずれかを実行するクエリを実行するコマンドです。</span><span class="sxs-lookup"><span data-stu-id="e2233-109">Command to execute a query that can take one of two values for parameter P1.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = '0000003262', @P1 = '0000003263'  
    ```  
  
-   <span data-ttu-id="e2233-110">パラメーターに特定の値をとることのできないクエリを実行するコマンドです。</span><span class="sxs-lookup"><span data-stu-id="e2233-110">Command to execute a query that cannot take specific values for parameters.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', NOT @P1 = '0000003262', NOT @P2 = '0000003263'  
    ```  
  
     <span data-ttu-id="e2233-111">この例では、P1 によって '0000003262' 以外の値をすることができます。</span><span class="sxs-lookup"><span data-stu-id="e2233-111">In this example, P1 can have any value other than '0000003262'.</span></span> <span data-ttu-id="e2233-112">同様に、P2 '0000003263' 以外の値をことができます。</span><span class="sxs-lookup"><span data-stu-id="e2233-112">Similarly, P2 can have any value other than '0000003263'.</span></span>  
  
-   <span data-ttu-id="e2233-113">SAP システムで定義されているバリアントを持つクエリを実行するコマンドです。</span><span class="sxs-lookup"><span data-stu-id="e2233-113">Command to execute a query that has variants defined in the SAP system.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @variant = ‘variant1’  
    ```  
  
     <span data-ttu-id="e2233-114">バリアントは、保存されている SAP クエリの実行中に指定できる選択条件のセットを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2233-114">Variants refer to a saved set of selection criteria that you can specify while executing an SAP query.</span></span> <span data-ttu-id="e2233-115">たとえば、バリアントを使用すると、クエリの既定値を指定します。</span><span class="sxs-lookup"><span data-stu-id="e2233-115">For example, you can use variants to specify default values for queries.</span></span> <span data-ttu-id="e2233-116">すべてのパラメーターの定義のバリアントのクエリでは、コマンド テキストでパラメーターを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e2233-116">For queries that have variants defined for all parameters, you do not need to specify the parameters in the command text.</span></span>  
  
-   <span data-ttu-id="e2233-117">パラメーターが不要なクエリを実行するコマンドです。</span><span class="sxs-lookup"><span data-stu-id="e2233-117">Command to execute a query that does not require a parameter.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = 'some_dummy_value'  
    ```  
  
     <span data-ttu-id="e2233-118">パラメーターを受け取らないのクエリでは、ダミーの値を持つパラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2233-118">For queries that do not take parameter, you must specify a parameter with a dummy value.</span></span>  
  
-   <span data-ttu-id="e2233-119">日付の値が必要なパラメーターを含むクエリを実行するコマンドです。</span><span class="sxs-lookup"><span data-stu-id="e2233-119">Command to execute a query containing a parameter expecting a date value.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = '20080606'  
    ```  
  
     <span data-ttu-id="e2233-120">かかるクエリのパラメーターが日付の値を指定してください、yyyymmdd 形式で指定として日付を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2233-120">For queries that take parameters expecting date values, you must specify the date as YYYYMMDD.</span></span>  
  
-   <span data-ttu-id="e2233-121">パラメーターに null 値を指定することによって、クエリを実行するコマンド。</span><span class="sxs-lookup"><span data-stu-id="e2233-121">Command to execute a query by specifying null values for parameters.</span></span>  
  
     <span data-ttu-id="e2233-122">そのようなクエリとしてクエリを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="e2233-122">For such queries, you cannot specify a query as:</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = 'null'  
    ```  
  
     <span data-ttu-id="e2233-123">代わりに、値を指定しない場合は、指定しないで P1 にします。</span><span class="sxs-lookup"><span data-stu-id="e2233-123">Instead, if you do not want to specify a value, you should not specify P1 at all.</span></span>  
  
-   <span data-ttu-id="e2233-124">値を特定の数より大きい値が必要なパラメーターを含むクエリを実行するコマンドです。</span><span class="sxs-lookup"><span data-stu-id="e2233-124">Command to execute a query containing a parameter expecting a value greater than a certain number.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 > '0000003262'  
    ```  
  
-   <span data-ttu-id="e2233-125">値が必要なパラメーターを含むクエリを実行するコマンドが特定の数よりも低い。</span><span class="sxs-lookup"><span data-stu-id="e2233-125">Command to execute a query containing a parameter expecting a value lesser than a certain number.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 < '0000003262'  
    ```  
  
-   <span data-ttu-id="e2233-126">値を一定数以上が必要なパラメーターを含むクエリを実行するコマンドです。</span><span class="sxs-lookup"><span data-stu-id="e2233-126">Command to execute a query containing a parameter expecting a value greater or equal to a certain number.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 >= '0000003262'  
    ```  
  
-   <span data-ttu-id="e2233-127">いずれか小さいほうまたは特定の値に等しい値が必要なパラメーターを含むクエリを実行するコマンドです。</span><span class="sxs-lookup"><span data-stu-id="e2233-127">Command to execute a query containing a parameter expecting a value lesser or equal to a certain number.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 <= '0000003262'  
    ```  
  
-   <span data-ttu-id="e2233-128">値を特定の数と等しくありませんが必要なパラメーターを含むクエリを実行するコマンドです。</span><span class="sxs-lookup"><span data-stu-id="e2233-128">Command to execute a query containing a parameter expecting a value not equal to a certain number.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 != '0000003262'  
    ```  
  