---
title: EDI ヘッダーの上書き |Microsoft Docs
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
ms.openlocfilehash: e768bb992497651a14558895e4bedf2dbff692fc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393369"
---
# <a name="overriding-edi-headers"></a><span data-ttu-id="d9ab1-102">EDI ヘッダーのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="d9ab1-102">Overriding EDI Headers</span></span>
<span data-ttu-id="d9ab1-103">EDI でエンコードされたインターチェンジを送信するときに、メッセージに適用される EDI エンベロープは通常、受信側アグリーメントの EDI のプロパティまたはフォールバック アグリーメントのプロパティに基づきます。</span><span class="sxs-lookup"><span data-stu-id="d9ab1-103">When sending an EDI-encoded interchange, the EDI envelope applied to the message is normally based upon the EDI properties of the receiving agreement, or the fallback agreement properties.</span></span> <span data-ttu-id="d9ab1-104">ただしの値を生成をランタイムに基づく EDI エンベロープのプロパティを設定すると便利です。</span><span class="sxs-lookup"><span data-stu-id="d9ab1-104">However it is often useful to set the EDI envelope properties based on runtime generated values.</span></span>  
  
 <span data-ttu-id="d9ab1-105">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、EdiOverride コンテキスト プロパティを使用して、送信ドキュメントで EDI エンベロープの生成に使用される値を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="d9ab1-105">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can use the EdiOverride context properties to specify the values used to generate the EDI envelope on outbound documents.</span></span>  
  
## <a name="using-edioverride-context-properties"></a><span data-ttu-id="d9ab1-106">EdiOverride コンテキスト プロパティの使用</span><span class="sxs-lookup"><span data-stu-id="d9ab1-106">Using EdiOverride Context Properties</span></span>  
 <span data-ttu-id="d9ab1-107">EdiOverride コンテキスト プロパティは、EDI エンベロープの生成に使用される値の一部またはすべてを上書きする方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="d9ab1-107">The EdiOverride context properties provide a way to override all, or part, of the values used to generate the EDI envelope.</span></span> <span data-ttu-id="d9ab1-108">EDI 送信パイプラインでは、エンベロープを構築する有効な値を格納する EdiOverride コンテキスト プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="d9ab1-108">The EDI send pipeline will use EdiOverride context property that contains a valid value to construct the envelope.</span></span> <span data-ttu-id="d9ab1-109">プロパティが設定されていない場合、アグリーメントが定義されていない場合、パイプラインはアグリーメントのプロパティまたはフォールバック アグリーメントのプロパティで指定された値を使用します。</span><span class="sxs-lookup"><span data-stu-id="d9ab1-109">If a property is not populated, the pipeline will use the value specified in agreement properties or fallback agreement properties, if an agreement is not defined.</span></span> <span data-ttu-id="d9ab1-110">プロパティに無効な値が含まれている場合、パイプラインがメッセージを中断し、検証エラーを報告します。</span><span class="sxs-lookup"><span data-stu-id="d9ab1-110">If a property contains an invalid value, the pipeline will suspend the message and report a validation error.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d9ab1-111">EdiOverride コレクションで指定された値は、場合にのみ使用されるが、`EdiOverride.OverrideEdiHeader`プロパティは、メッセージのコンテキストに書き込まれ、値"True"が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d9ab1-111">The values specified in the EdiOverride collection are only used if the `EdiOverride.OverrideEdiHeader` property is written into the context of a message and contains a value of “True”.</span></span>  
>   
>  <span data-ttu-id="d9ab1-112">既定値は設定されていません。</span><span class="sxs-lookup"><span data-stu-id="d9ab1-112">The default value is not set.</span></span>  
  
### <a name="edioverride-properties-for-x12-envelope-values"></a><span data-ttu-id="d9ab1-113">EdiOverride プロパティの X12 エンベロープ値</span><span class="sxs-lookup"><span data-stu-id="d9ab1-113">EdiOverride properties for X12 Envelope Values</span></span>  
 <span data-ttu-id="d9ab1-114">次の表は、EdiOverride コンテキスト プロパティと対応する X12 エンベロープ ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="d9ab1-114">The following table shows the EdiOverride context properties and the corresponding X12 envelope header:</span></span>  
  
|<span data-ttu-id="d9ab1-115">[ヘッダー]</span><span class="sxs-lookup"><span data-stu-id="d9ab1-115">Header</span></span>|<span data-ttu-id="d9ab1-116">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d9ab1-116">Properties</span></span>|  
|------------|----------------|  
|<span data-ttu-id="d9ab1-117">インターチェンジ制御ヘッダー (ISA)</span><span class="sxs-lookup"><span data-stu-id="d9ab1-117">Interchange Control Header (ISA)</span></span>|<span data-ttu-id="d9ab1-118">ISA01、ISA02、ISA03、ISA04、ISA05、ISA06、ISA07、ISA08、ISA09、ISA10、ISA11、ISA12、ISA13、ISA14、ISA15、ISA16</span><span class="sxs-lookup"><span data-stu-id="d9ab1-118">ISA01, ISA02, ISA03, ISA04, ISA05, ISA06, ISA07, ISA08, ISA09, ISA10, ISA11, ISA12, ISA13, ISA14, ISA15, ISA16</span></span>|  
|<span data-ttu-id="d9ab1-119">機能グループ ヘッダー (GS)</span><span class="sxs-lookup"><span data-stu-id="d9ab1-119">Functional Group Headers (GS)</span></span>|<span data-ttu-id="d9ab1-120">GS01、GS02、GS03、GS04、GS05、GS06、GS07、GS08</span><span class="sxs-lookup"><span data-stu-id="d9ab1-120">GS01, GS02, GS03, GS04, GS05, GS06, GS07, GS08</span></span>|  
|<span data-ttu-id="d9ab1-121">トランザクション セット ヘッダー</span><span class="sxs-lookup"><span data-stu-id="d9ab1-121">Transaction Set Header</span></span>|<span data-ttu-id="d9ab1-122">ST02</span><span class="sxs-lookup"><span data-stu-id="d9ab1-122">ST02</span></span>|  
  
### <a name="edioverride-properties-for-edifact-envelope-values"></a><span data-ttu-id="d9ab1-123">EDIFACT エンベロープ値の EdiOverride プロパティ</span><span class="sxs-lookup"><span data-stu-id="d9ab1-123">EdiOverride properties for EDIFACT Envelope Values</span></span>  
 <span data-ttu-id="d9ab1-124">次の表に、EdiOverride コンテキスト プロパティと対応する EDIFACT エンベロープ セグメントを示します。</span><span class="sxs-lookup"><span data-stu-id="d9ab1-124">The following table shows the EdiOverride context properties and the corresponding EDIFACT envelope segment:</span></span>  
  
|<span data-ttu-id="d9ab1-125">Segment</span><span class="sxs-lookup"><span data-stu-id="d9ab1-125">Segment</span></span>|<span data-ttu-id="d9ab1-126">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d9ab1-126">Properties</span></span>|  
|-------------|----------------|  
|<span data-ttu-id="d9ab1-127">文字列サービス通知 (UNA)</span><span class="sxs-lookup"><span data-stu-id="d9ab1-127">Service String Advice (UNA)</span></span>|<span data-ttu-id="d9ab1-128">UNA1、UNA2、UNA3、UNA4、UNA5、UNA6、UNA6Suffix</span><span class="sxs-lookup"><span data-stu-id="d9ab1-128">UNA1, UNA2, UNA3, UNA4, UNA5, UNA6, UNA6Suffix</span></span>|  
|<span data-ttu-id="d9ab1-129">インターチェンジ制御ヘッダー (UNB)</span><span class="sxs-lookup"><span data-stu-id="d9ab1-129">Interchange Control Header (UNB)</span></span>|<span data-ttu-id="d9ab1-130">UNB1_1、UNB1_2、UNB2_1、UNB2_2、UNB2_3、UNB3_1、UNB3_2、UNB3_3、UNB4_1、UNB4_2、UNB5、UNB6_1、UNB7、UNB8、UNB9、UNB10、UNB11</span><span class="sxs-lookup"><span data-stu-id="d9ab1-130">UNB1_1, UNB1_2, UNB2_1, UNB2_2, UNB2_3, UNB3_1, UNB3_2, UNB3_3, UNB4_1, UNB4_2, UNB5, UNB6_1, UNB7, UNB8, UNB9, UNB10, UNB11</span></span>|  
|<span data-ttu-id="d9ab1-131">機能グループ ヘッダー (UNG)</span><span class="sxs-lookup"><span data-stu-id="d9ab1-131">Functional Group Headers (UNG)</span></span>|<span data-ttu-id="d9ab1-132">UNG1、UNG2_1、UNG2_2、UNG3_1、UNG3_2、UNG4_1、UNG4_2、UNG5、UNG6、UNG7_1、UNG7_2、UNG7_3、UNG8</span><span class="sxs-lookup"><span data-stu-id="d9ab1-132">UNG1, UNG2_1, UNG2_2, UNG3_1, UNG3_2, UNG4_1, UNG4_2, UNG5, UNG6, UNG7_1, UNG7_2, UNG7_3, UNG8</span></span>|  
|<span data-ttu-id="d9ab1-133">メッセージ ヘッダー (UNH)</span><span class="sxs-lookup"><span data-stu-id="d9ab1-133">Message Header (UNH)</span></span>|<span data-ttu-id="d9ab1-134">UNH1</span><span class="sxs-lookup"><span data-stu-id="d9ab1-134">UNH1</span></span>|  
  
 <span data-ttu-id="d9ab1-135">関係なく、生成されたこれらのヘッダーがかどうかを判断する、GenerateUNA プロパティと GenerateUNG プロパティを使用できます、UNA セグメントと UNG EDIFACT セグメントは省略可能であるため、 **UNA セグメントを適用**アグリーメントの設定。</span><span class="sxs-lookup"><span data-stu-id="d9ab1-135">Since the UNA and UNG EDIFACT segments are optional, the GenerateUNA and GenerateUNG properties can be used to determine if these headers are generated, regardless of the **Apply UNA segment** agreement setting.</span></span> <span data-ttu-id="d9ab1-136">次の表は、これらのセグメントのジェネレーションで結果の値を示します。</span><span class="sxs-lookup"><span data-stu-id="d9ab1-136">The following tables show the values that result in generation of these segments:</span></span>  
  
|<span data-ttu-id="d9ab1-137">GenerateUNA コンテキスト プロパティ</span><span class="sxs-lookup"><span data-stu-id="d9ab1-137">GenerateUNA context property</span></span>|<span data-ttu-id="d9ab1-138">UNA セグメントのアグリーメント設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="d9ab1-138">Apply UNA segment agreement setting</span></span>|<span data-ttu-id="d9ab1-139">エンジンの動作</span><span class="sxs-lookup"><span data-stu-id="d9ab1-139">Engine behavior</span></span>|  
|----------------------------------|-----------------------------------------|---------------------|  
|<span data-ttu-id="d9ab1-140">TRUE</span><span class="sxs-lookup"><span data-stu-id="d9ab1-140">TRUE</span></span>|<span data-ttu-id="d9ab1-141">チェック</span><span class="sxs-lookup"><span data-stu-id="d9ab1-141">CHECKED</span></span>|<span data-ttu-id="d9ab1-142">UNA を生成します。</span><span class="sxs-lookup"><span data-stu-id="d9ab1-142">Generate UNA</span></span>|  
|<span data-ttu-id="d9ab1-143">TRUE</span><span class="sxs-lookup"><span data-stu-id="d9ab1-143">TRUE</span></span>|<span data-ttu-id="d9ab1-144">オフ</span><span class="sxs-lookup"><span data-stu-id="d9ab1-144">UNCHECKED</span></span>|<span data-ttu-id="d9ab1-145">UNA を生成します。</span><span class="sxs-lookup"><span data-stu-id="d9ab1-145">Generate UNA</span></span>|  
|<span data-ttu-id="d9ab1-146">FALSE</span><span class="sxs-lookup"><span data-stu-id="d9ab1-146">FALSE</span></span>|<span data-ttu-id="d9ab1-147">チェック</span><span class="sxs-lookup"><span data-stu-id="d9ab1-147">CHECKED</span></span>|<span data-ttu-id="d9ab1-148">UNA を生成しません。</span><span class="sxs-lookup"><span data-stu-id="d9ab1-148">Do not generate UNA</span></span>|  
|<span data-ttu-id="d9ab1-149">FALSE</span><span class="sxs-lookup"><span data-stu-id="d9ab1-149">FALSE</span></span>|<span data-ttu-id="d9ab1-150">オフ</span><span class="sxs-lookup"><span data-stu-id="d9ab1-150">UNCHECKED</span></span>|<span data-ttu-id="d9ab1-151">UNA を生成しません。</span><span class="sxs-lookup"><span data-stu-id="d9ab1-151">Do not generate UNA</span></span>|  
|<span data-ttu-id="d9ab1-152">存在しない (OverrideEDIHeader が false)</span><span class="sxs-lookup"><span data-stu-id="d9ab1-152">Not present (OverrideEDIHeader is false)</span></span>|<span data-ttu-id="d9ab1-153">チェック</span><span class="sxs-lookup"><span data-stu-id="d9ab1-153">CHECKED</span></span>|<span data-ttu-id="d9ab1-154">UNA を生成します。</span><span class="sxs-lookup"><span data-stu-id="d9ab1-154">Generate UNA</span></span>|  
|<span data-ttu-id="d9ab1-155">存在しない (OverrideEDIHeader が false)</span><span class="sxs-lookup"><span data-stu-id="d9ab1-155">Not present (OverrideEDIHeader is false)</span></span>|<span data-ttu-id="d9ab1-156">オフ</span><span class="sxs-lookup"><span data-stu-id="d9ab1-156">UNCHECKED</span></span>|<span data-ttu-id="d9ab1-157">UNA を生成しません。</span><span class="sxs-lookup"><span data-stu-id="d9ab1-157">Do not generate UNA</span></span>|  
  
|<span data-ttu-id="d9ab1-158">GenerateUNG コンテキスト プロパティ</span><span class="sxs-lookup"><span data-stu-id="d9ab1-158">GenerateUNG context property</span></span>|<span data-ttu-id="d9ab1-159">UNG セグメントのアグリーメント設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="d9ab1-159">Apply UNG segments agreement setting</span></span>|<span data-ttu-id="d9ab1-160">エンジンの動作</span><span class="sxs-lookup"><span data-stu-id="d9ab1-160">Engine behavior</span></span>|  
|----------------------------------|------------------------------------------|---------------------|  
|<span data-ttu-id="d9ab1-161">TRUE</span><span class="sxs-lookup"><span data-stu-id="d9ab1-161">TRUE</span></span>|<span data-ttu-id="d9ab1-162">チェック</span><span class="sxs-lookup"><span data-stu-id="d9ab1-162">CHECKED</span></span>|<span data-ttu-id="d9ab1-163">UNG を生成します。</span><span class="sxs-lookup"><span data-stu-id="d9ab1-163">Generate UNG</span></span>|  
|<span data-ttu-id="d9ab1-164">TRUE</span><span class="sxs-lookup"><span data-stu-id="d9ab1-164">TRUE</span></span>|<span data-ttu-id="d9ab1-165">オフ</span><span class="sxs-lookup"><span data-stu-id="d9ab1-165">UNCHECKED</span></span>|<span data-ttu-id="d9ab1-166">UNG を生成します。</span><span class="sxs-lookup"><span data-stu-id="d9ab1-166">Generate UNG</span></span>|  
|<span data-ttu-id="d9ab1-167">FALSE</span><span class="sxs-lookup"><span data-stu-id="d9ab1-167">FALSE</span></span>|<span data-ttu-id="d9ab1-168">チェック</span><span class="sxs-lookup"><span data-stu-id="d9ab1-168">CHECKED</span></span>|<span data-ttu-id="d9ab1-169">UNG を生成しません。</span><span class="sxs-lookup"><span data-stu-id="d9ab1-169">Do not generate UNG</span></span>|  
|<span data-ttu-id="d9ab1-170">FALSE</span><span class="sxs-lookup"><span data-stu-id="d9ab1-170">FALSE</span></span>|<span data-ttu-id="d9ab1-171">オフ</span><span class="sxs-lookup"><span data-stu-id="d9ab1-171">UNCHECKED</span></span>|<span data-ttu-id="d9ab1-172">UNG を生成しません。</span><span class="sxs-lookup"><span data-stu-id="d9ab1-172">Do not generate UNG</span></span>|  
|<span data-ttu-id="d9ab1-173">存在しない (OverrideEDIHeader が false)</span><span class="sxs-lookup"><span data-stu-id="d9ab1-173">Not present (OverrideEDIHeader is false)</span></span>|<span data-ttu-id="d9ab1-174">チェック</span><span class="sxs-lookup"><span data-stu-id="d9ab1-174">CHECKED</span></span>|<span data-ttu-id="d9ab1-175">UNG を生成します。</span><span class="sxs-lookup"><span data-stu-id="d9ab1-175">Generate UNG</span></span>|  
|<span data-ttu-id="d9ab1-176">存在しない (OverrideEDIHeader が false)</span><span class="sxs-lookup"><span data-stu-id="d9ab1-176">Not present (OverrideEDIHeader is false)</span></span>|<span data-ttu-id="d9ab1-177">オフ</span><span class="sxs-lookup"><span data-stu-id="d9ab1-177">UNCHECKED</span></span>|<span data-ttu-id="d9ab1-178">UNG を生成しません。</span><span class="sxs-lookup"><span data-stu-id="d9ab1-178">Do not generate UNG</span></span>|  
  
### <a name="group-envelopes"></a><span data-ttu-id="d9ab1-179">グループ エンベロープ</span><span class="sxs-lookup"><span data-stu-id="d9ab1-179">Group envelopes</span></span>  
 <span data-ttu-id="d9ab1-180">グループ エンベロープは、インターチェンジが存在する 1 つ以上のグループを持つことができますはの特殊な課題を提示します。</span><span class="sxs-lookup"><span data-stu-id="d9ab1-180">Group envelopes present a special challenge, as the interchange can have more than one group present.</span></span> <span data-ttu-id="d9ab1-181">これに対処、EDI 送信パイプライン、インターチェンジ内のすべてのグループにエンベロープを適用するか、インターチェンジ内の唯一のグループにエンベロープを適用します。</span><span class="sxs-lookup"><span data-stu-id="d9ab1-181">To address this, the EDI send pipeline can either apply the envelope to all groups in the interchange, or apply the envelope to the only group in the interchange.</span></span>  
  
 <span data-ttu-id="d9ab1-182">1 つのトランザクションのすべての GS または UNG フィールドを上書きできます。 バッチ インターチェンジの場合、次のフィールドのみをオーバーライドすることができます。</span><span class="sxs-lookup"><span data-stu-id="d9ab1-182">For single transactions, all GS or UNG fields can be overridden, for batch interchanges only the following fields can be overridden:</span></span>  
  
-   <span data-ttu-id="d9ab1-183">GS04</span><span class="sxs-lookup"><span data-stu-id="d9ab1-183">GS04</span></span>  
  
-   <span data-ttu-id="d9ab1-184">GS05</span><span class="sxs-lookup"><span data-stu-id="d9ab1-184">GS05</span></span>  
  
-   <span data-ttu-id="d9ab1-185">UNG4_1</span><span class="sxs-lookup"><span data-stu-id="d9ab1-185">UNG4_1</span></span>  
  
-   <span data-ttu-id="d9ab1-186">UNG4_2</span><span class="sxs-lookup"><span data-stu-id="d9ab1-186">UNG4_2</span></span>  
  
### <a name="batching"></a><span data-ttu-id="d9ab1-187">バッチ処理</span><span class="sxs-lookup"><span data-stu-id="d9ab1-187">Batching</span></span>  
 <span data-ttu-id="d9ab1-188">バッチ処理されたメッセージのトランザクション セット制御番号をオーバーライドすると、バッチ処理オーケストレーションによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="d9ab1-188">Overriding the transaction set control number for batched messages is handled by the Batching orchestration.</span></span> <span data-ttu-id="d9ab1-189">次のプロパティは、トランザクション セット制御番号が上書きするバッチ処理されるメッセージのコンテキストを記述できます。</span><span class="sxs-lookup"><span data-stu-id="d9ab1-189">The following properties can be written to the context of any message that will be batched to override the transaction set control number:</span></span>  
  
-   <span data-ttu-id="d9ab1-190">ST02 (x12 メッセージ)</span><span class="sxs-lookup"><span data-stu-id="d9ab1-190">ST02 (for X12 messages)</span></span>  
  
-   <span data-ttu-id="d9ab1-191">UNH1 (EDIFACT メッセージの場合</span><span class="sxs-lookup"><span data-stu-id="d9ab1-191">UNH1 (For EDIFACT messages</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d9ab1-192">複数の受信メッセージに同じグループ内の同じ制御番号が含まれている場合は、重複した番号を持つメッセージが中断されます。</span><span class="sxs-lookup"><span data-stu-id="d9ab1-192">If multiple incoming messages contain the same control number in the same group, messages with duplicate numbers will be suspended.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d9ab1-193">バッチ処理するメッセージの EdiOverride のコンテキスト プロパティ ISA、UNA、GS、または UNG は昇格しないでください。</span><span class="sxs-lookup"><span data-stu-id="d9ab1-193">Do not promote the EdiOverride context properties ISA, UNA, GS, or UNG for messages that are to be batched.</span></span> <span data-ttu-id="d9ab1-194">EDI を送信する前にバッチ オーケストレーションの出力メッセージで昇格してこれらのプロパティをオーバーライドする必要がある場合は、パイプラインに送信します。</span><span class="sxs-lookup"><span data-stu-id="d9ab1-194">If you need to override these properties, promote them on the output message of the batch orchestration before sending to the EDI send pipeline.</span></span>  
  
### <a name="delimiter-collision"></a><span data-ttu-id="d9ab1-195">区切り記号の競合</span><span class="sxs-lookup"><span data-stu-id="d9ab1-195">Delimiter collision</span></span>  
 <span data-ttu-id="d9ab1-196">UNA ヘッダーなどの区切り記号は、各フィールドに一意の値を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9ab1-196">Delimiters, such as the UNA headers, must contain a unique value for each field.</span></span> <span data-ttu-id="d9ab1-197">UNA ヘッダーなどの区切り記号の値をオーバーライドする場合は、各区切り記号の値がオーバーライドするもアグリーメントまたはフォールバック アグリーメント設定から使用される任意の区切り記号値間の値だけでなく内で一意であることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9ab1-197">When overriding delimiter values, such as the UNA headers, you must ensure that each delimiter value is unique not only within the values you override, but also among any delimiter values used from the agreement or fallback agreement settings.</span></span>  
  
 <span data-ttu-id="d9ab1-198">たとえば、UNA1、UNA2、UNA4 を上書きすると、UNA3、UNA5、UNA6、UNA6Suffix がアグリーメントのプロパティから取得、各プロパティは、他と比較して一意の値を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9ab1-198">For example, if you override UNA1, UNA2, and UNA4, and UNA3, UNA5, UNA6 and UNA6Suffix come from agreement properties, each property must contain a unique value compared to the others.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9ab1-199">参照</span><span class="sxs-lookup"><span data-stu-id="d9ab1-199">See Also</span></span>  
 [<span data-ttu-id="d9ab1-200">BizTalk Server が EDI メッセージを送信する方法</span><span class="sxs-lookup"><span data-stu-id="d9ab1-200">How BizTalk Server Sends EDI Messages</span></span>](../core/how-biztalk-server-sends-edi-messages.md)