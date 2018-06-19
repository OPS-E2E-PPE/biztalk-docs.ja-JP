---
title: EDI ヘッダーをオーバーライドする |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 16c19d3d-eab2-4d44-8752-25aeadb537a4
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 510a3817d0fd99d43b6da9462c74dd8bc7c1bdf0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22265442"
---
# <a name="overriding-edi-headers"></a><span data-ttu-id="cf05c-102">EDI ヘッダーの上書き</span><span class="sxs-lookup"><span data-stu-id="cf05c-102">Overriding EDI Headers</span></span>
<span data-ttu-id="cf05c-103">EDI エンコード インターチェンジを送信する場合、メッセージに適用される EDI エンベロープは、通常、受信アグリーメントの EDI プロパティに、またはフォールバック アグリーメントのプロパティに基づきます。</span><span class="sxs-lookup"><span data-stu-id="cf05c-103">When sending an EDI-encoded interchange, the EDI envelope applied to the message is normally based upon the EDI properties of the receiving agreement, or the fallback agreement properties.</span></span> <span data-ttu-id="cf05c-104">しかし、多くの場合、ランタイムに生成される値に基づいて EDI エンベロープ プロパティを設定すると便利です。</span><span class="sxs-lookup"><span data-stu-id="cf05c-104">However it is often useful to set the EDI envelope properties based on runtime generated values.</span></span>  
  
 <span data-ttu-id="cf05c-105">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、EdiOverride コンテキスト プロパティを使用して、送信ドキュメントで EDI エンベロープを生成するために使用する値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="cf05c-105">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can use the EdiOverride context properties to specify the values used to generate the EDI envelope on outbound documents.</span></span>  
  
## <a name="using-edioverride-context-properties"></a><span data-ttu-id="cf05c-106">EdiOverride コンテキスト プロパティの使用</span><span class="sxs-lookup"><span data-stu-id="cf05c-106">Using EdiOverride Context Properties</span></span>  
 <span data-ttu-id="cf05c-107">EdiOverride コンテキスト プロパティを使用すると、EDI エンベロープを生成するために使用する値のすべてまたは一部を上書きできます。</span><span class="sxs-lookup"><span data-stu-id="cf05c-107">The EdiOverride context properties provide a way to override all, or part, of the values used to generate the EDI envelope.</span></span> <span data-ttu-id="cf05c-108">EDI 送信パイプラインでは、エンベロープの作成に有効な値を格納する EdiOverride コンテキスト プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="cf05c-108">The EDI send pipeline will use EdiOverride context property that contains a valid value to construct the envelope.</span></span> <span data-ttu-id="cf05c-109">プロパティが設定されていない場合、パイプラインでは、アグリーメントのプロパティまたはフォールバック アグリーメントのプロパティ (アグリーメントが未定義の場合) で指定された値を使用します。</span><span class="sxs-lookup"><span data-stu-id="cf05c-109">If a property is not populated, the pipeline will use the value specified in agreement properties or fallback agreement properties, if an agreement is not defined.</span></span> <span data-ttu-id="cf05c-110">プロパティに無効な値が指定されている場合は、パイプラインではメッセージが中断し、検証エラーが報告されます。</span><span class="sxs-lookup"><span data-stu-id="cf05c-110">If a property contains an invalid value, the pipeline will suspend the message and report a validation error.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf05c-111">EdiOverride コレクションで指定された値が使用されるのは、`EdiOverride.OverrideEdiHeader` プロパティがメッセージのコンテキストに書き込まれ、値 "True" が指定されている場合のみです。</span><span class="sxs-lookup"><span data-stu-id="cf05c-111">The values specified in the EdiOverride collection are only used if the `EdiOverride.OverrideEdiHeader` property is written into the context of a message and contains a value of “True”.</span></span>  
>   
>  <span data-ttu-id="cf05c-112">既定では設定されません。</span><span class="sxs-lookup"><span data-stu-id="cf05c-112">The default value is not set.</span></span>  
  
### <a name="edioverride-properties-for-x12-envelope-values"></a><span data-ttu-id="cf05c-113">X12 エンベロープ値の EdiOverride プロパティ</span><span class="sxs-lookup"><span data-stu-id="cf05c-113">EdiOverride properties for X12 Envelope Values</span></span>  
 <span data-ttu-id="cf05c-114">次の表に、EdiOverride コンテキスト プロパティ、および対応する X12 エンベロープ ヘッダーを示します。</span><span class="sxs-lookup"><span data-stu-id="cf05c-114">The following table shows the EdiOverride context properties and the corresponding X12 envelope header:</span></span>  
  
|<span data-ttu-id="cf05c-115">Header</span><span class="sxs-lookup"><span data-stu-id="cf05c-115">Header</span></span>|<span data-ttu-id="cf05c-116">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="cf05c-116">Properties</span></span>|  
|------------|----------------|  
|<span data-ttu-id="cf05c-117">インターチェンジ制御ヘッダー (ISA)</span><span class="sxs-lookup"><span data-stu-id="cf05c-117">Interchange Control Header (ISA)</span></span>|<span data-ttu-id="cf05c-118">ISA01、ISA02、ISA03、ISA04、ISA05、ISA06、ISA07、ISA08、ISA09、ISA10、ISA11、ISA12、ISA13、ISA14、ISA15、ISA16</span><span class="sxs-lookup"><span data-stu-id="cf05c-118">ISA01, ISA02, ISA03, ISA04, ISA05, ISA06, ISA07, ISA08, ISA09, ISA10, ISA11, ISA12, ISA13, ISA14, ISA15, ISA16</span></span>|  
|<span data-ttu-id="cf05c-119">機能グループ ヘッダー (GS)</span><span class="sxs-lookup"><span data-stu-id="cf05c-119">Functional Group Headers (GS)</span></span>|<span data-ttu-id="cf05c-120">GS01、GS02、GS03、GS04、GS05、GS06、GS07、GS08</span><span class="sxs-lookup"><span data-stu-id="cf05c-120">GS01, GS02, GS03, GS04, GS05, GS06, GS07, GS08</span></span>|  
|<span data-ttu-id="cf05c-121">トランザクション セット ヘッダー</span><span class="sxs-lookup"><span data-stu-id="cf05c-121">Transaction Set Header</span></span>|<span data-ttu-id="cf05c-122">ST02</span><span class="sxs-lookup"><span data-stu-id="cf05c-122">ST02</span></span>|  
  
### <a name="edioverride-properties-for-edifact-envelope-values"></a><span data-ttu-id="cf05c-123">EDIFACT エンベロープ値の EdiOverride プロパティ</span><span class="sxs-lookup"><span data-stu-id="cf05c-123">EdiOverride properties for EDIFACT Envelope Values</span></span>  
 <span data-ttu-id="cf05c-124">次の表に、EdiOverride コンテキスト プロパティ、および対応する EDIFACT エンベロープ セグメントを示します。</span><span class="sxs-lookup"><span data-stu-id="cf05c-124">The following table shows the EdiOverride context properties and the corresponding EDIFACT envelope segment:</span></span>  
  
|<span data-ttu-id="cf05c-125">Segment</span><span class="sxs-lookup"><span data-stu-id="cf05c-125">Segment</span></span>|<span data-ttu-id="cf05c-126">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="cf05c-126">Properties</span></span>|  
|-------------|----------------|  
|<span data-ttu-id="cf05c-127">文字列サービス通知 (UNA)</span><span class="sxs-lookup"><span data-stu-id="cf05c-127">Service String Advice (UNA)</span></span>|<span data-ttu-id="cf05c-128">UNA1、UNA2、UNA3、UNA4、UNA5、UNA6、UNA6Suffix</span><span class="sxs-lookup"><span data-stu-id="cf05c-128">UNA1, UNA2, UNA3, UNA4, UNA5, UNA6, UNA6Suffix</span></span>|  
|<span data-ttu-id="cf05c-129">インターチェンジ制御ヘッダー (UNB)</span><span class="sxs-lookup"><span data-stu-id="cf05c-129">Interchange Control Header (UNB)</span></span>|<span data-ttu-id="cf05c-130">UNB1_1、UNB1_2、UNB2_1、UNB2_2、UNB2_3、UNB3_1、UNB3_2、UNB3_3、UNB4_1、UNB4_2、UNB5、UNB6_1、UNB7、UNB8、UNB9、UNB10、UNB11</span><span class="sxs-lookup"><span data-stu-id="cf05c-130">UNB1_1, UNB1_2, UNB2_1, UNB2_2, UNB2_3, UNB3_1, UNB3_2, UNB3_3, UNB4_1, UNB4_2, UNB5, UNB6_1, UNB7, UNB8, UNB9, UNB10, UNB11</span></span>|  
|<span data-ttu-id="cf05c-131">機能グループ ヘッダー (UNG)</span><span class="sxs-lookup"><span data-stu-id="cf05c-131">Functional Group Headers (UNG)</span></span>|<span data-ttu-id="cf05c-132">UNG1、UNG2_1、UNG2_2、UNG3_1、UNG3_2、UNG4_1、UNG4_2、UNG5、UNG6、UNG7_1、UNG7_2、UNG7_3、UNG8</span><span class="sxs-lookup"><span data-stu-id="cf05c-132">UNG1, UNG2_1, UNG2_2, UNG3_1, UNG3_2, UNG4_1, UNG4_2, UNG5, UNG6, UNG7_1, UNG7_2, UNG7_3, UNG8</span></span>|  
|<span data-ttu-id="cf05c-133">メッセージ ヘッダー (UNH)</span><span class="sxs-lookup"><span data-stu-id="cf05c-133">Message Header (UNH)</span></span>|<span data-ttu-id="cf05c-134">UNH1</span><span class="sxs-lookup"><span data-stu-id="cf05c-134">UNH1</span></span>|  
  
 <span data-ttu-id="cf05c-135">判断するかどうかはこれらのヘッダーに関係なく、生成された、GenerateUNA プロパティと GenerateUNG プロパティを使用できます、UNA セグメントと UNG EDIFACT セグメントは省略可能なにあるため、 **UNA セグメントを適用**アグリーメント設定します。</span><span class="sxs-lookup"><span data-stu-id="cf05c-135">Since the UNA and UNG EDIFACT segments are optional, the GenerateUNA and GenerateUNG properties can be used to determine if these headers are generated, regardless of the **Apply UNA segment** agreement setting.</span></span> <span data-ttu-id="cf05c-136">次の表には、これらのセグメントの生成の結果の値を示します。</span><span class="sxs-lookup"><span data-stu-id="cf05c-136">The following tables show the values that result in generation of these segments:</span></span>  
  
|<span data-ttu-id="cf05c-137">GenerateUNA コンテキスト プロパティ</span><span class="sxs-lookup"><span data-stu-id="cf05c-137">GenerateUNA context property</span></span>|<span data-ttu-id="cf05c-138">[UNA セグメントを適用する] アグリーメント設定</span><span class="sxs-lookup"><span data-stu-id="cf05c-138">Apply UNA segment agreement setting</span></span>|<span data-ttu-id="cf05c-139">エンジンの動作</span><span class="sxs-lookup"><span data-stu-id="cf05c-139">Engine behavior</span></span>|  
|----------------------------------|-----------------------------------------|---------------------|  
|<span data-ttu-id="cf05c-140">TRUE</span><span class="sxs-lookup"><span data-stu-id="cf05c-140">TRUE</span></span>|<span data-ttu-id="cf05c-141">CHECKED</span><span class="sxs-lookup"><span data-stu-id="cf05c-141">CHECKED</span></span>|<span data-ttu-id="cf05c-142">UNA を生成する</span><span class="sxs-lookup"><span data-stu-id="cf05c-142">Generate UNA</span></span>|  
|<span data-ttu-id="cf05c-143">TRUE</span><span class="sxs-lookup"><span data-stu-id="cf05c-143">TRUE</span></span>|<span data-ttu-id="cf05c-144">UNCHECKED</span><span class="sxs-lookup"><span data-stu-id="cf05c-144">UNCHECKED</span></span>|<span data-ttu-id="cf05c-145">UNA を生成する</span><span class="sxs-lookup"><span data-stu-id="cf05c-145">Generate UNA</span></span>|  
|<span data-ttu-id="cf05c-146">FALSE</span><span class="sxs-lookup"><span data-stu-id="cf05c-146">FALSE</span></span>|<span data-ttu-id="cf05c-147">CHECKED</span><span class="sxs-lookup"><span data-stu-id="cf05c-147">CHECKED</span></span>|<span data-ttu-id="cf05c-148">UNA を生成しない</span><span class="sxs-lookup"><span data-stu-id="cf05c-148">Do not generate UNA</span></span>|  
|<span data-ttu-id="cf05c-149">FALSE</span><span class="sxs-lookup"><span data-stu-id="cf05c-149">FALSE</span></span>|<span data-ttu-id="cf05c-150">UNCHECKED</span><span class="sxs-lookup"><span data-stu-id="cf05c-150">UNCHECKED</span></span>|<span data-ttu-id="cf05c-151">UNA を生成しない</span><span class="sxs-lookup"><span data-stu-id="cf05c-151">Do not generate UNA</span></span>|  
|<span data-ttu-id="cf05c-152">存在しない (OverrideEDIHeader が false)</span><span class="sxs-lookup"><span data-stu-id="cf05c-152">Not present (OverrideEDIHeader is false)</span></span>|<span data-ttu-id="cf05c-153">CHECKED</span><span class="sxs-lookup"><span data-stu-id="cf05c-153">CHECKED</span></span>|<span data-ttu-id="cf05c-154">UNA を生成する</span><span class="sxs-lookup"><span data-stu-id="cf05c-154">Generate UNA</span></span>|  
|<span data-ttu-id="cf05c-155">存在しない (OverrideEDIHeader が false)</span><span class="sxs-lookup"><span data-stu-id="cf05c-155">Not present (OverrideEDIHeader is false)</span></span>|<span data-ttu-id="cf05c-156">UNCHECKED</span><span class="sxs-lookup"><span data-stu-id="cf05c-156">UNCHECKED</span></span>|<span data-ttu-id="cf05c-157">UNA を生成しない</span><span class="sxs-lookup"><span data-stu-id="cf05c-157">Do not generate UNA</span></span>|  
  
|<span data-ttu-id="cf05c-158">GenerateUNG コンテキスト プロパティ</span><span class="sxs-lookup"><span data-stu-id="cf05c-158">GenerateUNG context property</span></span>|<span data-ttu-id="cf05c-159">[UNG セグメントを適用する] アグリーメント設定</span><span class="sxs-lookup"><span data-stu-id="cf05c-159">Apply UNG segments agreement setting</span></span>|<span data-ttu-id="cf05c-160">エンジンの動作</span><span class="sxs-lookup"><span data-stu-id="cf05c-160">Engine behavior</span></span>|  
|----------------------------------|------------------------------------------|---------------------|  
|<span data-ttu-id="cf05c-161">TRUE</span><span class="sxs-lookup"><span data-stu-id="cf05c-161">TRUE</span></span>|<span data-ttu-id="cf05c-162">CHECKED</span><span class="sxs-lookup"><span data-stu-id="cf05c-162">CHECKED</span></span>|<span data-ttu-id="cf05c-163">UNG を生成する</span><span class="sxs-lookup"><span data-stu-id="cf05c-163">Generate UNG</span></span>|  
|<span data-ttu-id="cf05c-164">TRUE</span><span class="sxs-lookup"><span data-stu-id="cf05c-164">TRUE</span></span>|<span data-ttu-id="cf05c-165">UNCHECKED</span><span class="sxs-lookup"><span data-stu-id="cf05c-165">UNCHECKED</span></span>|<span data-ttu-id="cf05c-166">UNG を生成する</span><span class="sxs-lookup"><span data-stu-id="cf05c-166">Generate UNG</span></span>|  
|<span data-ttu-id="cf05c-167">FALSE</span><span class="sxs-lookup"><span data-stu-id="cf05c-167">FALSE</span></span>|<span data-ttu-id="cf05c-168">CHECKED</span><span class="sxs-lookup"><span data-stu-id="cf05c-168">CHECKED</span></span>|<span data-ttu-id="cf05c-169">UNG を生成しない</span><span class="sxs-lookup"><span data-stu-id="cf05c-169">Do not generate UNG</span></span>|  
|<span data-ttu-id="cf05c-170">FALSE</span><span class="sxs-lookup"><span data-stu-id="cf05c-170">FALSE</span></span>|<span data-ttu-id="cf05c-171">UNCHECKED</span><span class="sxs-lookup"><span data-stu-id="cf05c-171">UNCHECKED</span></span>|<span data-ttu-id="cf05c-172">UNG を生成しない</span><span class="sxs-lookup"><span data-stu-id="cf05c-172">Do not generate UNG</span></span>|  
|<span data-ttu-id="cf05c-173">存在しない (OverrideEDIHeader が false)</span><span class="sxs-lookup"><span data-stu-id="cf05c-173">Not present (OverrideEDIHeader is false)</span></span>|<span data-ttu-id="cf05c-174">CHECKED</span><span class="sxs-lookup"><span data-stu-id="cf05c-174">CHECKED</span></span>|<span data-ttu-id="cf05c-175">UNG を生成する</span><span class="sxs-lookup"><span data-stu-id="cf05c-175">Generate UNG</span></span>|  
|<span data-ttu-id="cf05c-176">存在しない (OverrideEDIHeader が false)</span><span class="sxs-lookup"><span data-stu-id="cf05c-176">Not present (OverrideEDIHeader is false)</span></span>|<span data-ttu-id="cf05c-177">UNCHECKED</span><span class="sxs-lookup"><span data-stu-id="cf05c-177">UNCHECKED</span></span>|<span data-ttu-id="cf05c-178">UNG を生成しない</span><span class="sxs-lookup"><span data-stu-id="cf05c-178">Do not generate UNG</span></span>|  
  
### <a name="group-envelopes"></a><span data-ttu-id="cf05c-179">グループ エンベロープ</span><span class="sxs-lookup"><span data-stu-id="cf05c-179">Group envelopes</span></span>  
 <span data-ttu-id="cf05c-180">インターチェンジには複数のグループが含まれる場合があるため、グループ エンベロープには特殊な課題があります。</span><span class="sxs-lookup"><span data-stu-id="cf05c-180">Group envelopes present a special challenge, as the interchange can have more than one group present.</span></span> <span data-ttu-id="cf05c-181">この課題に対応するために、EDI 送信パイプラインは、インターチェンジ内のすべてのグループにエンベロープを適用することも、インターチェンジ内の唯一のグループにエンベロープを適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="cf05c-181">To address this, the EDI send pipeline can either apply the envelope to all groups in the interchange, or apply the envelope to the only group in the interchange.</span></span>  
  
 <span data-ttu-id="cf05c-182">単一のトランザクションでは、すべての GS または UNG フィールドを上書きできます。バッチ インターチェンジの場合にのみ、次のフィールドを上書きできます。</span><span class="sxs-lookup"><span data-stu-id="cf05c-182">For single transactions, all GS or UNG fields can be overridden, for batch interchanges only the following fields can be overridden:</span></span>  
  
-   <span data-ttu-id="cf05c-183">GS04</span><span class="sxs-lookup"><span data-stu-id="cf05c-183">GS04</span></span>  
  
-   <span data-ttu-id="cf05c-184">GS05</span><span class="sxs-lookup"><span data-stu-id="cf05c-184">GS05</span></span>  
  
-   <span data-ttu-id="cf05c-185">UNG4_1</span><span class="sxs-lookup"><span data-stu-id="cf05c-185">UNG4_1</span></span>  
  
-   <span data-ttu-id="cf05c-186">UNG4_2</span><span class="sxs-lookup"><span data-stu-id="cf05c-186">UNG4_2</span></span>  
  
### <a name="batching"></a><span data-ttu-id="cf05c-187">バッチ処理</span><span class="sxs-lookup"><span data-stu-id="cf05c-187">Batching</span></span>  
 <span data-ttu-id="cf05c-188">バッチ処理されたメッセージのトランザクション セット制御番号は、バッチ処理オーケストレーションで処理されます。</span><span class="sxs-lookup"><span data-stu-id="cf05c-188">Overriding the transaction set control number for batched messages is handled by the Batching orchestration.</span></span> <span data-ttu-id="cf05c-189">次のプロパティは、トランザクション セット制御番号の上書きをバッチ処理するために、任意のメッセージのコンテキストに書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="cf05c-189">The following properties can be written to the context of any message that will be batched to override the transaction set control number:</span></span>  
  
-   <span data-ttu-id="cf05c-190">ST02 (X12 メッセージの場合)</span><span class="sxs-lookup"><span data-stu-id="cf05c-190">ST02 (for X12 messages)</span></span>  
  
-   <span data-ttu-id="cf05c-191">UNH1 (EDIFACT メッセージの場合)</span><span class="sxs-lookup"><span data-stu-id="cf05c-191">UNH1 (For EDIFACT messages</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf05c-192">複数の受信メッセージに同じグループの同じ制御番号が含まれる場合、重複した番号のメッセージは中断されます。</span><span class="sxs-lookup"><span data-stu-id="cf05c-192">If multiple incoming messages contain the same control number in the same group, messages with duplicate numbers will be suspended.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf05c-193">バッチ処理するメッセージの EdiOverride コンテキスト プロパティ ISA、UNA、GS、UNG は昇格させないでください。</span><span class="sxs-lookup"><span data-stu-id="cf05c-193">Do not promote the EdiOverride context properties ISA, UNA, GS, or UNG for messages that are to be batched.</span></span> <span data-ttu-id="cf05c-194">これらのプロパティを上書きする必要がある場合は、EDI 送信パイプラインに送信する前にバッチ オーケストレーションの出力メッセージで昇格してください。</span><span class="sxs-lookup"><span data-stu-id="cf05c-194">If you need to override these properties, promote them on the output message of the batch orchestration before sending to the EDI send pipeline.</span></span>  
  
### <a name="delimiter-collision"></a><span data-ttu-id="cf05c-195">区切り記号の競合</span><span class="sxs-lookup"><span data-stu-id="cf05c-195">Delimiter collision</span></span>  
 <span data-ttu-id="cf05c-196">UNA ヘッダーなどの区切り記号には、フィールドごとに一意な値が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf05c-196">Delimiters, such as the UNA headers, must contain a unique value for each field.</span></span> <span data-ttu-id="cf05c-197">UNA ヘッダーなどの区切り記号の値を上書きする場合は、上書きする値内だけではなく、アグリーメントまたはフォールバック アグリーメント設定から使用するすべての区切り記号値間でも、各区切り記号値が一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf05c-197">When overriding delimiter values, such as the UNA headers, you must ensure that each delimiter value is unique not only within the values you override, but also among any delimiter values used from the agreement or fallback agreement settings.</span></span>  
  
 <span data-ttu-id="cf05c-198">たとえば、UNA1、UNA2、UNA4 を上書きし、UNA3、UNA5、UNA6、UNA6Suffix がアグリーメントのプロパティから取得される場合、各プロパティには他と比較して一意な値が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf05c-198">For example, if you override UNA1, UNA2, and UNA4, and UNA3, UNA5, UNA6 and UNA6Suffix come from agreement properties, each property must contain a unique value compared to the others.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf05c-199">参照</span><span class="sxs-lookup"><span data-stu-id="cf05c-199">See Also</span></span>  
 [<span data-ttu-id="cf05c-200">BizTalk Server が EDI メッセージを送信する方法</span><span class="sxs-lookup"><span data-stu-id="cf05c-200">How BizTalk Server Sends EDI Messages</span></span>](../core/how-biztalk-server-sends-edi-messages.md)