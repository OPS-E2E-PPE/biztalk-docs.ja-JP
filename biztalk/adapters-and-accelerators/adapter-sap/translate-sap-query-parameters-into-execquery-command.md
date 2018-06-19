---
title: SAP クエリのパラメーターを BizTalk での mySAP アダプターで EXECQUERY コマンドに変換 |Microsoft ドキュメント
description: EXECQUERY、例と共に SAP クエリを変換するガイダンス
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8a545e20-2607-4946-a60d-0a227b86d093
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efb50db3e499970c0504f81467d382aee31c868f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217730"
---
# <a name="translate-sap-query-parameters-into-execquery-command"></a><span data-ttu-id="66f65-103">SAP クエリのパラメーターを EXECQUERY コマンドに変換します。</span><span class="sxs-lookup"><span data-stu-id="66f65-103">Translate SAP query parameters into EXECQUERY command</span></span>
<span data-ttu-id="66f65-104">クエリのパラメーターが EXECQUERY コマンド テキストに変換する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="66f65-104">Explains how the parameters of a query translate into an EXECQUERY command text.</span></span> <span data-ttu-id="66f65-105">このトピックでは、ZQUERY_TST_NEW カスタムの SAP クエリの例を使用します。</span><span class="sxs-lookup"><span data-stu-id="66f65-105">This topic uses the example of a custom SAP query, ZQUERY_TST_NEW.</span></span>  
  
## <a name="open-the-query-in-sap-gui"></a><span data-ttu-id="66f65-106">SAP の GUI でクエリを開く</span><span class="sxs-lookup"><span data-stu-id="66f65-106">Open the Query in SAP GUI</span></span>  
 <span data-ttu-id="66f65-107">SAP でクエリを開くには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="66f65-107">Perform the following steps to open the query in SAP.</span></span> <span data-ttu-id="66f65-108">ここで示す手順では、ZQUERY_TST_NEW クエリに対してはされ、SAP のバージョンに固有です。</span><span class="sxs-lookup"><span data-stu-id="66f65-108">The steps provided here are for ZQUERY_TST_NEW query and are specific to SAP versions.</span></span>  
  
1.  <span data-ttu-id="66f65-109">SQ01 トランザクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="66f65-109">Run the transaction SQ01.</span></span>  
  
2.  <span data-ttu-id="66f65-110">**ユーザー グループからクエリ**] ページで [**クイック ビューアー**です。</span><span class="sxs-lookup"><span data-stu-id="66f65-110">In the **Query from User Group** page, click **Quick Viewer**.</span></span>  
  
3.  <span data-ttu-id="66f65-111">**クイック ビューアー** ] ページの [、**簡易ビュー**テキスト ボックスで、「 `ZQUERY_TST_NEW`、クリックしてして**表示**です。</span><span class="sxs-lookup"><span data-stu-id="66f65-111">In the **Quick Viewer** page, in the **Quick View** text box, type `ZQUERY_TST_NEW`, and then click **Display**.</span></span>  
  
4.  <span data-ttu-id="66f65-112">**クイック ビューアー**  ページで、をクリックして、**選択フィールド**タブは、クエリ内のすべてのパラメーターを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="66f65-112">In the **Quick Viewer** page, click the **Selection fields** tab to list all the parameters in the query.</span></span>  
  
     <span data-ttu-id="66f65-113">次の図は、クエリ定義にすべてのパラメーターを示します。</span><span class="sxs-lookup"><span data-stu-id="66f65-113">The following figure shows all the parameters in the query definition.</span></span>  
  
     <span data-ttu-id="66f65-114">![SAP クエリのパラメーターのリスト](../../adapters-and-accelerators/adapter-sap/media/sap-query-param-types.gif "sap_query_param_types")</span><span class="sxs-lookup"><span data-stu-id="66f65-114">![List of parameters for an SAP query](../../adapters-and-accelerators/adapter-sap/media/sap-query-param-types.gif "sap_query_param_types")</span></span>  
  
5.  <span data-ttu-id="66f65-115">**[実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66f65-115">Click **Execute**.</span></span> <span data-ttu-id="66f65-116">次のページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="66f65-116">The following page is displayed.</span></span>  
  
     <span data-ttu-id="66f65-117">![SAP クエリのパラメーター値を指定](../../adapters-and-accelerators/adapter-sap/media/sap-query-all-params.gif "sap_query_all_params")</span><span class="sxs-lookup"><span data-stu-id="66f65-117">![Provide parameter values for an SAP query](../../adapters-and-accelerators/adapter-sap/media/sap-query-all-params.gif "sap_query_all_params")</span></span>  
  
6.  <span data-ttu-id="66f65-118">各パラメーターを定義する黄色の矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66f65-118">Click the yellow arrows to define each parameter.</span></span> <span data-ttu-id="66f65-119">特定の許容/非で許容される値を定義するか、または許容/非-許容値の範囲を定義することができます。</span><span class="sxs-lookup"><span data-stu-id="66f65-119">You can either define specific allowable/non-allowable values or you can define a range of allowable/non-allowable values.</span></span>  <span data-ttu-id="66f65-120">パラメーターごとに、SAP GUI で構成されている値に基づいて EXECQUERY 構文を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66f65-120">The EXECQUERY syntax must be specified based on the values configured in the SAP GUI for each parameter.</span></span>  
  
 <span data-ttu-id="66f65-121">次のセクションでは、SAP GUI での値を定義する方法と、それらの値が EXECQUERY 構文に変換する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="66f65-121">The next section provides an explanation about how the values are defined in the SAP GUI and how those values translate to EXECQUERY syntax.</span></span>  
  
## <a name="frame-an-execquery-syntax"></a><span data-ttu-id="66f65-122">フレーム EXECQUERY 構文</span><span class="sxs-lookup"><span data-stu-id="66f65-122">Frame an EXECQUERY Syntax</span></span>  
 <span data-ttu-id="66f65-123">新機能のようになります EXECQUERY 構文に基づいてクエリ定義で定義されているパラメーター値を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="66f65-123">Let’s look at what the EXECQUERY syntax looks like based on the parameter values defined in the query definition.</span></span> <span data-ttu-id="66f65-124">これを理解するには、最初のパラメーターの値を構成する方法の例について説明します**2 桁の数字**、翻訳、 **ZQUERY_TST_NEW**クエリ。</span><span class="sxs-lookup"><span data-stu-id="66f65-124">To understand this, we’ll show examples of how the values configured for the first parameter, **Two digit number**, translate to the  **ZQUERY_TST_NEW** query.</span></span>  
  
 <span data-ttu-id="66f65-125">最初に、仮定の値、 **vals を単一**(緑色のドット) のタブは、次のスクリーン ショットに示すように定義されているは。</span><span class="sxs-lookup"><span data-stu-id="66f65-125">First, let’s assume the values in the **Single vals** tab (with a green dot) are defined as shown in the following screenshot:</span></span>  
  
 <span data-ttu-id="66f65-126">![クエリに使用できるパラメーター値の一覧](../../adapters-and-accelerators/adapter-sap/media/sap-query-param-val.gif "sap_query_param_val")</span><span class="sxs-lookup"><span data-stu-id="66f65-126">![List of parameter values that a query can take](../../adapters-and-accelerators/adapter-sap/media/sap-query-param-val.gif "sap_query_param_val")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="66f65-127">に対して、黄色の矢印をクリックした後、このダイアログ ボックスが表示されます、 **2 桁の数字**パラメーター。</span><span class="sxs-lookup"><span data-stu-id="66f65-127">This dialog box appears after you click the yellow arrow against the **Two digit number** parameter.</span></span>  
  
 <span data-ttu-id="66f65-128">このような場合は、EXECQUERY 構文はようになります。</span><span class="sxs-lookup"><span data-stu-id="66f65-128">In such a case, the EXECQUERY syntax looks like:</span></span>  
  
```  
EXECQUERY ZQUERY_TST_NEW @USERGROUP='mygroup', @P1 = '2', @P1 = '3', @P1 = '5'  
```  
  
 <span data-ttu-id="66f65-129">内の値だけでなく、同じクエリに対して、 **vals を単一** タブ (緑ピリオドの場合) にすることもできます値、 **vals を単一**は次のように定義されている (赤色のドット) を持つタブ。</span><span class="sxs-lookup"><span data-stu-id="66f65-129">For the same query, in addition to the values in the **Single vals** tab (with a green dot), you can also have the values in the **Single vals** tab (with a red dot) defined as following:</span></span>  
  
 <span data-ttu-id="66f65-130">![クエリがとることのできないパラメーター値の一覧](../../adapters-and-accelerators/adapter-sap/media/2af88a57-4ff6-4bcc-8961-0f25dbfb8166.gif "2af88a57-4ff6-4bcc-8961-0f25dbfb8166")</span><span class="sxs-lookup"><span data-stu-id="66f65-130">![List of parameter values that a query cannot take](../../adapters-and-accelerators/adapter-sap/media/2af88a57-4ff6-4bcc-8961-0f25dbfb8166.gif "2af88a57-4ff6-4bcc-8961-0f25dbfb8166")</span></span>  
  
 <span data-ttu-id="66f65-131">このような場合は、EXECQUERY 構文はようになります。</span><span class="sxs-lookup"><span data-stu-id="66f65-131">In such a case, EXECQUERY syntax looks like:</span></span>  
  
```  
EXECQUERY ZQUERY_TST_NEW @USERGROUP='mygroup', @P1 = '2', @P1 = '3', @P1 = '5', NOT @P1 = '6', NOT @P1 = '8'  
```  
  
 <span data-ttu-id="66f65-132">ここでは、値を追加する場合、**範囲**(緑ドットの場合) のようなタブの次のスクリーン ショットします。</span><span class="sxs-lookup"><span data-stu-id="66f65-132">Now, if you add values to the **Ranges** tab (with a green dot), like shown in the following screenshot:</span></span>  
  
 <span data-ttu-id="66f65-133">![クエリに使用できるパラメーター値の範囲](../../adapters-and-accelerators/adapter-sap/media/74907c7d-5a7a-4a2d-a614-6a835eca1764.gif "74907c7d-5a7a-4a2d-a614-6a835eca1764")</span><span class="sxs-lookup"><span data-stu-id="66f65-133">![Range of parameter values that a query can take](../../adapters-and-accelerators/adapter-sap/media/74907c7d-5a7a-4a2d-a614-6a835eca1764.gif "74907c7d-5a7a-4a2d-a614-6a835eca1764")</span></span>  
  
 <span data-ttu-id="66f65-134">EXECQUERY 構文は、ようになります。</span><span class="sxs-lookup"><span data-stu-id="66f65-134">the EXECQUERY syntax looks like:</span></span>  
  
```  
EXECQUERY ZQUERY_TST_NEW @USERGROUP='mygroup', @P1 = '2', @P1 = '3', @P1 = '5', NOT @P1 = '6', NOT @P1 = '8', @P1 BETWEEN '2' and '5'  
```  
  
 <span data-ttu-id="66f65-135">同様に、値を追加する場合、**範囲**(赤色のドット) を持つ タブのような次のスクリーン ショットに示すように。</span><span class="sxs-lookup"><span data-stu-id="66f65-135">Similarly, if you add values to the **Ranges** tab (with a red dot), like shown in the following screenshot:</span></span>  
  
 <span data-ttu-id="66f65-136">![クエリがとることのできないパラメーター値の範囲](../../adapters-and-accelerators/adapter-sap/media/ccc6a7bb-bc47-4325-8b58-094201f791bf.gif "ccc6a7bb-bc47-4325-8b58-094201f791bf")</span><span class="sxs-lookup"><span data-stu-id="66f65-136">![Range of parameter values that a query cannot take](../../adapters-and-accelerators/adapter-sap/media/ccc6a7bb-bc47-4325-8b58-094201f791bf.gif "ccc6a7bb-bc47-4325-8b58-094201f791bf")</span></span>  
  
 <span data-ttu-id="66f65-137">EXECQUERY 構文は、ようになります。</span><span class="sxs-lookup"><span data-stu-id="66f65-137">the EXECQUERY syntax looks like:</span></span>  
  
```  
EXECQUERY ZQUERY_TST_NEW @USERGROUP='mygroup', @P1 = '2', @P1 = '3', @P1 = '5', NOT @P1 = '6', NOT @P1 = '8', @P1 BETWEEN '2' and '5', NOT @P1 BETWEEN '6' AND '8'  
```  
  
 <span data-ttu-id="66f65-138">簡潔さとについては、このトピックの内容のみについて説明、最初のパラメーター **2 桁の数字**します。</span><span class="sxs-lookup"><span data-stu-id="66f65-138">For simplicity and understanding, this topic only talks about the first parameter, **Two digit number**.</span></span> <span data-ttu-id="66f65-139">その他のパラメーターに対して定義された値が EXECQUERY 構文に変換する方法を決定するのに同様のメソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="66f65-139">You can use similar methods to determine how values defined for other parameters translate into an EXECQUERY syntax.</span></span>  
  
