---
title: "EDI 検証、スキーマ、およびメッセージに関する既知の問題 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 417c3e18-9a97-4d59-bc2b-e96a8c33d388
caps.latest.revision: "42"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a508834ff81814b17bc12f1d698984d65748092
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-edi-validation-schemas-and-messages"></a><span data-ttu-id="2a0bb-102">EDI 検証、スキーマ、およびメッセージに関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="2a0bb-102">Known Issues with EDI Validation, Schemas, and Messages</span></span>
<span data-ttu-id="2a0bb-103">このトピックでは、検証に関する既知の問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-103">This topic describes known validation issues.</span></span>  
  
## <a name="message-is-suspended-with-edi-validation-turned-off"></a><span data-ttu-id="2a0bb-104">EDI 検証の無効化によってメッセージが中断される</span><span class="sxs-lookup"><span data-stu-id="2a0bb-104">Message Is Suspended with EDI Validation Turned Off</span></span>  
 <span data-ttu-id="2a0bb-105">**現象**</span><span class="sxs-lookup"><span data-stu-id="2a0bb-105">**Symptom**</span></span>  
  
 <span data-ttu-id="2a0bb-106">1 組のルールに違反し、検証は無効であるにもかかわらず、メッセージが (シリアル化される代わりに) 中断されます。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-106">A paired rule is violated, and validation is turned off, but the message is suspended (expected results are that the message is serialized).</span></span>  
  
 <span data-ttu-id="2a0bb-107">**考えられる原因**</span><span class="sxs-lookup"><span data-stu-id="2a0bb-107">**Possible Cause**</span></span>  
  
 <span data-ttu-id="2a0bb-108">クロス フィールド/セグメント検証を実行すると、場合でも**EDI の種類**プロパティが選択されて、**検証と確認の生成の設定**のノード、 **EDI プロパティ**ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-108">Cross-field/segment validation is performed, even if **EDI type** property is deselected in the **Validation and ACK Generation Settings** node of the **EDI Properties** dialog box.</span></span> <span data-ttu-id="2a0bb-109">検証は、スキーマの注釈で有効になっているために発生します。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-109">Validation occurs because it is turned on in the schema annotation.</span></span>  
  
 <span data-ttu-id="2a0bb-110">**解決策**</span><span class="sxs-lookup"><span data-stu-id="2a0bb-110">**Resolution**</span></span>  
  
 <span data-ttu-id="2a0bb-111">スキーマの注釈で検証を無効にします。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-111">Turn off validation in the schema annotation.</span></span>  
  
## <a name="the-biztalk-service-needs-to-be-restarted-after-a-schema-has-been-edited-and-redeployed"></a><span data-ttu-id="2a0bb-112">スキーマを編集し、再展開した後で BizTalk サービスを再起動する必要がある</span><span class="sxs-lookup"><span data-stu-id="2a0bb-112">The BizTalk service needs to be restarted after a schema has been edited and redeployed</span></span>  
 <span data-ttu-id="2a0bb-113">**現象**</span><span class="sxs-lookup"><span data-stu-id="2a0bb-113">**Symptom**</span></span>  
  
 <span data-ttu-id="2a0bb-114">スキーマを編集し、再展開した後に BizTalk Server が有効なメッセージを正常に処理しません。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-114">BizTalk Server does not successfully process a valid message after a schema has been edited and redeployed.</span></span>  
  
 <span data-ttu-id="2a0bb-115">**考えられる原因**</span><span class="sxs-lookup"><span data-stu-id="2a0bb-115">**Possible Cause**</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="2a0bb-116"> が、無限のタイムアウトが設定されたスキーマをキャッシュしています。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-116"> caches schemas with unlimited timeouts.</span></span>  
  
 <span data-ttu-id="2a0bb-117">**解決策**</span><span class="sxs-lookup"><span data-stu-id="2a0bb-117">**Resolution**</span></span>  
  
 <span data-ttu-id="2a0bb-118">スキーマを編集し、再展開した後で、BizTalk Server アプリケーション サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-118">After editing and redeploying a schema, restart the BizTalk Server Application service.</span></span> <span data-ttu-id="2a0bb-119">また、再展開されたスキーマを使用するパイプラインをホストするホスト インスタンスを再起動する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-119">You also must restart the host instance hosting the pipeline that is using the redeployed schema.</span></span>  
  
## <a name="processing-has-been-aborted-for-messages-of-a-single-encoding-type-for-a-single-party"></a><span data-ttu-id="2a0bb-120">1 つのパーティのエンコードの種類が同じであるメッセージの処理が中断される</span><span class="sxs-lookup"><span data-stu-id="2a0bb-120">Processing Has Been Aborted for Messages of a Single Encoding Type for a Single Party</span></span>  
 <span data-ttu-id="2a0bb-121">**現象**</span><span class="sxs-lookup"><span data-stu-id="2a0bb-121">**Symptom**</span></span>  
  
 <span data-ttu-id="2a0bb-122">1 つのパーティのエンコードの種類 (X12、EDIFACT など) が同じであるすべてのメッセージの処理が中断されます。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-122">The processing of all messages of a single encoding type (for example, X12 or EDIFACT) for a single party have been aborted.</span></span> <span data-ttu-id="2a0bb-123">このパーティのエンコードの種類が異なるメッセージ、または別のパーティのメッセージは処理されます。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-123">Processing of messages of another encoding type for the same party, or any messages for another party, has not been affected.</span></span>  
  
 <span data-ttu-id="2a0bb-124">**考えられる原因**</span><span class="sxs-lookup"><span data-stu-id="2a0bb-124">**Possible Cause**</span></span>  
  
 <span data-ttu-id="2a0bb-125">インターチェンジ、グループ、またはトランザクション セットの制御番号の長さが許容されている最大の長さを超えています。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-125">The length of the interchange, group, or transaction set control number has exceeded the maximum allowable length.</span></span>  
  
 <span data-ttu-id="2a0bb-126">X12 メッセージの場合、制御番号の最大文字数は 9 桁です。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-126">For X12 messages, the maximum length of a control number is nine digits.</span></span> <span data-ttu-id="2a0bb-127">EDIFACT メッセージの場合、制御番号の最大文字数は、3 つのフィールドを合わせて 14 桁です。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-127">For EDIFACT message, the maximum length of a control number is 14 digits over three fields.</span></span>  
  
 <span data-ttu-id="2a0bb-128">**解決策**</span><span class="sxs-lookup"><span data-stu-id="2a0bb-128">**Resolution**</span></span>  
  
 <span data-ttu-id="2a0bb-129">影響を受けるパーティの [EDI のプロパティ] ダイアログ ボックスの該当するプロパティ ページで、制御番号をリセットしてください。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-129">Reset the control number in the appropriate property page of the EDI Properties dialog box for the affected party.</span></span> <span data-ttu-id="2a0bb-130">制御番号は、次のプロパティ ページで編集できます。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-130">You can edit the control numbers in the following property pages:</span></span>  
  
-   <span data-ttu-id="2a0bb-131">X12 インターチェンジ制御番号 : X12 プロパティの [パーティ - インターチェンジの受信者] ノードにある [ISA セグメントの定義] ページ</span><span class="sxs-lookup"><span data-stu-id="2a0bb-131">X12 interchange control number: ISA Segment Definition page (in the Party as Interchange Receiver node) for X12 Properties</span></span>  
  
-   <span data-ttu-id="2a0bb-132">X12 グループまたはトランザクション セット制御番号 : X12 プロパティの [パーティ - インターチェンジの受信者] ノードにある [GS および ST セグメントの定義] ページ</span><span class="sxs-lookup"><span data-stu-id="2a0bb-132">X12 group or transaction set control number: GS and ST Segment Definition page (in the Party as Interchange Receiver node for X12 Properties)</span></span>  
  
-   <span data-ttu-id="2a0bb-133">EDIFACT インターチェンジ制御番号 : EDIFACT プロパティの [パーティ - インターチェンジの受信者] ノードにある [UNB セグメントの定義] ページ</span><span class="sxs-lookup"><span data-stu-id="2a0bb-133">EDIFACT interchange control number: UNB Segment Definition page (in the Party as Interchange Receiver node for EDIFACT Properties)</span></span>  
  
-   <span data-ttu-id="2a0bb-134">EDIFACT グループまたはトランザクション セット制御番号 : EDIFACT プロパティの [パーティ - インターチェンジの受信者] ノードにある [UNG および UNH セグメントの定義] ページ</span><span class="sxs-lookup"><span data-stu-id="2a0bb-134">EDIFACT group or transaction set control number: UNG and UNH Segment Definition page (in the Party as Interchange Receiver node for EDIFACT Properties)</span></span>  
  
## <a name="biztalk-server-validates-with-schemas-that-have-unh-segments-with-seven-data-elements"></a><span data-ttu-id="2a0bb-135">BizTalk Server が 7 つのデータ要素を含む UNH セグメントを持つスキーマを使用して検証を行う</span><span class="sxs-lookup"><span data-stu-id="2a0bb-135">BizTalk Server validates with schemas that have UNH segments with seven data elements</span></span>  
 <span data-ttu-id="2a0bb-136">EDIFACT の以前のバージョンの UNH セグメントには 4 つの要素が含まれていましたが、新しいバージョンの UNH セグメントには 7 つの要素 (うち 3 つはオプション) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-136">In earlier versions of EDIFACT, the UNH segment has four elements, rather than the seven elements (three of which are optional) that the UNH segment has in later versions.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="2a0bb-137"> は、7 つのデータ要素を含む新しいバージョンを検証に使用します。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-137"> uses the later version with seven elements for validation.</span></span>  
  
## <a name="error-messages-generated-for-multiple-cross-field-validation-rules-will-not-be-specific-to-the-rule"></a><span data-ttu-id="2a0bb-138">複数のクロスフィールド検証に対して生成されたエラー メッセージが、ルールに固有のものではない</span><span class="sxs-lookup"><span data-stu-id="2a0bb-138">Error messages generated for multiple cross-field validation rules will not be specific to the rule</span></span>  
 <span data-ttu-id="2a0bb-139">メッセージのデータ要素に対する複数のクロスフィールド検証ルールがスキーマに含まれている場合、データ要素にエラーが発生すると、検証ルールごとに別々のエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-139">If a schema contains multiple cross-field validation rules for a data element in a message, and an error occurs with the data element, a separate error will be generated for each validation rule.</span></span> <span data-ttu-id="2a0bb-140">ただし、これらのエラーには同じエラー コードと説明が表示されます (エラーが検証ルールに固有のものではありません)。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-140">However, each of these errors will have the same error code and description; the errors will not be specific to the validation rule.</span></span>  
  
## <a name="if-edi-type-validation-is-disabled-on-receive-and-enabled-on-send-the-send-pipeline-will-not-be-able-to-serialize-the-message"></a><span data-ttu-id="2a0bb-141">EDI 型の検証が受信時は無効、送信時は有効の場合、送信パイプラインはメッセージをシリアル化できない</span><span class="sxs-lookup"><span data-stu-id="2a0bb-141">If EDI type validation is disabled on receive and enabled on send, the send pipeline will not be able to serialize the message</span></span>  
 <span data-ttu-id="2a0bb-142">EDI 型の検証を受信側で無効にした場合、EDI 受信パイプラインは、メッセージが有効であるか無効であるかにかかわらず、受信した EDI メッセージから XML メッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-142">If you turn off EDI type validation on the receive side, the EDI receive pipeline will generate an XML message from a received EDI message, whether or not the message is valid.</span></span> <span data-ttu-id="2a0bb-143">EDI 型の検証を送信側で有効にした場合、XML ファイルにエラーが含まれていると、EDI 送信パイプラインは XML を有効な EDI ファイルに再処理することができないため、エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-143">If EDI validation is enabled on the send side, the EDI send pipeline will not be able to reprocess the XML into a valid EDI file if the XML file contains errors, and as a result will generate an error.</span></span>  
  
## <a name="edi-promoted-properties-are-only-available-if-your-application-has-a-reference-to-the-biztalk-edi-application"></a><span data-ttu-id="2a0bb-144">EDI が昇格させたプロパティは、アプリケーションが BizTalk EDI アプリケーションを参照する場合にのみ使用可能である</span><span class="sxs-lookup"><span data-stu-id="2a0bb-144">EDI promoted properties are only available if your application has a reference to the BizTalk EDI application</span></span>  
 <span data-ttu-id="2a0bb-145">**現象**</span><span class="sxs-lookup"><span data-stu-id="2a0bb-145">**Symptom**</span></span>  
  
 <span data-ttu-id="2a0bb-146">EDI 名前空間で昇格させたプロパティが、オーケストレーションや送信ポートのフィルター条件などで使用する予定の昇格させたプロパティの一覧に表示されません。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-146">Promoted properties under the EDI namespace are not displayed in the list of promoted properties that you are trying to use, for example, in an orchestration or in the filter conditions for a send port.</span></span>  
  
 <span data-ttu-id="2a0bb-147">**考えられる原因**</span><span class="sxs-lookup"><span data-stu-id="2a0bb-147">**Possible Cause**</span></span>  
  
 <span data-ttu-id="2a0bb-148">使用している BizTalk アプリケーションが BizTalk EDI アプリケーションを参照していません。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-148">The BizTalk application that you are using does not have a reference to the BizTalk EDI Application.</span></span> <span data-ttu-id="2a0bb-149">EDI が昇格させたプロパティのプロパティ スキーマは、BizTalk EDI アプリケーションのリソース フォルダーに格納されている Microsoft.BizTalk.Edi.BaseArtifacts.dll 内にあります。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-149">The property schemas for the EDI promoted properties are in Microsoft.BizTalk.Edi.BaseArtifacts.dll, which is included in the Resources folder of BizTalk EDI Application.</span></span>  
  
 <span data-ttu-id="2a0bb-150">**解決策**</span><span class="sxs-lookup"><span data-stu-id="2a0bb-150">**Resolution**</span></span>  
  
 <span data-ttu-id="2a0bb-151">操作している BizTalk アプリケーションに、BizTalk EDI アプリケーションへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-151">To the BizTalk application that you are working in, add a reference to the BizTalk EDI Application.</span></span>  
  
## <a name="the-data-element-name-in-a-context-property-name-contains-an-underscore-not-a-period"></a><span data-ttu-id="2a0bb-152">データ要素名のピリオドがコンテキスト プロパティ名ではアンダースコアになる</span><span class="sxs-lookup"><span data-stu-id="2a0bb-152">The Data Element Name in a Context Property Name Contains an Underscore, Not a Period</span></span>  
 <span data-ttu-id="2a0bb-153">EDI セグメント内のデータ要素名には、ピリオドが含まれています (UNB2 送信者セグメントの ID フィールドである UNB2.1 など)。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-153">The name of a data element within an EDI segment contains a period, for example, UNB2.1, which is the identification field for the UNB2 Sender segment.</span></span> <span data-ttu-id="2a0bb-154">しかし、データ要素名が EDI コンテキスト プロパティの一部となった場合、ピリオドがアンダースコアに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-154">However, when the data element name is included as part of an EDI context property, the period is replaced with an underscore.</span></span> <span data-ttu-id="2a0bb-155">たとえば、送信者 ID データ要素を表すコンテキスト プロパティは、EDI.UNB2.1 ではなく EDI.UNB2_1 となります。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-155">For example, the context property for the Sender Identification data element is EDI.UNB2_1, not EDI.UNB2.1.</span></span> <span data-ttu-id="2a0bb-156">この現象は、コンテキスト プロパティ名でピリオドがサポートされていないために発生します。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-156">The reason for this is that a period is not supported in a context property name.</span></span>  
  
## <a name="irrelevant-string-is-appended-to-instance-validation-error-message"></a><span data-ttu-id="2a0bb-157">インスタンスの検証エラー メッセージに関連のない文字列が追加される</span><span class="sxs-lookup"><span data-stu-id="2a0bb-157">Irrelevant string is appended to instance validation error message</span></span>  
 <span data-ttu-id="2a0bb-158">インスタンスの検証中にエラーが表示された場合、エラー メッセージに "BEC 2004" という文字列が追加されます。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-158">Whenever you receive an error during instance validation, the string "BEC 2004" will be appended to the error message.</span></span> <span data-ttu-id="2a0bb-159">この文字列は無視してかまいません。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-159">You can ignore this string.</span></span>  
  
## <a name="edifact-schema-names-are-case-sensitive"></a><span data-ttu-id="2a0bb-160">EDIFACT スキーマ名で大文字と小文字が区別される</span><span class="sxs-lookup"><span data-stu-id="2a0bb-160">EDIFACT Schema Names Are Case-Sensitive</span></span>  
 <span data-ttu-id="2a0bb-161">EDIFACT スキーマのスキーマ名では、スキーマの root_reference データ要素に示されるように、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-161">The schema name of an EDIFACT schema, as shown in the root_reference data element of the schema, is case-sensitive.</span></span> <span data-ttu-id="2a0bb-162">たとえば、EFACT_D98B_ORDERS と EFACT_d98B_Orders は 2 つの異なるスキーマです。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-162">For example, EFACT_D98B_ORDERS and EFACT_d98B_Orders would be two different schemas.</span></span>  
  
## <a name="invalid-edi-messages-can-be-suspended-even-if-edi-type-validation-is-disabled"></a><span data-ttu-id="2a0bb-163">EDI 型の検証が無効の場合でも、無効な EDI メッセージを中断できる</span><span class="sxs-lookup"><span data-stu-id="2a0bb-163">Invalid EDI Messages Can Be Suspended Even If EDI Type Validation Is Disabled</span></span>  
 <span data-ttu-id="2a0bb-164">EDI 型の検証が無効の場合でも、EDI 構造検証は実行されます。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-164">EDI structural validation is performed even if the EDI Type validation is disabled.</span></span> <span data-ttu-id="2a0bb-165">EDI の種類の検証が無効であっても、基本的な構造の検証でエラーとなったインターチェンジは中断されます。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-165">An interchange that fails the basic structural validations will be suspended, even if the EDI Type validation is disabled.</span></span>  
  
## <a name="the-edi-assembler-will-serialize-an-unbatched-interchange-even-if-a-separator-character-is-used-in-an-envelope-header"></a><span data-ttu-id="2a0bb-166">エンベロープ ヘッダーに区切り文字が使用されている場合でも、EDI アセンブラーはバッチ化されていないインターチェンジをシリアル化する</span><span class="sxs-lookup"><span data-stu-id="2a0bb-166">The EDI Assembler Will Serialize an Unbatched Interchange Even If a Separator Character Is Used in an Envelope Header</span></span>  
 <span data-ttu-id="2a0bb-167">ヘッダー フィールドとトレーラー フィールドを分離するために使用する区切り文字は、インターチェンジ受信者としてのパーティ用に定義されているとおり、インターチェンジ、グループ、またはトランザクション セットのヘッダーまたはトレーラー フィールドの定義で使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-167">The separator characters used to separate header and trailer fields must not be used in the definition of any of the interchange, group, or transaction set header or trailer fields, as defined for the party as interchange receiver.</span></span> <span data-ttu-id="2a0bb-168">これらを定義で使用すると、インターチェンジは、送信側 BizTalk Server の EDI アセンブラーまたは受信側パーティの逆アセンブラーのどちらかの処理に失敗します。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-168">If they are, the interchange will fail processing either in the EDI Assembler of the sending BizTalk Server or in the disassembler of the receiving party.</span></span> <span data-ttu-id="2a0bb-169">アセンブラーはヘッダー制御 (サービス) スキーマに対してエンベロープを検証するので、送信バッチの場合、インターチェンジは EDI アセンブラーの処理に失敗します。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-169">The interchange will fail in the EDI Assembler if it is an outbound batch, because the Assembler will validate the envelope against the header control (service) schema.</span></span> <span data-ttu-id="2a0bb-170">バッチ化されていないインターチェンジは、EDI アセンブラーではシリアル化されますが、受信側パーティの逆アセンブラーでは処理に失敗します。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-170">If the interchange is unbatched, the EDI Assembler will serialize it, but it will fail processing in the disassembler at the receiving party.</span></span>  
  
## <a name="mismatched-character-sets-can-result-in-suspended-interchanges"></a><span data-ttu-id="2a0bb-171">文字セットの不一致によりインターチェンジの中断が発生する</span><span class="sxs-lookup"><span data-stu-id="2a0bb-171">Mismatched Character Sets Can Result in Suspended Interchanges</span></span>  
 <span data-ttu-id="2a0bb-172">送信インターチェンジに使用される文字セットは、インターチェンジに挿入されるトランザクション セットの作成に使用される文字セットと同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-172">The character set used for an outgoing interchange should be the same as the character set used to create the transaction sets inserted into the interchange.</span></span> <span data-ttu-id="2a0bb-173">同じでなければ、無効な文字が存在することを示すエラー メッセージが表示され、インターチェンジが中断される場合があります。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-173">If not, the interchange will likely be suspended with an error message indicating that there were invalid characters.</span></span>  
  
 <span data-ttu-id="2a0bb-174">たとえば、UNOA 文字セットを使用して EDIFACT バッチを作成するときに、バッチに追加するトランザクション セットに小文字を使用すると、UNOA は小文字を許可しないためバッチ処理オーケストレーションはメッセージを中断します。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-174">For example, if you create an EDIFACT batch using the UNOA character set, but a transaction set added to the batch has lower-case characters, the batching orchestration will suspend the message because UNOA does not allow lower-case characters.</span></span>  
  
 <span data-ttu-id="2a0bb-175">また、"基本" 文字セットを使用して X12 インターチェンジの EDI 送信パイプラインを構成するときに、インターチェンジ受信者としてのパーティの [X12 インターチェンジのエンベロープの生成] ページで選択される X12 文字セットは "拡張" または "UTF8/Unicode" であるため、バッチ化された X12 インターチェンジに小文字を使用すると、エンベロープの設定が適用されるときに、バッチ化されたメッセージは中断されます。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-175">As another example, if you configure the EDI send pipeline for X12 interchanges with the "Basic" character set, but an X12 batched interchange has lower-case characters because the X12 character set selected in the X12 Interchange Envelop Generation page for the party as an interchange receiver is set to "Extended" or "UTF8/Unicode", the batched message will be suspended when envelope settings are applied.</span></span>  
  
## <a name="using-unh25-for-schema-resolution-requires-an-update-to-the-schema"></a><span data-ttu-id="2a0bb-176">スキーマの解決に UNH2.5 を使用する場合、スキーマの更新が要求される</span><span class="sxs-lookup"><span data-stu-id="2a0bb-176">Using UNH2.5 for schema resolution requires an update to the schema</span></span>  
 <span data-ttu-id="2a0bb-177">受信 EDIFACT インターチェンジのスキーマの解決に UNH2.5 (関連付けの割り当てコード) を使用する場合は、\Program Files\Microsoft BizTalk Server 20xx\Schema フォルダーにある、関連するドキュメント スキーマを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-177">If you use UNH2.5 (the Association assigned code) for schema resolution of an incoming EDIFACT interchange, you will need to update the relevant document schema in the \Program Files\Microsoft BizTalk Server 20xx\Schema folder.</span></span> <span data-ttu-id="2a0bb-178">root_reference、display_reference、および xs:element name の既存の値に、UNH2.5 の値を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-178">You will need to append the value of UNH2.5 to the existing values for the root_reference, display_reference, and xs:element name.</span></span> <span data-ttu-id="2a0bb-179">たとえば、UNH2.5 が "EAN008" で、EFACT_D96A_INVOIC スキーマを使用している場合、root_reference、display_reference、および xs:element name を "EFACT_D96A_INVOIC_EAN008" に設定します。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-179">For example, if UNH2.5 is "EAN008" and you are using the EFACT_D96A_INVOIC schema, you would set root_reference, display_reference, and xs:element name to "EFACT_D96A_INVOIC_EAN008".</span></span>  
  
## <a name="the-compressed-file-of-schemas-will-be-replaced-when-an-upgrade-is-performed"></a><span data-ttu-id="2a0bb-180">アップグレードを実行すると、スキーマの圧縮ファイルが置き換えられる</span><span class="sxs-lookup"><span data-stu-id="2a0bb-180">The compressed file of schemas will be replaced when an upgrade is performed</span></span>  
 <span data-ttu-id="2a0bb-181">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を新しいビルドにアップグレードすると、環境内の MicrosoftEdiXSDTemplates.exe ファイルが、アップグレードに関連付けられた MicrosoftEdiXSDTemplates.exe ファイルに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-181">If you upgrade Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to a later build, the MicrosoftEdiXSDTemplates.exe file in your installation will be replaced with the MicrosoftEdiXSDTemplates.exe file associated with the upgrade.</span></span> <span data-ttu-id="2a0bb-182">古い圧縮ファイルのスキーマを引き続き使用する場合は、古い圧縮ファイルをバックアップしない限り、アップグレード後、圧縮ファイルにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-182">If you plan to continue to use the schemas from the old compressed file, you will no longer have access to the compressed file after the upgrade unless you back up the old compressed file.</span></span>  
  
## <a name="if-a-group-contains-multiple-x12-transaction-sets-all-must-be-of-the-same-type"></a><span data-ttu-id="2a0bb-183">1 つのグループに複数の X12 トランザクション セットが含まれる場合、すべてが同じ種類でなければならない</span><span class="sxs-lookup"><span data-stu-id="2a0bb-183">If a group contains multiple X12 transaction sets, all must be of the same type</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="2a0bb-184"> では、同じグループ内での異なるトランザクション セットの混合はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-184"> does not support mixing different transaction sets within the same group.</span></span> <span data-ttu-id="2a0bb-185">1 つのグループに複数のトランザクションが含まれる場合、すべてのトランザクションで ST01 の値が同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-185">When a group contains multiple transactions, the value of ST01 must be the same for all transactions.</span></span>  
  
## <a name="receiving-x12-interchanges-that-contain-non-ascii-delimiters-may-result-in-the-message-becoming-suspended"></a><span data-ttu-id="2a0bb-186">ASCII 以外の区切り文字を含む X12 インターチェンジを受信すると、メッセージが中断する場合がある</span><span class="sxs-lookup"><span data-stu-id="2a0bb-186">Receiving X12 interchanges that contain non-ASCII delimiters may result in the message becoming suspended</span></span>  
 <span data-ttu-id="2a0bb-187">**現象**</span><span class="sxs-lookup"><span data-stu-id="2a0bb-187">**Symptom**</span></span>  
  
 <span data-ttu-id="2a0bb-188">ASCII 以外の区切り文字の値を使用する X12 インターチェンジを受信すると、メッセージが中断状態になり、アプリケーション イベント ログにエラーが書き込まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-188">When receiving an X12 interchange that uses non-ASCII delimiter values, the message may become suspended and an error written to the application event log.</span></span>  
  
 <span data-ttu-id="2a0bb-189">**考えられる原因**</span><span class="sxs-lookup"><span data-stu-id="2a0bb-189">**Possible Cause**</span></span>  
  
 <span data-ttu-id="2a0bb-190">この問題は、インターチェンジが UTF-8 としてエンコードされていない場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-190">This problem can occur if the interchange is not encoded as UTF-8.</span></span>  
  
 <span data-ttu-id="2a0bb-191">**解決策**</span><span class="sxs-lookup"><span data-stu-id="2a0bb-191">**Resolution**</span></span>  
  
 <span data-ttu-id="2a0bb-192">ASCII 以外の区切り文字を含む受信 X12 インターチェンジが UTF-8 としてエンコードされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2a0bb-192">Ensure that any incoming X12 interchange that contains non-ASCII delimiters is encoded as UTF-8.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a0bb-193">参照</span><span class="sxs-lookup"><span data-stu-id="2a0bb-193">See Also</span></span>  
 <span data-ttu-id="2a0bb-194">[EDI 処理に関する既知の問題](../core/known-issues-with-edi-processing.md) </span><span class="sxs-lookup"><span data-stu-id="2a0bb-194">[Known Issues with EDI Processing](../core/known-issues-with-edi-processing.md) </span></span>  
 <span data-ttu-id="2a0bb-195">[EDI メッセージング](../core/edi-messaging.md) </span><span class="sxs-lookup"><span data-stu-id="2a0bb-195">[EDI Messaging](../core/edi-messaging.md) </span></span>  
 <span data-ttu-id="2a0bb-196">[EDI メッセージの検証](../core/edi-message-validation.md) </span><span class="sxs-lookup"><span data-stu-id="2a0bb-196">[EDI Message Validation](../core/edi-message-validation.md) </span></span>  
 <span data-ttu-id="2a0bb-197">[EDI スキーマ](../core/edi-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="2a0bb-197">[EDI Schemas](../core/edi-schemas.md) </span></span>  
 [<span data-ttu-id="2a0bb-198">EDI スキーマの開発</span><span class="sxs-lookup"><span data-stu-id="2a0bb-198">Developing EDI Schemas</span></span>](../core/developing-edi-schemas.md)