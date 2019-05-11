---
title: 要求セットのメッセージ スキーマ |Microsoft Docs
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
ms.openlocfilehash: 1fb14d8ed93f61f72b08bc4db31464bcf8eb4561
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530684"
---
# <a name="message-schemas-for-request-sets"></a><span data-ttu-id="63db6-102">要求セットのメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="63db6-102">Message Schemas for Request Sets</span></span>
<span data-ttu-id="63db6-103">内の操作として表示される各要求では、Oracle E-business Suite で Oracle アプリケーション設定[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="63db6-103">Each request set in an Oracle application in Oracle E-Business Suite is surfaced as an operation in [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)].</span></span>  
  
## <a name="message-structure-of-request-set-operation"></a><span data-ttu-id="63db6-104">設定操作の要求のメッセージの構造</span><span class="sxs-lookup"><span data-stu-id="63db6-104">Message Structure of Request Set Operation</span></span>  
 <span data-ttu-id="63db6-105">要求セットの表示操作では、要求-応答のメッセージ交換パターンに従います。</span><span class="sxs-lookup"><span data-stu-id="63db6-105">The operations surfaced for request set follow a request-response message exchange pattern.</span></span> <span data-ttu-id="63db6-106">次の表では、これらの要求と応答メッセージの構造を示します。</span><span class="sxs-lookup"><span data-stu-id="63db6-106">The following table shows the structure of these request and response messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="63db6-107">表の後は、エンティティの説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63db6-107">See entity descriptions after the table.</span></span>  
  
|<span data-ttu-id="63db6-108">操作</span><span class="sxs-lookup"><span data-stu-id="63db6-108">Operation</span></span>|<span data-ttu-id="63db6-109">XML メッセージ</span><span class="sxs-lookup"><span data-stu-id="63db6-109">XML Message</span></span>|<span data-ttu-id="63db6-110">説明</span><span class="sxs-lookup"><span data-stu-id="63db6-110">Description</span></span>|  
|---------------|-----------------|-----------------|  
|<span data-ttu-id="63db6-111">[Request_Set_Name]要求</span><span class="sxs-lookup"><span data-stu-id="63db6-111">[Request_Set_Name] Request</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <[Request_Set_Name] xmlns="[VERSION]/RequestSets/[APP_SHORT_NAME]/">   <SetRelClassOptions>     <Application>[value]</Application>     <ClassName>[value]</ClassName>     <CancelOrHold>[value]</CancelOrHold>     <StaleDate>[value]</StaleDate>     <ContinueOnFail>[value]</ContinueOnFail>   </SetRelClassOptions>   <SetPrintOptions>     <Printer>[value]</Printer>     <Style>[value]</Style>     <Copies>[value]</Copies>     <SaveOutput>[value]</SaveOutput>     <PrintTogether>[value]</PrintTogether>     <ContinueOnFail>[value]</ContinueOnFail>   </SetPrintOptions>   <SetRepeatOptions>     <RepeatTime>[value]</RepeatTime>     <RepeatInterval>[value]</RepeatInterval>     <RepeatUnit>[value]</RepeatUnit>     <RepeatType>[value]</RepeatType>     <RepeatEndTime>[value]</RepeatEndTime>     <ContinueOnFail>[value]</ContinueOnFail>   </SetRepeatOptions>   <SetNlsOptions>     <Language>[value]</Language>     <Territory>[value]</Territory>     <ContinueOnFail>[value]</ContinueOnFail>   </SetNlsOptions>   <StartTime><[value]</StartTime>   <[CONCURRENT_PROGRAM_NAME1]>[value]</[CONCURRENT_PROGRAM_NAME1]>   <[CONCURRENT_PROGRAM_NAME2]>[value]</[CONCURRENT_PROGRAM_NAME2]>   … </[Request_Set_Name]>`|<span data-ttu-id="63db6-112">-[Request_Set_Name] 操作は、5 つの標準パラメーターを受け取ります。 `SetRelClassOptions`、 `SetPrintOptions`、 `SetRepeatOptions`、 `SetNlsOptions`、および`StartTime`します。</span><span class="sxs-lookup"><span data-stu-id="63db6-112">- The [Request_Set_Name] operation takes five standard parameters:  `SetRelClassOptions`, `SetPrintOptions`,  `SetRepeatOptions`, `SetNlsOptions`, and `StartTime`.</span></span><br /><br /> <span data-ttu-id="63db6-113">-`ContinueOnFail`パラメーターは、要求セットを送信する必要があります続行または親パラメーターの場合は例外をスローするかどうかを示します (`SetRelClassOptions`、 `SetPrintOptions`、`SetRepeatOptions`または`SetNlsOptions`) が失敗します。</span><span class="sxs-lookup"><span data-stu-id="63db6-113">- The `ContinueOnFail` parameter indicates whether the request set submission should continue or throw an exception in case the parent parameter (`SetRelClassOptions`, `SetPrintOptions`, `SetRepeatOptions` or `SetNlsOptions`) fails.</span></span> <span data-ttu-id="63db6-114">指定できる**True** (続行) または**False** (例外をスロー)。</span><span class="sxs-lookup"><span data-stu-id="63db6-114">You can specify **True** (continue) or **False** (throw an exception).</span></span><br /><br /> <span data-ttu-id="63db6-115">各パラメーターの詳細については、次を参照してください。[要求セットの操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-request-sets.md)します。</span><span class="sxs-lookup"><span data-stu-id="63db6-115">- For detailed information about each parameter, see [Operations on Request Sets](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-request-sets.md).</span></span>|  
|<span data-ttu-id="63db6-116">[Request_Set_Name]応答</span><span class="sxs-lookup"><span data-stu-id="63db6-116">[Request_Set_Name] Response</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <[Request_Set_Name]Response xmlns="[VERSION]/RequestSets/[APP_SHORT_NAME]">   <[Request_Set_Name]Result>[value]</[Request_Set_Name]Result> </[Request_Set_Name]Response>`|<span data-ttu-id="63db6-117">Oracle E-business Suite からの応答には、同時実行の要求 ID が含まれています。</span><span class="sxs-lookup"><span data-stu-id="63db6-117">The response from Oracle E-Business Suite contains a concurrent request ID.</span></span>|  
  
 <span data-ttu-id="63db6-118">エンティティの説明</span><span class="sxs-lookup"><span data-stu-id="63db6-118">Entity descriptions:</span></span>  
  
 <span data-ttu-id="63db6-119">[バージョン] = http://schemas.microsoft.com/OracleEBS/2008/05</span><span class="sxs-lookup"><span data-stu-id="63db6-119">[VERSION] = http://schemas.microsoft.com/OracleEBS/2008/05</span></span>  
  
 <span data-ttu-id="63db6-120">.</span><span class="sxs-lookup"><span data-stu-id="63db6-120">.</span></span>  
  
 <span data-ttu-id="63db6-121">[CONCURRENT_PROGRAM_NAME] = 同時実行プログラムの要求セットに含まれています。</span><span class="sxs-lookup"><span data-stu-id="63db6-121">[CONCURRENT_PROGRAM_NAME] = Concurrent program included in the request set.</span></span>  
  
## <a name="message-actions-for-request-sets"></a><span data-ttu-id="63db6-122">要求セットのメッセージのアクション</span><span class="sxs-lookup"><span data-stu-id="63db6-122">Message Actions for Request Sets</span></span>  
 <span data-ttu-id="63db6-123">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]要求セットの次のメッセージのアクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="63db6-123">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] uses the following message actions for request sets.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="63db6-124">表の後は、エンティティの説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63db6-124">See entity descriptions after the table.</span></span>  
  
|<span data-ttu-id="63db6-125">メッセージ</span><span class="sxs-lookup"><span data-stu-id="63db6-125">Message</span></span>|<span data-ttu-id="63db6-126">操作</span><span class="sxs-lookup"><span data-stu-id="63db6-126">Action</span></span>|<span data-ttu-id="63db6-127">例</span><span class="sxs-lookup"><span data-stu-id="63db6-127">Example</span></span>|  
|-------------|------------|-------------|  
|<span data-ttu-id="63db6-128">要求セット</span><span class="sxs-lookup"><span data-stu-id="63db6-128">Request Set request</span></span>|<span data-ttu-id="63db6-129">RequestSets/[APP_SHORT_NAME]/[REQUESTSET_SHORT_NAME]</span><span class="sxs-lookup"><span data-stu-id="63db6-129">RequestSets/[APP_SHORT_NAME]/[REQUESTSET_SHORT_NAME]</span></span>|<span data-ttu-id="63db6-130">RequestSets/SQLGL/FNDRSSUB965</span><span class="sxs-lookup"><span data-stu-id="63db6-130">RequestSets/SQLGL/FNDRSSUB965</span></span>|  
|<span data-ttu-id="63db6-131">要求セットの応答</span><span class="sxs-lookup"><span data-stu-id="63db6-131">Request Set response</span></span>|<span data-ttu-id="63db6-132">RequestSets/[APP_SHORT_NAME]/[REQUESTSET_SHORT_NAME]/応答</span><span class="sxs-lookup"><span data-stu-id="63db6-132">RequestSets/[APP_SHORT_NAME]/[REQUESTSET_SHORT_NAME]]/response</span></span>|<span data-ttu-id="63db6-133">RequestSets SQLGL/FNDRSSUB965/応答</span><span class="sxs-lookup"><span data-stu-id="63db6-133">RequestSets/SQLGL/FNDRSSUB965/response</span></span>|  
  
 <span data-ttu-id="63db6-134">エンティティの説明</span><span class="sxs-lookup"><span data-stu-id="63db6-134">Entity descriptions:</span></span>  
  
 <span data-ttu-id="63db6-135">[APP_SHORT_NAME] アプリケーションの短い名前を = です。</span><span class="sxs-lookup"><span data-stu-id="63db6-135">[APP_SHORT_NAME] = Application short name.</span></span>  
  
 <span data-ttu-id="63db6-136">[REQUESTSET_SHORT_NAME] = 短い名前の設定を要求します。</span><span class="sxs-lookup"><span data-stu-id="63db6-136">[REQUESTSET_SHORT_NAME] = Request Set short name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63db6-137">参照</span><span class="sxs-lookup"><span data-stu-id="63db6-137">See Also</span></span>  
 [<span data-ttu-id="63db6-138">メッセージと BizTalk Adapter for Oracle E-business Suite のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="63db6-138">Messages and Message Schemas for BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)