---
title: BizTalk での mySAP アダプターでの EXECQUERY ステートメントの例 |Microsoft Docs
description: EXECQUERY の例と、mySAP アダプターを BizTalk アダプター パック (BAP) を使用したサンプル
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
ms.openlocfilehash: 631780b540d37e80c9218fc03f58b628e6d6e7d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373479"
---
# <a name="examples-for-execquery-statement"></a><span data-ttu-id="057dc-103">EXECQUERY ステートメントの例</span><span class="sxs-lookup"><span data-stu-id="057dc-103">Examples for EXECQUERY Statement</span></span>
<span data-ttu-id="057dc-104">このトピックでは、EXECQUERY ステートメントの例を示します。</span><span class="sxs-lookup"><span data-stu-id="057dc-104">This topic provides sample EXECQUERY statements.</span></span>  


## <a name="sample-statements"></a><span data-ttu-id="057dc-105">サンプル ステートメント</span><span class="sxs-lookup"><span data-stu-id="057dc-105">Sample statements</span></span>
-   <span data-ttu-id="057dc-106">P1 と P2 の 2 つのパラメーターを受け取るクエリを実行するコマンド。</span><span class="sxs-lookup"><span data-stu-id="057dc-106">Command to execute a query that takes two parameters P1 and P2.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = '0000003262',@P2 = 'La Quinta Hotel & Towers'  
    ```  
  
-   <span data-ttu-id="057dc-107">P1 のパラメーターの値の範囲を受け取るクエリを実行するコマンドです。</span><span class="sxs-lookup"><span data-stu-id="057dc-107">Command to execute a query that takes a range of value for parameter P1.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 BETWEEN '0000003262' AND '0000003265'  
    ```  
  
-   <span data-ttu-id="057dc-108">特定の範囲外パラメーター P1 の値を取得するクエリを実行するコマンド。</span><span class="sxs-lookup"><span data-stu-id="057dc-108">Command to execute a query that takes values for parameter P1 outside a particular range.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', NOT @P1 BETWEEN '0000003262' AND '0000003265'  
    ```  
  
-   <span data-ttu-id="057dc-109">パラメーター P1 の 2 つの値のいずれかを実行するクエリを実行するコマンド。</span><span class="sxs-lookup"><span data-stu-id="057dc-109">Command to execute a query that can take one of two values for parameter P1.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = '0000003262', @P1 = '0000003263'  
    ```  
  
-   <span data-ttu-id="057dc-110">特定のパラメーターの値をとることのできないクエリを実行するコマンド。</span><span class="sxs-lookup"><span data-stu-id="057dc-110">Command to execute a query that cannot take specific values for parameters.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', NOT @P1 = '0000003262', NOT @P2 = '0000003263'  
    ```  
  
     <span data-ttu-id="057dc-111">この例では、P1 は '0000003262' 以外の値を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="057dc-111">In this example, P1 can have any value other than '0000003262'.</span></span> <span data-ttu-id="057dc-112">同様に、P2 では、'0000003263' 以外の値を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="057dc-112">Similarly, P2 can have any value other than '0000003263'.</span></span>  
  
-   <span data-ttu-id="057dc-113">SAP システムで定義されたバリアントを持つクエリを実行するコマンド。</span><span class="sxs-lookup"><span data-stu-id="057dc-113">Command to execute a query that has variants defined in the SAP system.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @variant = ‘variant1’  
    ```  
  
     <span data-ttu-id="057dc-114">バリアントは、保存された一連の SAP クエリの実行中に指定できる選択条件を参照してください。</span><span class="sxs-lookup"><span data-stu-id="057dc-114">Variants refer to a saved set of selection criteria that you can specify while executing an SAP query.</span></span> <span data-ttu-id="057dc-115">たとえば、バリアントを使用すると、クエリの既定値を指定します。</span><span class="sxs-lookup"><span data-stu-id="057dc-115">For example, you can use variants to specify default values for queries.</span></span> <span data-ttu-id="057dc-116">すべてのパラメーターに対して定義されているバリエーションがあるクエリでは、コマンド テキストでパラメーターを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="057dc-116">For queries that have variants defined for all parameters, you do not need to specify the parameters in the command text.</span></span>  
  
-   <span data-ttu-id="057dc-117">パラメーターを必要としないクエリを実行するコマンド。</span><span class="sxs-lookup"><span data-stu-id="057dc-117">Command to execute a query that does not require a parameter.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = 'some_dummy_value'  
    ```  
  
     <span data-ttu-id="057dc-118">パラメーターを受け取らないクエリでは、ダミーの値を持つパラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="057dc-118">For queries that do not take parameter, you must specify a parameter with a dummy value.</span></span>  
  
-   <span data-ttu-id="057dc-119">日付の値を指定してください。 パラメーターを含むクエリを実行するコマンド。</span><span class="sxs-lookup"><span data-stu-id="057dc-119">Command to execute a query containing a parameter expecting a date value.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = '20080606'  
    ```  
  
     <span data-ttu-id="057dc-120">日付の値を指定してください。 パラメーターを受け取るクエリでは、yyyymmdd 形式で指定として日付を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="057dc-120">For queries that take parameters expecting date values, you must specify the date as YYYYMMDD.</span></span>  
  
-   <span data-ttu-id="057dc-121">パラメーターに null 値を指定することでクエリを実行するコマンド。</span><span class="sxs-lookup"><span data-stu-id="057dc-121">Command to execute a query by specifying null values for parameters.</span></span>  
  
     <span data-ttu-id="057dc-122">このようなクエリでは、としてクエリを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="057dc-122">For such queries, you cannot specify a query as:</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = 'null'  
    ```  
  
     <span data-ttu-id="057dc-123">代わりに、値を指定しない場合を指定しないでください P1 にします。</span><span class="sxs-lookup"><span data-stu-id="057dc-123">Instead, if you do not want to specify a value, you should not specify P1 at all.</span></span>  
  
-   <span data-ttu-id="057dc-124">特定の数よりも大きい値を指定してくださいパラメーターを含むクエリを実行するコマンド。</span><span class="sxs-lookup"><span data-stu-id="057dc-124">Command to execute a query containing a parameter expecting a value greater than a certain number.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 > '0000003262'  
    ```  
  
-   <span data-ttu-id="057dc-125">値を指定してください。 パラメーターを含むクエリを実行するコマンドを特定の数よりも低い。</span><span class="sxs-lookup"><span data-stu-id="057dc-125">Command to execute a query containing a parameter expecting a value lesser than a certain number.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 < '0000003262'  
    ```  
  
-   <span data-ttu-id="057dc-126">特定の数以上の値を指定してくださいパラメーターを含むクエリを実行するコマンド。</span><span class="sxs-lookup"><span data-stu-id="057dc-126">Command to execute a query containing a parameter expecting a value greater or equal to a certain number.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 >= '0000003262'  
    ```  
  
-   <span data-ttu-id="057dc-127">小さいまたは特定の数と等しく、値を指定してくださいパラメーターを含むクエリを実行するコマンド。</span><span class="sxs-lookup"><span data-stu-id="057dc-127">Command to execute a query containing a parameter expecting a value lesser or equal to a certain number.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 <= '0000003262'  
    ```  
  
-   <span data-ttu-id="057dc-128">値が特定の数と等しくありません必要パラメーターを含むクエリを実行するコマンド。</span><span class="sxs-lookup"><span data-stu-id="057dc-128">Command to execute a query containing a parameter expecting a value not equal to a certain number.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 != '0000003262'  
    ```  
  