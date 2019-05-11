---
title: MQSeries コンテキスト プロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQXQH_RemoteQName property [MQSeries adapters]
- MQCIH_TaskEndStatus property [MQSeries adapters]
- MQIIH_SecurityScope property [MQSeries adapters]
- MQCIH_AbendCode property [MQSeries adapters]
- filters, MQSeries adapters
- MQCIH_ReturnCode property [MQSeries adapters]
- MQCIH_TransactionId property [MQSeries adapters]
- MQCIH_ReplyToFormat property [MQSeries adapters]
- MQMD_ReplyToQ property [MQSeries adapters]
- MQMD_PutTime property [MQSeries adapters]
- configuring [MQSeries adapters], properties
- MQMD_PutApplName property [MQSeries adapters]
- configuring [MQSeries adapters], filtering
- MQCIH_UOWControl property [MQSeries adapters]
- MQCIH_ErrorOffset property [MQSeries adapters]
- MQMD_Priority property [MQSeries adapters]
- MQMD_MsgSeqNumber property [MQSeries adapters]
- MQMD_Format property [MQSeries adapters]
- MQCIH_ConversationalTask property [MQSeries adapters]
- Message Descriptor table [MQSeries adapters]
- MQMD_Feedback property [MQSeries adapters]
- MQCIH_Authenticator property [MQSeries adapters]
- MQIIH_TranState property [MQSeries adapters]
- MQCIH_AttentionId property [MQSeries adapters]
- MQMD_UserIdentifier property [MQSeries adapters]
- MQCIH_Flags property [MQSeries adapters]
- MQMD_CorrelId property [MQSeries adapters]
- MQIIH_Format property [MQSeries adapters]
- MQMD_Offset property [MQSeries adapters]
- MQMD_BackoutCount property [MQSeries adapters]
- MQMD_Report property [MQSeries adapters]
- MQMD_MsgFlags property [MQSeries adapters]
- MQSeries adapters, filtering
- MQMD_ApplIdentityData property [MQSeries adapters]
- MQIIH_Authenticator property [MQSeries adapters]
- MQIIH_MFSMapName property [MQSeries adapters]
- MQCIH_LinkType property [MQSeries adapters]
- MQMD_Persistence property [MQSeries adapters]
- MQCIH_CursorPosition property [MQSeries adapters]
- MQCIH_Format property [MQSeries adapters]
- MQCIH_Facility property [MQSeries adapters]
- MQCIH_CancelCode property [MQSeries adapters]
- MQMD_PutDate property [MQSeries adapters]
- MQCIH_NextTransactionId property [MQSeries adapters]
- MQIIH_CommitMode property [MQSeries adapters]
- MQIIH_ReplyToFormat property [MQSeries adapters]
- MQCIH_Function property [MQSeries adapters]
- MQMD_ReplyToQMgr property [MQSeries adapters]
- MQCIH_StartCode property [MQSeries adapters]
- MQMD_Expiry property [MQSeries adapters]
- MQMD_PutApplType property [MQSeries adapters]
- MQCIH_FacilityLike property [MQSeries adapters]
- MQIIH_Flags property [MQSeries adapters]
- MQCIH_CompCode property [MQSeries adapters]
- MQSeries adapters, properties
- MQCIH_FacilityKeepTime property [MQSeries adapters]
- MQMD_ApplOriginData property [MQSeries adapters]
- MQCIH_Reason property [MQSeries adapters]
- MQIIH_LTermOverride property [MQSeries adapters]
- MQMD_CodedCharSetId property [MQSeries adapters]
- MQMD_GroupID property [MQSeries adapters]
- MQXQH_RemoteQMgrName property [MQSeries adapters]
- MQMD_MsgType property [MQSeries adapters]
- MQMD_OriginalLength property [MQSeries adapters]
- MQMD_Encoding property [MQSeries adapters]
- MQMD_AccountingToken property [MQSeries adapters]
- MQCIH_OutputDataLength property [MQSeries adapters]
- MQIIH_TranInstanceId property [MQSeries adapters]
- MQCIH_GetWaitInterval property [MQSeries adapters]
- MQCIH_ADSDescriptor property [MQSeries adapters]
- MQMD_MsgId property [MQSeries adapters]
ms.assetid: 1b22b7d7-432b-4ec5-938c-c43077ce3e0f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 586897eb36f0c5b68ad58c79be865bc92ebd2087
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65326485"
---
# <a name="mqseries-context-properties"></a><span data-ttu-id="a26a0-102">MQSeries コンテキスト プロパティ</span><span class="sxs-lookup"><span data-stu-id="a26a0-102">MQSeries Context Properties</span></span>
<span data-ttu-id="a26a0-103">MQSeries アダプターは、アプリケーションで使用できる MQSeries に固有のコンテキスト プロパティのセットを提供します。</span><span class="sxs-lookup"><span data-stu-id="a26a0-103">The MQSeries adapter provides a set of context properties, specific to MQSeries, for use in your applications.</span></span> <span data-ttu-id="a26a0-104">フィルター式では、オーケストレーションで、これらのプロパティを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="a26a0-104">You can use these properties in filter expressions and in your orchestrations.</span></span>  
  
 <span data-ttu-id="a26a0-105">MQSeries アダプターにバインドされている送信ポートに送信メッセージに MQSeries コンテキスト プロパティを割り当てる、メッセージ代入演算子を使用してし、MQSeries 名前空間で使用できるプロパティのいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="a26a0-105">To assign MQSeries context properties to a message destined to a send port that is bound to the MQSeries adapter, use the message assignment operator and specify one of the available context properties in the MQSeries namespace.</span></span>  
  
 <span data-ttu-id="a26a0-106">MQSeries を設定する例を次に**MQMD_UserIdentifier**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="a26a0-106">The following is an example of setting the MQSeries **MQMD_UserIdentifier** property:</span></span>  
  
```  
Message_2(MQSeries.MQMD_UserIdentifier) = "MeMyselfAndI";  
```  
  
 <span data-ttu-id="a26a0-107">プログラミング言語のヘッダー ファイル、IBM MQSeries SDK に含まれている、C から、列挙値を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a26a0-107">You must obtain enumerated values from the C programming language header files included with the IBM MQSeries SDK.</span></span> <span data-ttu-id="a26a0-108">これらのファイル、プログラム Files\IBM\WebSphere \tools\c\include フォルダにあります。</span><span class="sxs-lookup"><span data-stu-id="a26a0-108">You can find these files in the Program Files\IBM\WebSphere MQ\Tools\c\include folder.</span></span> <span data-ttu-id="a26a0-109">これらのファイルは、設定または MQSeries コンテキスト プロパティの値を読み取るときに使用する値を定義します。</span><span class="sxs-lookup"><span data-stu-id="a26a0-109">These files define the values to use when setting or reading MQSeries context property values.</span></span>  
  
 <span data-ttu-id="a26a0-110">16 進数の文字列値は、バイナリ値を表す文字列です。</span><span class="sxs-lookup"><span data-stu-id="a26a0-110">Hexadecimal string values are character strings representing binary values.</span></span> <span data-ttu-id="a26a0-111">0 x のようなプレフィックスはありません。</span><span class="sxs-lookup"><span data-stu-id="a26a0-111">They do not have a prefix such as 0x.</span></span> <span data-ttu-id="a26a0-112">0 ~ 9 桁の数字と文字"a"~"f"または"A"~"F"が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a26a0-112">They contain digits from 0 through 9 and letters from "a" through "f" or "A" through "F".</span></span> <span data-ttu-id="a26a0-113">アダプターは、それらの空白部分を無視します。</span><span class="sxs-lookup"><span data-stu-id="a26a0-113">The adapter ignores white space in them.</span></span>  
  
 <span data-ttu-id="a26a0-114">これらのプロパティの詳細については、IBM WebSphere MQ のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a26a0-114">For more information about these properties, see the IBM WebSphere MQ documentation.</span></span>  
  
 <span data-ttu-id="a26a0-115">次の表では、使用可能なメッセージ記述子 (MQMD 構造) プロパティと、対応する型と値の完全なセットを示します。</span><span class="sxs-lookup"><span data-stu-id="a26a0-115">The following table shows the complete set of available Message Descriptor (MQMD structure) properties and their corresponding types and values.</span></span>  
  
|<span data-ttu-id="a26a0-116">名前</span><span class="sxs-lookup"><span data-stu-id="a26a0-116">Name</span></span>|<span data-ttu-id="a26a0-117">型</span><span class="sxs-lookup"><span data-stu-id="a26a0-117">Type</span></span>|<span data-ttu-id="a26a0-118">長さ</span><span class="sxs-lookup"><span data-stu-id="a26a0-118">Length</span></span>|<span data-ttu-id="a26a0-119">値</span><span class="sxs-lookup"><span data-stu-id="a26a0-119">Value</span></span>|  
|----------|----------|------------|-----------|  
|<span data-ttu-id="a26a0-120">**MQMD_AccountingToken**</span><span class="sxs-lookup"><span data-stu-id="a26a0-120">**MQMD_AccountingToken**</span></span>|<span data-ttu-id="a26a0-121">string</span><span class="sxs-lookup"><span data-stu-id="a26a0-121">string</span></span>|<span data-ttu-id="a26a0-122">64</span><span class="sxs-lookup"><span data-stu-id="a26a0-122">64</span></span>|<span data-ttu-id="a26a0-123">16 進数文字列</span><span class="sxs-lookup"><span data-stu-id="a26a0-123">Hexadecimal string</span></span>|  
|<span data-ttu-id="a26a0-124">**MQMD_ApplIdentityData**</span><span class="sxs-lookup"><span data-stu-id="a26a0-124">**MQMD_ApplIdentityData**</span></span>|<span data-ttu-id="a26a0-125">string</span><span class="sxs-lookup"><span data-stu-id="a26a0-125">string</span></span>|<span data-ttu-id="a26a0-126">32</span><span class="sxs-lookup"><span data-stu-id="a26a0-126">32</span></span>|<span data-ttu-id="a26a0-127">16 進数文字列</span><span class="sxs-lookup"><span data-stu-id="a26a0-127">Hexadecimal string</span></span>|  
|<span data-ttu-id="a26a0-128">**MQMD_ApplOriginData**</span><span class="sxs-lookup"><span data-stu-id="a26a0-128">**MQMD_ApplOriginData**</span></span>|<span data-ttu-id="a26a0-129">string</span><span class="sxs-lookup"><span data-stu-id="a26a0-129">string</span></span>|<span data-ttu-id="a26a0-130">4</span><span class="sxs-lookup"><span data-stu-id="a26a0-130">4</span></span>|<span data-ttu-id="a26a0-131">String</span><span class="sxs-lookup"><span data-stu-id="a26a0-131">String</span></span><br /><br /> <span data-ttu-id="a26a0-132">**既定値:** 領域</span><span class="sxs-lookup"><span data-stu-id="a26a0-132">**Default:** space</span></span>|  
|<span data-ttu-id="a26a0-133">**MQMD_BackoutCount**</span><span class="sxs-lookup"><span data-stu-id="a26a0-133">**MQMD_BackoutCount**</span></span>|<span data-ttu-id="a26a0-134">unsigned int</span><span class="sxs-lookup"><span data-stu-id="a26a0-134">unsigned int</span></span>|<span data-ttu-id="a26a0-135">4</span><span class="sxs-lookup"><span data-stu-id="a26a0-135">4</span></span>|<span data-ttu-id="a26a0-136">数値</span><span class="sxs-lookup"><span data-stu-id="a26a0-136">Number</span></span><br /><br /> <span data-ttu-id="a26a0-137">読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="a26a0-137">Read only</span></span><br /><br /> <span data-ttu-id="a26a0-138">**既定値:** 0</span><span class="sxs-lookup"><span data-stu-id="a26a0-138">**Default:** 0</span></span>|  
|<span data-ttu-id="a26a0-139">**MQMD_CodedCharSetId**</span><span class="sxs-lookup"><span data-stu-id="a26a0-139">**MQMD_CodedCharSetId**</span></span>|<span data-ttu-id="a26a0-140">unsigned int</span><span class="sxs-lookup"><span data-stu-id="a26a0-140">unsigned int</span></span>|<span data-ttu-id="a26a0-141">4</span><span class="sxs-lookup"><span data-stu-id="a26a0-141">4</span></span>|<span data-ttu-id="a26a0-142">数値</span><span class="sxs-lookup"><span data-stu-id="a26a0-142">Number</span></span><br /><br /> <span data-ttu-id="a26a0-143">**既定値:** 0</span><span class="sxs-lookup"><span data-stu-id="a26a0-143">**Default:** 0</span></span>|  
|<span data-ttu-id="a26a0-144">**MQMD_CorrelId**</span><span class="sxs-lookup"><span data-stu-id="a26a0-144">**MQMD_CorrelId**</span></span>|<span data-ttu-id="a26a0-145">string</span><span class="sxs-lookup"><span data-stu-id="a26a0-145">string</span></span>|<span data-ttu-id="a26a0-146">48</span><span class="sxs-lookup"><span data-stu-id="a26a0-146">48</span></span>|<span data-ttu-id="a26a0-147">16 進数文字列</span><span class="sxs-lookup"><span data-stu-id="a26a0-147">Hexadecimal string</span></span>|  
|<span data-ttu-id="a26a0-148">**MQMD_Encoding**</span><span class="sxs-lookup"><span data-stu-id="a26a0-148">**MQMD_Encoding**</span></span>|<span data-ttu-id="a26a0-149">unsigned int</span><span class="sxs-lookup"><span data-stu-id="a26a0-149">unsigned int</span></span>|<span data-ttu-id="a26a0-150">4</span><span class="sxs-lookup"><span data-stu-id="a26a0-150">4</span></span>|<span data-ttu-id="a26a0-151">数値</span><span class="sxs-lookup"><span data-stu-id="a26a0-151">Number</span></span><br /><br /> <span data-ttu-id="a26a0-152">ヘッダー ファイルの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="a26a0-152">Use header file value.</span></span> <span data-ttu-id="a26a0-153">**既定値:** 0</span><span class="sxs-lookup"><span data-stu-id="a26a0-153">**Default:** 0</span></span>|  
|<span data-ttu-id="a26a0-154">**MQMD_Expiry**</span><span class="sxs-lookup"><span data-stu-id="a26a0-154">**MQMD_Expiry**</span></span>|<span data-ttu-id="a26a0-155">unsigned int</span><span class="sxs-lookup"><span data-stu-id="a26a0-155">unsigned int</span></span>|<span data-ttu-id="a26a0-156">4</span><span class="sxs-lookup"><span data-stu-id="a26a0-156">4</span></span>|<span data-ttu-id="a26a0-157">数値</span><span class="sxs-lookup"><span data-stu-id="a26a0-157">Number</span></span>|  
|<span data-ttu-id="a26a0-158">**MQMD_Feedback**</span><span class="sxs-lookup"><span data-stu-id="a26a0-158">**MQMD_Feedback**</span></span>|<span data-ttu-id="a26a0-159">unsigned int</span><span class="sxs-lookup"><span data-stu-id="a26a0-159">unsigned int</span></span>|<span data-ttu-id="a26a0-160">4</span><span class="sxs-lookup"><span data-stu-id="a26a0-160">4</span></span>|<span data-ttu-id="a26a0-161">数値</span><span class="sxs-lookup"><span data-stu-id="a26a0-161">Number</span></span><br /><br /> <span data-ttu-id="a26a0-162">ヘッダー ファイルの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="a26a0-162">Use header file value.</span></span> <span data-ttu-id="a26a0-163">**既定値:** 0</span><span class="sxs-lookup"><span data-stu-id="a26a0-163">**Default:** 0</span></span>|  
|<span data-ttu-id="a26a0-164">**MQMD_Format**</span><span class="sxs-lookup"><span data-stu-id="a26a0-164">**MQMD_Format**</span></span>|<span data-ttu-id="a26a0-165">string</span><span class="sxs-lookup"><span data-stu-id="a26a0-165">string</span></span>|<span data-ttu-id="a26a0-166">8</span><span class="sxs-lookup"><span data-stu-id="a26a0-166">8</span></span>|<span data-ttu-id="a26a0-167">String</span><span class="sxs-lookup"><span data-stu-id="a26a0-167">String</span></span><br /><br /> <span data-ttu-id="a26a0-168">場合 MQXMIT に設定、により、MQXQH プロパティに値があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a26a0-168">If set to MQXMIT, makes sure that the MQXQH properties have values.</span></span>|  
|<span data-ttu-id="a26a0-169">**MQMD_GroupID**</span><span class="sxs-lookup"><span data-stu-id="a26a0-169">**MQMD_GroupID**</span></span>|<span data-ttu-id="a26a0-170">string</span><span class="sxs-lookup"><span data-stu-id="a26a0-170">string</span></span>|<span data-ttu-id="a26a0-171">48</span><span class="sxs-lookup"><span data-stu-id="a26a0-171">48</span></span>|<span data-ttu-id="a26a0-172">16 進数文字列</span><span class="sxs-lookup"><span data-stu-id="a26a0-172">Hexadecimal string</span></span>|  
|<span data-ttu-id="a26a0-173">**MQMD_MsgFlags**</span><span class="sxs-lookup"><span data-stu-id="a26a0-173">**MQMD_MsgFlags**</span></span>|<span data-ttu-id="a26a0-174">unsigned int</span><span class="sxs-lookup"><span data-stu-id="a26a0-174">unsigned int</span></span>|<span data-ttu-id="a26a0-175">4</span><span class="sxs-lookup"><span data-stu-id="a26a0-175">4</span></span>|<span data-ttu-id="a26a0-176">数値</span><span class="sxs-lookup"><span data-stu-id="a26a0-176">Number</span></span><br /><br /> <span data-ttu-id="a26a0-177">ヘッダー ファイルの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="a26a0-177">Use header file value.</span></span> <span data-ttu-id="a26a0-178">**既定値:** 0</span><span class="sxs-lookup"><span data-stu-id="a26a0-178">**Default:** 0</span></span>|  
|<span data-ttu-id="a26a0-179">**MQMD_MsgId**</span><span class="sxs-lookup"><span data-stu-id="a26a0-179">**MQMD_MsgId**</span></span>|<span data-ttu-id="a26a0-180">string</span><span class="sxs-lookup"><span data-stu-id="a26a0-180">string</span></span>|<span data-ttu-id="a26a0-181">48</span><span class="sxs-lookup"><span data-stu-id="a26a0-181">48</span></span>|<span data-ttu-id="a26a0-182">16 進数文字列</span><span class="sxs-lookup"><span data-stu-id="a26a0-182">Hexadecimal string</span></span>|  
|<span data-ttu-id="a26a0-183">**MQMD_MsgSeqNumber**</span><span class="sxs-lookup"><span data-stu-id="a26a0-183">**MQMD_MsgSeqNumber**</span></span>|<span data-ttu-id="a26a0-184">unsigned int</span><span class="sxs-lookup"><span data-stu-id="a26a0-184">unsigned int</span></span>|<span data-ttu-id="a26a0-185">4</span><span class="sxs-lookup"><span data-stu-id="a26a0-185">4</span></span>||  
|<span data-ttu-id="a26a0-186">**MQMD_MsgType**</span><span class="sxs-lookup"><span data-stu-id="a26a0-186">**MQMD_MsgType**</span></span>|<span data-ttu-id="a26a0-187">unsigned int</span><span class="sxs-lookup"><span data-stu-id="a26a0-187">unsigned int</span></span>|<span data-ttu-id="a26a0-188">4</span><span class="sxs-lookup"><span data-stu-id="a26a0-188">4</span></span>|<span data-ttu-id="a26a0-189">数値</span><span class="sxs-lookup"><span data-stu-id="a26a0-189">Number</span></span><br /><br /> <span data-ttu-id="a26a0-190">ヘッダー ファイルの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="a26a0-190">Use header file value.</span></span>|  
|<span data-ttu-id="a26a0-191">**MQMD_Offset**</span><span class="sxs-lookup"><span data-stu-id="a26a0-191">**MQMD_Offset**</span></span>|<span data-ttu-id="a26a0-192">unsigned int</span><span class="sxs-lookup"><span data-stu-id="a26a0-192">unsigned int</span></span>|<span data-ttu-id="a26a0-193">4</span><span class="sxs-lookup"><span data-stu-id="a26a0-193">4</span></span>||  
|<span data-ttu-id="a26a0-194">**MQMD_OriginalLength**</span><span class="sxs-lookup"><span data-stu-id="a26a0-194">**MQMD_OriginalLength**</span></span>|<span data-ttu-id="a26a0-195">unsigned int</span><span class="sxs-lookup"><span data-stu-id="a26a0-195">unsigned int</span></span>|<span data-ttu-id="a26a0-196">4</span><span class="sxs-lookup"><span data-stu-id="a26a0-196">4</span></span>||  
|<span data-ttu-id="a26a0-197">**MQMD_Persistence**</span><span class="sxs-lookup"><span data-stu-id="a26a0-197">**MQMD_Persistence**</span></span>|<span data-ttu-id="a26a0-198">unsigned int</span><span class="sxs-lookup"><span data-stu-id="a26a0-198">unsigned int</span></span>|<span data-ttu-id="a26a0-199">4</span><span class="sxs-lookup"><span data-stu-id="a26a0-199">4</span></span>|<span data-ttu-id="a26a0-200">数値</span><span class="sxs-lookup"><span data-stu-id="a26a0-200">Number</span></span><br /><br /> <span data-ttu-id="a26a0-201">ヘッダー ファイルの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="a26a0-201">Use header file value.</span></span>|  
|<span data-ttu-id="a26a0-202">**MQMD_Priority**</span><span class="sxs-lookup"><span data-stu-id="a26a0-202">**MQMD_Priority**</span></span>|<span data-ttu-id="a26a0-203">unsigned int</span><span class="sxs-lookup"><span data-stu-id="a26a0-203">unsigned int</span></span>|<span data-ttu-id="a26a0-204">4</span><span class="sxs-lookup"><span data-stu-id="a26a0-204">4</span></span>|<span data-ttu-id="a26a0-205">数値</span><span class="sxs-lookup"><span data-stu-id="a26a0-205">Number</span></span>|  
|<span data-ttu-id="a26a0-206">**MQMD_PutApplName**</span><span class="sxs-lookup"><span data-stu-id="a26a0-206">**MQMD_PutApplName**</span></span>|<span data-ttu-id="a26a0-207">string</span><span class="sxs-lookup"><span data-stu-id="a26a0-207">string</span></span>|<span data-ttu-id="a26a0-208">28</span><span class="sxs-lookup"><span data-stu-id="a26a0-208">28</span></span>|<span data-ttu-id="a26a0-209">String</span><span class="sxs-lookup"><span data-stu-id="a26a0-209">String</span></span><br /><br /> <span data-ttu-id="a26a0-210">**既定値:** 領域</span><span class="sxs-lookup"><span data-stu-id="a26a0-210">**Default:** space</span></span>|  
|<span data-ttu-id="a26a0-211">**MQMD_PutApplType**</span><span class="sxs-lookup"><span data-stu-id="a26a0-211">**MQMD_PutApplType**</span></span>|<span data-ttu-id="a26a0-212">unsigned int</span><span class="sxs-lookup"><span data-stu-id="a26a0-212">unsigned int</span></span>|<span data-ttu-id="a26a0-213">4</span><span class="sxs-lookup"><span data-stu-id="a26a0-213">4</span></span>|<span data-ttu-id="a26a0-214">数値</span><span class="sxs-lookup"><span data-stu-id="a26a0-214">Number</span></span><br /><br /> <span data-ttu-id="a26a0-215">ヘッダー ファイルの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="a26a0-215">Use header file value.</span></span> <span data-ttu-id="a26a0-216">**既定値:** 0</span><span class="sxs-lookup"><span data-stu-id="a26a0-216">**Default:** 0</span></span>|  
|<span data-ttu-id="a26a0-217">**MQMD_PutDate**</span><span class="sxs-lookup"><span data-stu-id="a26a0-217">**MQMD_PutDate**</span></span>|<span data-ttu-id="a26a0-218">string</span><span class="sxs-lookup"><span data-stu-id="a26a0-218">string</span></span>|<span data-ttu-id="a26a0-219">8</span><span class="sxs-lookup"><span data-stu-id="a26a0-219">8</span></span>|<span data-ttu-id="a26a0-220">date</span><span class="sxs-lookup"><span data-stu-id="a26a0-220">Date</span></span>|  
|<span data-ttu-id="a26a0-221">**MQMD_PutTime**</span><span class="sxs-lookup"><span data-stu-id="a26a0-221">**MQMD_PutTime**</span></span>|<span data-ttu-id="a26a0-222">string</span><span class="sxs-lookup"><span data-stu-id="a26a0-222">string</span></span>|<span data-ttu-id="a26a0-223">8</span><span class="sxs-lookup"><span data-stu-id="a26a0-223">8</span></span>|<span data-ttu-id="a26a0-224">Time</span><span class="sxs-lookup"><span data-stu-id="a26a0-224">Time</span></span>|  
|<span data-ttu-id="a26a0-225">**MQMD_ReplyToQ**</span><span class="sxs-lookup"><span data-stu-id="a26a0-225">**MQMD_ReplyToQ**</span></span>|<span data-ttu-id="a26a0-226">string</span><span class="sxs-lookup"><span data-stu-id="a26a0-226">string</span></span>|<span data-ttu-id="a26a0-227">48</span><span class="sxs-lookup"><span data-stu-id="a26a0-227">48</span></span>|<span data-ttu-id="a26a0-228">String</span><span class="sxs-lookup"><span data-stu-id="a26a0-228">String</span></span><br /><br /> <span data-ttu-id="a26a0-229">**既定値:** 領域</span><span class="sxs-lookup"><span data-stu-id="a26a0-229">**Default:** space</span></span>|  
|<span data-ttu-id="a26a0-230">**MQMD_ReplyToQMgr**</span><span class="sxs-lookup"><span data-stu-id="a26a0-230">**MQMD_ReplyToQMgr**</span></span>|<span data-ttu-id="a26a0-231">string</span><span class="sxs-lookup"><span data-stu-id="a26a0-231">string</span></span>|<span data-ttu-id="a26a0-232">48</span><span class="sxs-lookup"><span data-stu-id="a26a0-232">48</span></span>|<span data-ttu-id="a26a0-233">String</span><span class="sxs-lookup"><span data-stu-id="a26a0-233">String</span></span><br /><br /> <span data-ttu-id="a26a0-234">**既定値:** 領域</span><span class="sxs-lookup"><span data-stu-id="a26a0-234">**Default:** space</span></span>|  
|<span data-ttu-id="a26a0-235">**MQMD_Report**</span><span class="sxs-lookup"><span data-stu-id="a26a0-235">**MQMD_Report**</span></span>|<span data-ttu-id="a26a0-236">unsigned int</span><span class="sxs-lookup"><span data-stu-id="a26a0-236">unsigned int</span></span>|<span data-ttu-id="a26a0-237">4</span><span class="sxs-lookup"><span data-stu-id="a26a0-237">4</span></span>|<span data-ttu-id="a26a0-238">数値</span><span class="sxs-lookup"><span data-stu-id="a26a0-238">Number</span></span><br /><br /> <span data-ttu-id="a26a0-239">ヘッダー ファイルの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="a26a0-239">Use header file value.</span></span>|  
|<span data-ttu-id="a26a0-240">**MQMD_UserIdentifier**</span><span class="sxs-lookup"><span data-stu-id="a26a0-240">**MQMD_UserIdentifier**</span></span>|<span data-ttu-id="a26a0-241">string</span><span class="sxs-lookup"><span data-stu-id="a26a0-241">string</span></span>|<span data-ttu-id="a26a0-242">12</span><span class="sxs-lookup"><span data-stu-id="a26a0-242">12</span></span>|<span data-ttu-id="a26a0-243">String</span><span class="sxs-lookup"><span data-stu-id="a26a0-243">String</span></span><br /><br /> <span data-ttu-id="a26a0-244">使用するときに、ユーザー識別子を含む、 **SSOAffiliateApplication**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="a26a0-244">Contains the user identifier when you use the **SSOAffiliateApplication** property.</span></span>|  
  
 <span data-ttu-id="a26a0-245">MQSeries 転送キューから直接メッセージを受信するときに、MQSeries アダプターは転送キューのヘッダー プロパティ (MQXQH データ構造体) を書式設定し、対応するコンテキスト プロパティに配置します。</span><span class="sxs-lookup"><span data-stu-id="a26a0-245">When receiving messages directly from MQSeries transmission queues, the MQSeries adapter formats the transmission queue header properties (the MQXQH data structure) and places them in their corresponding context properties.</span></span> <span data-ttu-id="a26a0-246">ヘッダーのプロパティはフォーマットされ、対応するコンテキスト プロパティ場合にのみから値を割り当てられているメッセージを MQSeries 転送キューに直接送信する場合、 **MQMD_Format** MQXMIT の値を持つプロパティです。</span><span class="sxs-lookup"><span data-stu-id="a26a0-246">When sending messages directly to MQSeries transmission queues, the header properties are formatted and assigned values from the corresponding context properties only if the **MQMD_Format** property has a value of MQXMIT.</span></span> <span data-ttu-id="a26a0-247">次の表は、プロパティを示しています。</span><span class="sxs-lookup"><span data-stu-id="a26a0-247">The following table describes the properties.</span></span>  
  
|<span data-ttu-id="a26a0-248">名前</span><span class="sxs-lookup"><span data-stu-id="a26a0-248">Name</span></span>|<span data-ttu-id="a26a0-249">型</span><span class="sxs-lookup"><span data-stu-id="a26a0-249">Type</span></span>|<span data-ttu-id="a26a0-250">長さ</span><span class="sxs-lookup"><span data-stu-id="a26a0-250">Length</span></span>|<span data-ttu-id="a26a0-251">値</span><span class="sxs-lookup"><span data-stu-id="a26a0-251">Value</span></span>|  
|----------|----------|------------|-----------|  
|<span data-ttu-id="a26a0-252">**MQXQH_RemoteQMgrName**</span><span class="sxs-lookup"><span data-stu-id="a26a0-252">**MQXQH_RemoteQMgrName**</span></span>|<span data-ttu-id="a26a0-253">string</span><span class="sxs-lookup"><span data-stu-id="a26a0-253">string</span></span>|<span data-ttu-id="a26a0-254">48</span><span class="sxs-lookup"><span data-stu-id="a26a0-254">48</span></span>|<span data-ttu-id="a26a0-255">string</span><span class="sxs-lookup"><span data-stu-id="a26a0-255">string</span></span>|  
|<span data-ttu-id="a26a0-256">**MQXQH_RemoteQName**</span><span class="sxs-lookup"><span data-stu-id="a26a0-256">**MQXQH_RemoteQName**</span></span>|<span data-ttu-id="a26a0-257">string</span><span class="sxs-lookup"><span data-stu-id="a26a0-257">string</span></span>|<span data-ttu-id="a26a0-258">48</span><span class="sxs-lookup"><span data-stu-id="a26a0-258">48</span></span>|<span data-ttu-id="a26a0-259">string</span><span class="sxs-lookup"><span data-stu-id="a26a0-259">string</span></span>|  
  
 <span data-ttu-id="a26a0-260">このトピックの前半に示したプロパティと共に、アダプターは同じ規則に従って次のメッセージ記述子の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="a26a0-260">Together with the properties listed earlier in this topic, the adapter populates the following Message Descriptor values following the same rules.</span></span> <span data-ttu-id="a26a0-261">アダプター MQMD_ ではなく MQXQH_ でこれらのプロパティ名のプレフィックスが、それ以外の場合、メッセージ記述子テーブルで定義されているプロパティに直接マップします。</span><span class="sxs-lookup"><span data-stu-id="a26a0-261">The adapter prefixes these property names with MQXQH_ instead of MQMD_, but otherwise they map directly to those properties defined in the Message Descriptor table:</span></span>  
  
- <span data-ttu-id="a26a0-262">**MQXQH_MsgDesc_AccountingToken**</span><span class="sxs-lookup"><span data-stu-id="a26a0-262">**MQXQH_MsgDesc_AccountingToken**</span></span>  
  
- <span data-ttu-id="a26a0-263">**MQXQH_MsgDesc_ApplIdentityData**</span><span class="sxs-lookup"><span data-stu-id="a26a0-263">**MQXQH_MsgDesc_ApplIdentityData**</span></span>  
  
- <span data-ttu-id="a26a0-264">**MQXQH_MsgDesc_ApplOriginData**</span><span class="sxs-lookup"><span data-stu-id="a26a0-264">**MQXQH_MsgDesc_ApplOriginData**</span></span>  
  
- <span data-ttu-id="a26a0-265">**MQXQH_MsgDesc_BackoutCount**</span><span class="sxs-lookup"><span data-stu-id="a26a0-265">**MQXQH_MsgDesc_BackoutCount**</span></span>  
  
- <span data-ttu-id="a26a0-266">**MQXQH_MsgDesc_CodedCharSetId**</span><span class="sxs-lookup"><span data-stu-id="a26a0-266">**MQXQH_MsgDesc_CodedCharSetId**</span></span>  
  
- <span data-ttu-id="a26a0-267">**MQXQH_MsgDesc_CorrelId**</span><span class="sxs-lookup"><span data-stu-id="a26a0-267">**MQXQH_MsgDesc_CorrelId**</span></span>  
  
- <span data-ttu-id="a26a0-268">**MQXQH_MsgDesc_Encoding**</span><span class="sxs-lookup"><span data-stu-id="a26a0-268">**MQXQH_MsgDesc_Encoding**</span></span>  
  
- <span data-ttu-id="a26a0-269">**MQXQH_MsgDesc_Expiry**</span><span class="sxs-lookup"><span data-stu-id="a26a0-269">**MQXQH_MsgDesc_Expiry**</span></span>  
  
- <span data-ttu-id="a26a0-270">**MQXQH_MsgDesc_Feedback**</span><span class="sxs-lookup"><span data-stu-id="a26a0-270">**MQXQH_MsgDesc_Feedback**</span></span>  
  
- <span data-ttu-id="a26a0-271">**MQXQH_MsgDesc_Format**</span><span class="sxs-lookup"><span data-stu-id="a26a0-271">**MQXQH_MsgDesc_Format**</span></span>  
  
- <span data-ttu-id="a26a0-272">**MQXQH_MsgDesc_MsgId**</span><span class="sxs-lookup"><span data-stu-id="a26a0-272">**MQXQH_MsgDesc_MsgId**</span></span>  
  
- <span data-ttu-id="a26a0-273">**MQXQH_MsgDesc_MsgType**</span><span class="sxs-lookup"><span data-stu-id="a26a0-273">**MQXQH_MsgDesc_MsgType**</span></span>  
  
- <span data-ttu-id="a26a0-274">**MQXQH_MsgDesc_Persistence**</span><span class="sxs-lookup"><span data-stu-id="a26a0-274">**MQXQH_MsgDesc_Persistence**</span></span>  
  
- <span data-ttu-id="a26a0-275">**MQXQH_MsgDesc_Priority**</span><span class="sxs-lookup"><span data-stu-id="a26a0-275">**MQXQH_MsgDesc_Priority**</span></span>  
  
- <span data-ttu-id="a26a0-276">**MQXQH_MsgDesc_PutApplName**</span><span class="sxs-lookup"><span data-stu-id="a26a0-276">**MQXQH_MsgDesc_PutApplName**</span></span>  
  
- <span data-ttu-id="a26a0-277">**MQXQH_MsgDesc_PutApplType**</span><span class="sxs-lookup"><span data-stu-id="a26a0-277">**MQXQH_MsgDesc_PutApplType**</span></span>  
  
- <span data-ttu-id="a26a0-278">**MQXQH_MsgDesc_PutDate**</span><span class="sxs-lookup"><span data-stu-id="a26a0-278">**MQXQH_MsgDesc_PutDate**</span></span>  
  
- <span data-ttu-id="a26a0-279">**MQXQH_MsgDesc_PutTime**</span><span class="sxs-lookup"><span data-stu-id="a26a0-279">**MQXQH_MsgDesc_PutTime**</span></span>  
  
- <span data-ttu-id="a26a0-280">**MQXQH_MsgDesc_ReplyToQ**</span><span class="sxs-lookup"><span data-stu-id="a26a0-280">**MQXQH_MsgDesc_ReplyToQ**</span></span>  
  
- <span data-ttu-id="a26a0-281">**MQXQH_MsgDesc_ReplyToQMgr**</span><span class="sxs-lookup"><span data-stu-id="a26a0-281">**MQXQH_MsgDesc_ReplyToQMgr**</span></span>  
  
- <span data-ttu-id="a26a0-282">**MQXQH_MsgDesc_Report**</span><span class="sxs-lookup"><span data-stu-id="a26a0-282">**MQXQH_MsgDesc_Report**</span></span>  
  
- <span data-ttu-id="a26a0-283">**MQXQH_MsgDesc_UserIdentifier**</span><span class="sxs-lookup"><span data-stu-id="a26a0-283">**MQXQH_MsgDesc_UserIdentifier**</span></span>  
  
  <span data-ttu-id="a26a0-284">プロパティがある追加 MQSeries に関連するプロパティ スキーマに付属しており、フィルター式で使用できます。</span><span class="sxs-lookup"><span data-stu-id="a26a0-284">There are additional MQSeries-related properties included in the property schema and available for use in filtering expressions.</span></span> <span data-ttu-id="a26a0-285">次の表は、これらのプロパティを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="a26a0-285">The following table lists these properties.</span></span>  
  
|<span data-ttu-id="a26a0-286">名前</span><span class="sxs-lookup"><span data-stu-id="a26a0-286">Name</span></span>|<span data-ttu-id="a26a0-287">型</span><span class="sxs-lookup"><span data-stu-id="a26a0-287">Type</span></span>|<span data-ttu-id="a26a0-288">長さ</span><span class="sxs-lookup"><span data-stu-id="a26a0-288">Length</span></span>|<span data-ttu-id="a26a0-289">値</span><span class="sxs-lookup"><span data-stu-id="a26a0-289">Value</span></span>|  
|----------|----------|------------|-----------|  
|<span data-ttu-id="a26a0-290">**MQCIH_AbendCode**</span><span class="sxs-lookup"><span data-stu-id="a26a0-290">**MQCIH_AbendCode**</span></span>|<span data-ttu-id="a26a0-291">string</span><span class="sxs-lookup"><span data-stu-id="a26a0-291">string</span></span>|<span data-ttu-id="a26a0-292">4</span><span class="sxs-lookup"><span data-stu-id="a26a0-292">4</span></span>||  
|<span data-ttu-id="a26a0-293">**MQCIH_ADSDescriptor**</span><span class="sxs-lookup"><span data-stu-id="a26a0-293">**MQCIH_ADSDescriptor**</span></span>|<span data-ttu-id="a26a0-294">unsigned int</span><span class="sxs-lookup"><span data-stu-id="a26a0-294">unsigned int</span></span>|<span data-ttu-id="a26a0-295">4</span><span class="sxs-lookup"><span data-stu-id="a26a0-295">4</span></span>||  
|<span data-ttu-id="a26a0-296">**MQCIH_AttentionId**</span><span class="sxs-lookup"><span data-stu-id="a26a0-296">**MQCIH_AttentionId**</span></span>|<span data-ttu-id="a26a0-297">string</span><span class="sxs-lookup"><span data-stu-id="a26a0-297">string</span></span>|<span data-ttu-id="a26a0-298">4</span><span class="sxs-lookup"><span data-stu-id="a26a0-298">4</span></span>||  
|<span data-ttu-id="a26a0-299">**MQCIH_Authenticator**</span><span class="sxs-lookup"><span data-stu-id="a26a0-299">**MQCIH_Authenticator**</span></span>|<span data-ttu-id="a26a0-300">string</span><span class="sxs-lookup"><span data-stu-id="a26a0-300">string</span></span>|<span data-ttu-id="a26a0-301">8</span><span class="sxs-lookup"><span data-stu-id="a26a0-301">8</span></span>|<span data-ttu-id="a26a0-302">使用すると、SSO パスワードに設定、 **SSOAffiliateApplication**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="a26a0-302">Set to the SSO password when you use the **SSOAffiliateApplication** property.</span></span> <span data-ttu-id="a26a0-303">**注:** この値は、SSO パスワードの長さが 8 文字を超える場合は、MQSeries アダプターが空白に設定されます。</span><span class="sxs-lookup"><span data-stu-id="a26a0-303">**Note:**  This value will be set to blank by the MQSeries adapter if length of the SSO password exceeds 8 characters.</span></span>|  
|<span data-ttu-id="a26a0-304">**MQCIH_CancelCode**</span><span class="sxs-lookup"><span data-stu-id="a26a0-304">**MQCIH_CancelCode**</span></span>|<span data-ttu-id="a26a0-305">string</span><span class="sxs-lookup"><span data-stu-id="a26a0-305">string</span></span>|<span data-ttu-id="a26a0-306">4</span><span class="sxs-lookup"><span data-stu-id="a26a0-306">4</span></span>||  
|<span data-ttu-id="a26a0-307">**MQCIH_CompCode**</span><span class="sxs-lookup"><span data-stu-id="a26a0-307">**MQCIH_CompCode**</span></span>|<span data-ttu-id="a26a0-308">unsigned int</span><span class="sxs-lookup"><span data-stu-id="a26a0-308">unsigned int</span></span>|<span data-ttu-id="a26a0-309">4</span><span class="sxs-lookup"><span data-stu-id="a26a0-309">4</span></span>||  
|<span data-ttu-id="a26a0-310">**MQCIH_ConversationalTask**</span><span class="sxs-lookup"><span data-stu-id="a26a0-310">**MQCIH_ConversationalTask**</span></span>|<span data-ttu-id="a26a0-311">unsigned int</span><span class="sxs-lookup"><span data-stu-id="a26a0-311">unsigned int</span></span>|<span data-ttu-id="a26a0-312">4</span><span class="sxs-lookup"><span data-stu-id="a26a0-312">4</span></span>||  
|<span data-ttu-id="a26a0-313">**MQCIH_CursorPosition**</span><span class="sxs-lookup"><span data-stu-id="a26a0-313">**MQCIH_CursorPosition**</span></span>|<span data-ttu-id="a26a0-314">unsigned int</span><span class="sxs-lookup"><span data-stu-id="a26a0-314">unsigned int</span></span>|<span data-ttu-id="a26a0-315">4</span><span class="sxs-lookup"><span data-stu-id="a26a0-315">4</span></span>||  
|<span data-ttu-id="a26a0-316">**MQCIH_ErrorOffset**</span><span class="sxs-lookup"><span data-stu-id="a26a0-316">**MQCIH_ErrorOffset**</span></span>|<span data-ttu-id="a26a0-317">unsigned int</span><span class="sxs-lookup"><span data-stu-id="a26a0-317">unsigned int</span></span>|<span data-ttu-id="a26a0-318">4</span><span class="sxs-lookup"><span data-stu-id="a26a0-318">4</span></span>||  
|<span data-ttu-id="a26a0-319">**MQCIH_Facility**</span><span class="sxs-lookup"><span data-stu-id="a26a0-319">**MQCIH_Facility**</span></span>|<span data-ttu-id="a26a0-320">string</span><span class="sxs-lookup"><span data-stu-id="a26a0-320">string</span></span>|<span data-ttu-id="a26a0-321">16</span><span class="sxs-lookup"><span data-stu-id="a26a0-321">16</span></span>|<span data-ttu-id="a26a0-322">16 進数文字列</span><span class="sxs-lookup"><span data-stu-id="a26a0-322">Hexadecimal string</span></span>|  
|<span data-ttu-id="a26a0-323">**MQCIH_FacilityKeepTime**</span><span class="sxs-lookup"><span data-stu-id="a26a0-323">**MQCIH_FacilityKeepTime**</span></span>|<span data-ttu-id="a26a0-324">unsigned int</span><span class="sxs-lookup"><span data-stu-id="a26a0-324">unsigned int</span></span>|<span data-ttu-id="a26a0-325">4</span><span class="sxs-lookup"><span data-stu-id="a26a0-325">4</span></span>||  
|<span data-ttu-id="a26a0-326">**MQCIH_FacilityLike**</span><span class="sxs-lookup"><span data-stu-id="a26a0-326">**MQCIH_FacilityLike**</span></span>|<span data-ttu-id="a26a0-327">string</span><span class="sxs-lookup"><span data-stu-id="a26a0-327">string</span></span>|<span data-ttu-id="a26a0-328">4</span><span class="sxs-lookup"><span data-stu-id="a26a0-328">4</span></span>||  
|<span data-ttu-id="a26a0-329">**MQCIH_Flags**</span><span class="sxs-lookup"><span data-stu-id="a26a0-329">**MQCIH_Flags**</span></span>|<span data-ttu-id="a26a0-330">unsigned int</span><span class="sxs-lookup"><span data-stu-id="a26a0-330">unsigned int</span></span>|<span data-ttu-id="a26a0-331">4</span><span class="sxs-lookup"><span data-stu-id="a26a0-331">4</span></span>||  
|<span data-ttu-id="a26a0-332">**MQCIH_Format**</span><span class="sxs-lookup"><span data-stu-id="a26a0-332">**MQCIH_Format**</span></span>|<span data-ttu-id="a26a0-333">string</span><span class="sxs-lookup"><span data-stu-id="a26a0-333">string</span></span>|||  
|<span data-ttu-id="a26a0-334">**MQCIH_Function**</span><span class="sxs-lookup"><span data-stu-id="a26a0-334">**MQCIH_Function**</span></span>|<span data-ttu-id="a26a0-335">string</span><span class="sxs-lookup"><span data-stu-id="a26a0-335">string</span></span>|<span data-ttu-id="a26a0-336">4</span><span class="sxs-lookup"><span data-stu-id="a26a0-336">4</span></span>||  
|<span data-ttu-id="a26a0-337">**MQCIH_GetWaitInterval**</span><span class="sxs-lookup"><span data-stu-id="a26a0-337">**MQCIH_GetWaitInterval**</span></span>|<span data-ttu-id="a26a0-338">unsigned int</span><span class="sxs-lookup"><span data-stu-id="a26a0-338">unsigned int</span></span>|<span data-ttu-id="a26a0-339">4</span><span class="sxs-lookup"><span data-stu-id="a26a0-339">4</span></span>||  
|<span data-ttu-id="a26a0-340">**MQCIH_LinkType**</span><span class="sxs-lookup"><span data-stu-id="a26a0-340">**MQCIH_LinkType**</span></span>|<span data-ttu-id="a26a0-341">unsigned int</span><span class="sxs-lookup"><span data-stu-id="a26a0-341">unsigned int</span></span>|<span data-ttu-id="a26a0-342">4</span><span class="sxs-lookup"><span data-stu-id="a26a0-342">4</span></span>||  
|<span data-ttu-id="a26a0-343">**MQCIH_NextTransactionId**</span><span class="sxs-lookup"><span data-stu-id="a26a0-343">**MQCIH_NextTransactionId**</span></span>|<span data-ttu-id="a26a0-344">string</span><span class="sxs-lookup"><span data-stu-id="a26a0-344">string</span></span>|<span data-ttu-id="a26a0-345">4</span><span class="sxs-lookup"><span data-stu-id="a26a0-345">4</span></span>||  
|<span data-ttu-id="a26a0-346">**MQCIH_OutputDataLength**</span><span class="sxs-lookup"><span data-stu-id="a26a0-346">**MQCIH_OutputDataLength**</span></span>|<span data-ttu-id="a26a0-347">unsigned int</span><span class="sxs-lookup"><span data-stu-id="a26a0-347">unsigned int</span></span>|<span data-ttu-id="a26a0-348">4</span><span class="sxs-lookup"><span data-stu-id="a26a0-348">4</span></span>||  
|<span data-ttu-id="a26a0-349">**MQCIH_Reason**</span><span class="sxs-lookup"><span data-stu-id="a26a0-349">**MQCIH_Reason**</span></span>|<span data-ttu-id="a26a0-350">unsigned int</span><span class="sxs-lookup"><span data-stu-id="a26a0-350">unsigned int</span></span>|<span data-ttu-id="a26a0-351">4</span><span class="sxs-lookup"><span data-stu-id="a26a0-351">4</span></span>||  
|<span data-ttu-id="a26a0-352">**MQCIH_ReplyToFormat**</span><span class="sxs-lookup"><span data-stu-id="a26a0-352">**MQCIH_ReplyToFormat**</span></span>|<span data-ttu-id="a26a0-353">string</span><span class="sxs-lookup"><span data-stu-id="a26a0-353">string</span></span>|||  
|<span data-ttu-id="a26a0-354">**MQCIH_ReturnCode**</span><span class="sxs-lookup"><span data-stu-id="a26a0-354">**MQCIH_ReturnCode**</span></span>|<span data-ttu-id="a26a0-355">unsigned int</span><span class="sxs-lookup"><span data-stu-id="a26a0-355">unsigned int</span></span>|<span data-ttu-id="a26a0-356">4</span><span class="sxs-lookup"><span data-stu-id="a26a0-356">4</span></span>||  
|<span data-ttu-id="a26a0-357">**MQCIH_StartCode**</span><span class="sxs-lookup"><span data-stu-id="a26a0-357">**MQCIH_StartCode**</span></span>|<span data-ttu-id="a26a0-358">string</span><span class="sxs-lookup"><span data-stu-id="a26a0-358">string</span></span>|<span data-ttu-id="a26a0-359">4</span><span class="sxs-lookup"><span data-stu-id="a26a0-359">4</span></span>||  
|<span data-ttu-id="a26a0-360">**MQCIH_TaskEndStatus**</span><span class="sxs-lookup"><span data-stu-id="a26a0-360">**MQCIH_TaskEndStatus**</span></span>|<span data-ttu-id="a26a0-361">unsigned int</span><span class="sxs-lookup"><span data-stu-id="a26a0-361">unsigned int</span></span>|<span data-ttu-id="a26a0-362">4</span><span class="sxs-lookup"><span data-stu-id="a26a0-362">4</span></span>||  
|<span data-ttu-id="a26a0-363">**MQCIH_TransactionId**</span><span class="sxs-lookup"><span data-stu-id="a26a0-363">**MQCIH_TransactionId**</span></span>|<span data-ttu-id="a26a0-364">string</span><span class="sxs-lookup"><span data-stu-id="a26a0-364">string</span></span>|<span data-ttu-id="a26a0-365">4</span><span class="sxs-lookup"><span data-stu-id="a26a0-365">4</span></span>||  
|<span data-ttu-id="a26a0-366">**MQCIH_UOWControl**</span><span class="sxs-lookup"><span data-stu-id="a26a0-366">**MQCIH_UOWControl**</span></span>|<span data-ttu-id="a26a0-367">unsigned int</span><span class="sxs-lookup"><span data-stu-id="a26a0-367">unsigned int</span></span>|<span data-ttu-id="a26a0-368">4</span><span class="sxs-lookup"><span data-stu-id="a26a0-368">4</span></span>||  
|<span data-ttu-id="a26a0-369">**MQIIH_Authenticator**</span><span class="sxs-lookup"><span data-stu-id="a26a0-369">**MQIIH_Authenticator**</span></span>|<span data-ttu-id="a26a0-370">string</span><span class="sxs-lookup"><span data-stu-id="a26a0-370">string</span></span>|<span data-ttu-id="a26a0-371">8</span><span class="sxs-lookup"><span data-stu-id="a26a0-371">8</span></span>|<span data-ttu-id="a26a0-372">使用すると、SSO パスワードに設定、 **SSOAffiliateApplication**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="a26a0-372">Set to the SSO password when you use the **SSOAffiliateApplication** property.</span></span> <span data-ttu-id="a26a0-373">**注:** この値は、SSO パスワードの長さが 8 文字を超える場合は、MQSeries アダプターが空白に設定されます。</span><span class="sxs-lookup"><span data-stu-id="a26a0-373">**Note:**  This value will be set to blank by the MQSeries adapter if length of the SSO password exceeds 8 characters.</span></span>|  
|<span data-ttu-id="a26a0-374">**MQIIH_CommitMode**</span><span class="sxs-lookup"><span data-stu-id="a26a0-374">**MQIIH_CommitMode**</span></span>|<span data-ttu-id="a26a0-375">string</span><span class="sxs-lookup"><span data-stu-id="a26a0-375">string</span></span>|||  
|<span data-ttu-id="a26a0-376">**MQIIH_Flags**</span><span class="sxs-lookup"><span data-stu-id="a26a0-376">**MQIIH_Flags**</span></span>|<span data-ttu-id="a26a0-377">unsigned int</span><span class="sxs-lookup"><span data-stu-id="a26a0-377">unsigned int</span></span>|<span data-ttu-id="a26a0-378">4</span><span class="sxs-lookup"><span data-stu-id="a26a0-378">4</span></span>||  
|<span data-ttu-id="a26a0-379">**MQIIH_Format**</span><span class="sxs-lookup"><span data-stu-id="a26a0-379">**MQIIH_Format**</span></span>|<span data-ttu-id="a26a0-380">string</span><span class="sxs-lookup"><span data-stu-id="a26a0-380">string</span></span>|||  
|<span data-ttu-id="a26a0-381">**MQIIH_LTermOverride**</span><span class="sxs-lookup"><span data-stu-id="a26a0-381">**MQIIH_LTermOverride**</span></span>|<span data-ttu-id="a26a0-382">string</span><span class="sxs-lookup"><span data-stu-id="a26a0-382">string</span></span>|<span data-ttu-id="a26a0-383">8</span><span class="sxs-lookup"><span data-stu-id="a26a0-383">8</span></span>||  
|<span data-ttu-id="a26a0-384">**MQIIH_MFSMapName**</span><span class="sxs-lookup"><span data-stu-id="a26a0-384">**MQIIH_MFSMapName**</span></span>|<span data-ttu-id="a26a0-385">string</span><span class="sxs-lookup"><span data-stu-id="a26a0-385">string</span></span>|<span data-ttu-id="a26a0-386">8</span><span class="sxs-lookup"><span data-stu-id="a26a0-386">8</span></span>||  
|<span data-ttu-id="a26a0-387">**MQIIH_ReplyToFormat**</span><span class="sxs-lookup"><span data-stu-id="a26a0-387">**MQIIH_ReplyToFormat**</span></span>|<span data-ttu-id="a26a0-388">string</span><span class="sxs-lookup"><span data-stu-id="a26a0-388">string</span></span>|||  
|<span data-ttu-id="a26a0-389">**MQIIH_SecurityScope**</span><span class="sxs-lookup"><span data-stu-id="a26a0-389">**MQIIH_SecurityScope**</span></span>|<span data-ttu-id="a26a0-390">string</span><span class="sxs-lookup"><span data-stu-id="a26a0-390">string</span></span>|||  
|<span data-ttu-id="a26a0-391">**MQIIH_TranInstanceId**</span><span class="sxs-lookup"><span data-stu-id="a26a0-391">**MQIIH_TranInstanceId**</span></span>|<span data-ttu-id="a26a0-392">string</span><span class="sxs-lookup"><span data-stu-id="a26a0-392">string</span></span>|<span data-ttu-id="a26a0-393">32</span><span class="sxs-lookup"><span data-stu-id="a26a0-393">32</span></span>|<span data-ttu-id="a26a0-394">16 進数文字列</span><span class="sxs-lookup"><span data-stu-id="a26a0-394">Hexadecimal string</span></span>|  
|<span data-ttu-id="a26a0-395">**MQIIH_TranState**</span><span class="sxs-lookup"><span data-stu-id="a26a0-395">**MQIIH_TranState**</span></span>|<span data-ttu-id="a26a0-396">string</span><span class="sxs-lookup"><span data-stu-id="a26a0-396">string</span></span>|||  
  
## <a name="see-also"></a><span data-ttu-id="a26a0-397">参照</span><span class="sxs-lookup"><span data-stu-id="a26a0-397">See Also</span></span>  
 <span data-ttu-id="a26a0-398">[MQSeries アダプターのプロパティ](../core/mqseries-adapter-properties.md) </span><span class="sxs-lookup"><span data-stu-id="a26a0-398">[MQSeries Adapter Properties](../core/mqseries-adapter-properties.md) </span></span>  
 <span data-ttu-id="a26a0-399">[BizTalk Server に関連するプロパティ](../core/properties-related-to-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="a26a0-399">[Properties Related to BizTalk Server](../core/properties-related-to-biztalk-server.md) </span></span>  
 [<span data-ttu-id="a26a0-400">プロパティのデータ型変換</span><span class="sxs-lookup"><span data-stu-id="a26a0-400">Data Type Conversion of Properties</span></span>](../core/data-type-conversion-of-properties.md)