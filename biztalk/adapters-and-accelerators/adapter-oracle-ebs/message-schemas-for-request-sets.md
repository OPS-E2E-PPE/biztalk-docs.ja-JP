---
title: メッセージ要求のセットのスキーマ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bba9677d-ee94-4da5-8611-b1e47f2f3798
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6fd81ee75088b41a182c5a2aa675266420f8f32f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217098"
---
# <a name="message-schemas-for-request-sets"></a><span data-ttu-id="6dc76-102">要求のセットのメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="6dc76-102">Message Schemas for Request Sets</span></span>
<span data-ttu-id="6dc76-103">Oracle E-business Suite で Oracle アプリケーションの設定の各要求が内の操作として公開される[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="6dc76-103">Each request set in an Oracle application in Oracle E-Business Suite is surfaced as an operation in [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)].</span></span>  
  
## <a name="message-structure-of-request-set-operation"></a><span data-ttu-id="6dc76-104">セット操作の要求のメッセージの構造</span><span class="sxs-lookup"><span data-stu-id="6dc76-104">Message Structure of Request Set Operation</span></span>  
 <span data-ttu-id="6dc76-105">要求のセットの表示操作では、要求-応答メッセージ交換パターンに従います。</span><span class="sxs-lookup"><span data-stu-id="6dc76-105">The operations surfaced for request set follow a request-response message exchange pattern.</span></span> <span data-ttu-id="6dc76-106">次の表は、これらの要求と応答メッセージの構造を示しています。</span><span class="sxs-lookup"><span data-stu-id="6dc76-106">The following table shows the structure of these request and response messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6dc76-107">表の後に、エンティティの説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6dc76-107">See entity descriptions after the table.</span></span>  
  
|<span data-ttu-id="6dc76-108">操作</span><span class="sxs-lookup"><span data-stu-id="6dc76-108">Operation</span></span>|<span data-ttu-id="6dc76-109">XML メッセージ</span><span class="sxs-lookup"><span data-stu-id="6dc76-109">XML Message</span></span>|<span data-ttu-id="6dc76-110">Description</span><span class="sxs-lookup"><span data-stu-id="6dc76-110">Description</span></span>|  
|---------------|-----------------|-----------------|  
|<span data-ttu-id="6dc76-111">[Request_Set_Name]要求</span><span class="sxs-lookup"><span data-stu-id="6dc76-111">[Request_Set_Name] Request</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <[Request_Set_Name] xmlns="[VERSION]/RequestSets/[APP_SHORT_NAME]/">   <SetRelClassOptions>     <Application>[value]</Application>     <ClassName>[value]</ClassName>     <CancelOrHold>[value]</CancelOrHold>     <StaleDate>[value]</StaleDate>     <ContinueOnFail>[value]</ContinueOnFail>   </SetRelClassOptions>   <SetPrintOptions>     <Printer>[value]</Printer>     <Style>[value]</Style>     <Copies>[value]</Copies>     <SaveOutput>[value]</SaveOutput>     <PrintTogether>[value]</PrintTogether>     <ContinueOnFail>[value]</ContinueOnFail>   </SetPrintOptions>   <SetRepeatOptions>     <RepeatTime>[value]</RepeatTime>     <RepeatInterval>[value]</RepeatInterval>     <RepeatUnit>[value]</RepeatUnit>     <RepeatType>[value]</RepeatType>     <RepeatEndTime>[value]</RepeatEndTime>     <ContinueOnFail>[value]</ContinueOnFail>   </SetRepeatOptions>   <SetNlsOptions>     <Language>[value]</Language>     <Territory>[value]</Territory>     <ContinueOnFail>[value]</ContinueOnFail>   </SetNlsOptions>   <StartTime><[value]</StartTime>   <[CONCURRENT_PROGRAM_NAME1]>[value]</[CONCURRENT_PROGRAM_NAME1]>   <[CONCURRENT_PROGRAM_NAME2]>[value]</[CONCURRENT_PROGRAM_NAME2]>   … </[Request_Set_Name]>`|<span data-ttu-id="6dc76-112">-[Request_Set_Name] 操作は、5 つの標準的なパラメーターを受け取る: `SetRelClassOptions`、 `SetPrintOptions`、 `SetRepeatOptions`、 `SetNlsOptions`、および`StartTime`です。</span><span class="sxs-lookup"><span data-stu-id="6dc76-112">- The [Request_Set_Name] operation takes five standard parameters:  `SetRelClassOptions`, `SetPrintOptions`,  `SetRepeatOptions`, `SetNlsOptions`, and `StartTime`.</span></span><br /><br /> <span data-ttu-id="6dc76-113">-`ContinueOnFail`パラメーターは、要求セットの送信を続行するか、親のパラメーターのケースで例外をスローするかどうかを示します (`SetRelClassOptions`、 `SetPrintOptions`、`SetRepeatOptions`または`SetNlsOptions`) が失敗します。</span><span class="sxs-lookup"><span data-stu-id="6dc76-113">- The `ContinueOnFail` parameter indicates whether the request set submission should continue or throw an exception in case the parent parameter (`SetRelClassOptions`, `SetPrintOptions`, `SetRepeatOptions` or `SetNlsOptions`) fails.</span></span> <span data-ttu-id="6dc76-114">指定できます**True** (続行) または**False** (例外をスローする)。</span><span class="sxs-lookup"><span data-stu-id="6dc76-114">You can specify **True** (continue) or **False** (throw an exception).</span></span><br /><br /> <span data-ttu-id="6dc76-115">各パラメーターの詳細についてを参照してください[要求セットの操作について](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-request-sets.md)です。</span><span class="sxs-lookup"><span data-stu-id="6dc76-115">- For detailed information about each parameter, see [Operations on Request Sets](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-request-sets.md).</span></span>|  
|<span data-ttu-id="6dc76-116">[Request_Set_Name]応答</span><span class="sxs-lookup"><span data-stu-id="6dc76-116">[Request_Set_Name] Response</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <[Request_Set_Name]Response xmlns="[VERSION]/RequestSets/[APP_SHORT_NAME]">   <[Request_Set_Name]Result>[value]</[Request_Set_Name]Result> </[Request_Set_Name]Response>`|<span data-ttu-id="6dc76-117">Oracle E-business Suite からの応答には、同時実行の要求 ID が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6dc76-117">The response from Oracle E-Business Suite contains a concurrent request ID.</span></span>|  
  
 <span data-ttu-id="6dc76-118">エンティティの説明</span><span class="sxs-lookup"><span data-stu-id="6dc76-118">Entity descriptions:</span></span>  
  
 <span data-ttu-id="6dc76-119">[バージョン] http://schemas.microsoft.com/OracleEBS/2008/05 を =</span><span class="sxs-lookup"><span data-stu-id="6dc76-119">[VERSION] = http://schemas.microsoft.com/OracleEBS/2008/05</span></span>  
  
 <span data-ttu-id="6dc76-120">のインスタンスにアクセスするたびに SQL Server ログインを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6dc76-120">.</span></span>  
  
 <span data-ttu-id="6dc76-121">[CONCURRENT_PROGRAM_NAME] プログラムの同時要求セットに含めるを = です。</span><span class="sxs-lookup"><span data-stu-id="6dc76-121">[CONCURRENT_PROGRAM_NAME] = Concurrent program included in the request set.</span></span>  
  
## <a name="message-actions-for-request-sets"></a><span data-ttu-id="6dc76-122">要求のセットのメッセージの動作</span><span class="sxs-lookup"><span data-stu-id="6dc76-122">Message Actions for Request Sets</span></span>  
 <span data-ttu-id="6dc76-123">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]要求セットの次のメッセージ アクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="6dc76-123">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] uses the following message actions for request sets.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6dc76-124">表の後に、エンティティの説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6dc76-124">See entity descriptions after the table.</span></span>  
  
|<span data-ttu-id="6dc76-125">メッセージ</span><span class="sxs-lookup"><span data-stu-id="6dc76-125">Message</span></span>|<span data-ttu-id="6dc76-126">操作</span><span class="sxs-lookup"><span data-stu-id="6dc76-126">Action</span></span>|<span data-ttu-id="6dc76-127">例</span><span class="sxs-lookup"><span data-stu-id="6dc76-127">Example</span></span>|  
|-------------|------------|-------------|  
|<span data-ttu-id="6dc76-128">Set 要求を要求します。</span><span class="sxs-lookup"><span data-stu-id="6dc76-128">Request Set request</span></span>|<span data-ttu-id="6dc76-129">RequestSets/[APP_SHORT_NAME]/[REQUESTSET_SHORT_NAME]</span><span class="sxs-lookup"><span data-stu-id="6dc76-129">RequestSets/[APP_SHORT_NAME]/[REQUESTSET_SHORT_NAME]</span></span>|<span data-ttu-id="6dc76-130">RequestSets/SQLGL/FNDRSSUB965</span><span class="sxs-lookup"><span data-stu-id="6dc76-130">RequestSets/SQLGL/FNDRSSUB965</span></span>|  
|<span data-ttu-id="6dc76-131">セットの応答を要求します。</span><span class="sxs-lookup"><span data-stu-id="6dc76-131">Request Set response</span></span>|<span data-ttu-id="6dc76-132">RequestSets/[APP_SHORT_NAME]/[REQUESTSET_SHORT_NAME]/応答</span><span class="sxs-lookup"><span data-stu-id="6dc76-132">RequestSets/[APP_SHORT_NAME]/[REQUESTSET_SHORT_NAME]]/response</span></span>|<span data-ttu-id="6dc76-133">RequestSets/SQLGL/FNDRSSUB965/応答</span><span class="sxs-lookup"><span data-stu-id="6dc76-133">RequestSets/SQLGL/FNDRSSUB965/response</span></span>|  
  
 <span data-ttu-id="6dc76-134">エンティティの説明</span><span class="sxs-lookup"><span data-stu-id="6dc76-134">Entity descriptions:</span></span>  
  
 <span data-ttu-id="6dc76-135">[APP_SHORT_NAME] アプリケーションの短い名前を = です。</span><span class="sxs-lookup"><span data-stu-id="6dc76-135">[APP_SHORT_NAME] = Application short name.</span></span>  
  
 <span data-ttu-id="6dc76-136">[REQUESTSET_SHORT_NAME] = 短い名前の設定を要求します。</span><span class="sxs-lookup"><span data-stu-id="6dc76-136">[REQUESTSET_SHORT_NAME] = Request Set short name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dc76-137">参照</span><span class="sxs-lookup"><span data-stu-id="6dc76-137">See Also</span></span>  
 [<span data-ttu-id="6dc76-138">メッセージと BizTalk Adapter for Oracle E-business Suite のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="6dc76-138">Messages and Message Schemas for BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)