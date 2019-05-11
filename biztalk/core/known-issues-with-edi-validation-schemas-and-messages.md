---
title: EDI の検証、スキーマ、およびメッセージに関する既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 417c3e18-9a97-4d59-bc2b-e96a8c33d388
caps.latest.revision: 42
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 706b165067fbbed058c12ff096c91851594d945a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380746"
---
# <a name="known-issues-with-edi-validation-schemas-and-messages"></a><span data-ttu-id="6b7b4-102">EDI の検証、スキーマ、およびメッセージに関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="6b7b4-102">Known Issues with EDI Validation, Schemas, and Messages</span></span>
<span data-ttu-id="6b7b4-103">このトピックでは、既知の検証の問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-103">This topic describes known validation issues.</span></span>  
  
## <a name="message-is-suspended-with-edi-validation-turned-off"></a><span data-ttu-id="6b7b4-104">EDI 検証をになっているメッセージは中断されます。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-104">Message Is Suspended with EDI Validation Turned Off</span></span>  
 <span data-ttu-id="6b7b4-105">**現象**</span><span class="sxs-lookup"><span data-stu-id="6b7b4-105">**Symptom**</span></span>  
  
 <span data-ttu-id="6b7b4-106">1 組のルールに違反すると、検証は無効しが、メッセージは中断されます (結果は、メッセージがシリアル化されることが必要です)。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-106">A paired rule is violated, and validation is turned off, but the message is suspended (expected results are that the message is serialized).</span></span>  
  
 <span data-ttu-id="6b7b4-107">**考えられる原因**</span><span class="sxs-lookup"><span data-stu-id="6b7b4-107">**Possible Cause**</span></span>  
  
 <span data-ttu-id="6b7b4-108">クロス フィールド/セグメント検証を実行すると、場合でも**EDI の種類**プロパティが選択されて、**検証と確認の生成の設定**のノード、 **EDI プロパティ**ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-108">Cross-field/segment validation is performed, even if **EDI type** property is deselected in the **Validation and ACK Generation Settings** node of the **EDI Properties** dialog box.</span></span> <span data-ttu-id="6b7b4-109">検証では、スキーマ注釈でオンにするために発生します。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-109">Validation occurs because it is turned on in the schema annotation.</span></span>  
  
 <span data-ttu-id="6b7b4-110">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="6b7b4-110">**Resolution**</span></span>  
  
 <span data-ttu-id="6b7b4-111">スキーマの注釈で検証を無効にします。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-111">Turn off validation in the schema annotation.</span></span>  
  
## <a name="the-biztalk-service-needs-to-be-restarted-after-a-schema-has-been-edited-and-redeployed"></a><span data-ttu-id="6b7b4-112">BizTalk サービスは、スキーマを編集し、再デプロイ後に再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-112">The BizTalk service needs to be restarted after a schema has been edited and redeployed</span></span>  
 <span data-ttu-id="6b7b4-113">**現象**</span><span class="sxs-lookup"><span data-stu-id="6b7b4-113">**Symptom**</span></span>  
  
 <span data-ttu-id="6b7b4-114">BizTalk Server は有効なメッセージがスキーマを編集し、再デプロイ後に正常に処理していません。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-114">BizTalk Server does not successfully process a valid message after a schema has been edited and redeployed.</span></span>  
  
 <span data-ttu-id="6b7b4-115">**考えられる原因**</span><span class="sxs-lookup"><span data-stu-id="6b7b4-115">**Possible Cause**</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="6b7b4-116">無制限のタイムアウトを持つスキーマをキャッシュします。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-116">caches schemas with unlimited timeouts.</span></span>  
  
 <span data-ttu-id="6b7b4-117">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="6b7b4-117">**Resolution**</span></span>  
  
 <span data-ttu-id="6b7b4-118">編集、スキーマを再デプロイすると、BizTalk Server アプリケーション サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-118">After editing and redeploying a schema, restart the BizTalk Server Application service.</span></span> <span data-ttu-id="6b7b4-119">また、再展開されたスキーマを使用しているパイプラインをホストするホスト インスタンスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-119">You also must restart the host instance hosting the pipeline that is using the redeployed schema.</span></span>  
  
## <a name="processing-has-been-aborted-for-messages-of-a-single-encoding-type-for-a-single-party"></a><span data-ttu-id="6b7b4-120">1 つのパーティのエンコードの種類のメッセージの処理は中止されました</span><span class="sxs-lookup"><span data-stu-id="6b7b4-120">Processing Has Been Aborted for Messages of a Single Encoding Type for a Single Party</span></span>  
 <span data-ttu-id="6b7b4-121">**現象**</span><span class="sxs-lookup"><span data-stu-id="6b7b4-121">**Symptom**</span></span>  
  
 <span data-ttu-id="6b7b4-122">エンコードの種類のすべてのメッセージの処理 (たとえば、X12 または EDIFACT)、単一のパーティが中止されました。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-122">The processing of all messages of a single encoding type (for example, X12 or EDIFACT) for a single party have been aborted.</span></span> <span data-ttu-id="6b7b4-123">別のパーティに同じのパーティのエンコードの種類のメッセージまたはメッセージの処理、影響はありません。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-123">Processing of messages of another encoding type for the same party, or any messages for another party, has not been affected.</span></span>  
  
 <span data-ttu-id="6b7b4-124">**考えられる原因**</span><span class="sxs-lookup"><span data-stu-id="6b7b4-124">**Possible Cause**</span></span>  
  
 <span data-ttu-id="6b7b4-125">インターチェンジ、グループ、またはトランザクション セット制御番号の長さが許容される最大長を超えました。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-125">The length of the interchange, group, or transaction set control number has exceeded the maximum allowable length.</span></span>  
  
 <span data-ttu-id="6b7b4-126">X12 メッセージで、コントロールの最大長は 9 桁の数字です。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-126">For X12 messages, the maximum length of a control number is nine digits.</span></span> <span data-ttu-id="6b7b4-127">EDIFACT メッセージの場合は、制御番号の最大長は、14 桁を 3 つのフィールドが。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-127">For EDIFACT message, the maximum length of a control number is 14 digits over three fields.</span></span>  
  
 <span data-ttu-id="6b7b4-128">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="6b7b4-128">**Resolution**</span></span>  
  
 <span data-ttu-id="6b7b4-129">影響を受けるパーティの EDI のプロパティ ダイアログ ボックスの該当するプロパティ ページで、制御番号をリセットします。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-129">Reset the control number in the appropriate property page of the EDI Properties dialog box for the affected party.</span></span> <span data-ttu-id="6b7b4-130">次のプロパティ ページで制御番号を編集できます。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-130">You can edit the control numbers in the following property pages:</span></span>  
  
-   <span data-ttu-id="6b7b4-131">X12 インターチェンジ制御番号です。ISA セグメントの定義 ページ (パーティ-インターチェンジの受信者 ノード) で X12 のプロパティ</span><span class="sxs-lookup"><span data-stu-id="6b7b4-131">X12 interchange control number: ISA Segment Definition page (in the Party as Interchange Receiver node) for X12 Properties</span></span>  
  
-   <span data-ttu-id="6b7b4-132">X12 グループまたはトランザクション セット制御番号。GS および ST セグメントの定義 ページ (x12 パーティ-インターチェンジの受信者 ノード プロパティ)</span><span class="sxs-lookup"><span data-stu-id="6b7b4-132">X12 group or transaction set control number: GS and ST Segment Definition page (in the Party as Interchange Receiver node for X12 Properties)</span></span>  
  
-   <span data-ttu-id="6b7b4-133">EDIFACT インターチェンジ制御番号:UNB セグメントの定義ページの [パーティ-インターチェンジの受信者] ノード EDIFACT プロパティの)</span><span class="sxs-lookup"><span data-stu-id="6b7b4-133">EDIFACT interchange control number: UNB Segment Definition page (in the Party as Interchange Receiver node for EDIFACT Properties)</span></span>  
  
-   <span data-ttu-id="6b7b4-134">EDIFACT グループまたはトランザクション セットの制御番号。[パーティ-インターチェンジの受信者] ノードの EDIFACT のプロパティとして)、[UNG および UNH セグメントの定義] ページ</span><span class="sxs-lookup"><span data-stu-id="6b7b4-134">EDIFACT group or transaction set control number: UNG and UNH Segment Definition page (in the Party as Interchange Receiver node for EDIFACT Properties)</span></span>  
  
## <a name="biztalk-server-validates-with-schemas-that-have-unh-segments-with-seven-data-elements"></a><span data-ttu-id="6b7b4-135">BizTalk Server が 7 つのデータ要素を含む UNH セグメントのスキーマを使用して検証します。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-135">BizTalk Server validates with schemas that have UNH segments with seven data elements</span></span>  
 <span data-ttu-id="6b7b4-136">UNH セグメントが 7 つの要素 (うち 3 つは省略可能) ではなく、4 つの要素、EDIFACT の以前のバージョンの UNH セグメントの以降のバージョンであります。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-136">In earlier versions of EDIFACT, the UNH segment has four elements, rather than the seven elements (three of which are optional) that the UNH segment has in later versions.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="6b7b4-137">検証のための 7 つの要素に以降のバージョンを使用します。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-137">uses the later version with seven elements for validation.</span></span>  
  
## <a name="error-messages-generated-for-multiple-cross-field-validation-rules-will-not-be-specific-to-the-rule"></a><span data-ttu-id="6b7b4-138">複数のクロス フィールド検証ルールを生成するエラー メッセージをルールに固有にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-138">Error messages generated for multiple cross-field validation rules will not be specific to the rule</span></span>  
 <span data-ttu-id="6b7b4-139">スキーマには、メッセージ内のデータ要素に対して複数のクロス フィールド検証ルールが含まれています、データ要素エラーが発生した場合は、それぞれの検証規則の個別のエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-139">If a schema contains multiple cross-field validation rules for a data element in a message, and an error occurs with the data element, a separate error will be generated for each validation rule.</span></span> <span data-ttu-id="6b7b4-140">ただし、これらのエラーが、同じエラー コードと説明。エラーは、検証規則を特定できません。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-140">However, each of these errors will have the same error code and description; the errors will not be specific to the validation rule.</span></span>  
  
## <a name="if-edi-type-validation-is-disabled-on-receive-and-enabled-on-send-the-send-pipeline-will-not-be-able-to-serialize-the-message"></a><span data-ttu-id="6b7b4-141">EDI 型の検証が無効になっている場合は、受信し、送信を有効になっている、送信パイプラインはできません、メッセージをシリアル化するには</span><span class="sxs-lookup"><span data-stu-id="6b7b4-141">If EDI type validation is disabled on receive and enabled on send, the send pipeline will not be able to serialize the message</span></span>  
 <span data-ttu-id="6b7b4-142">EDI 型の検証、受信側で無効にした場合、受信した EDI メッセージからメッセージが有効かどうか、EDI 受信パイプラインに XML メッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-142">If you turn off EDI type validation on the receive side, the EDI receive pipeline will generate an XML message from a received EDI message, whether or not the message is valid.</span></span> <span data-ttu-id="6b7b4-143">送信側の EDI の検証が有効な場合、EDI 送信パイプラインは XML ファイルは、エラーにはが含まれていて、その結果、エラーが発生、有効な EDI ファイルに XML を再処理することはできません。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-143">If EDI validation is enabled on the send side, the EDI send pipeline will not be able to reprocess the XML into a valid EDI file if the XML file contains errors, and as a result will generate an error.</span></span>  
  
## <a name="edi-promoted-properties-are-only-available-if-your-application-has-a-reference-to-the-biztalk-edi-application"></a><span data-ttu-id="6b7b4-144">EDI が昇格させたプロパティはのみ、アプリケーションが BizTalk EDI アプリケーションへの参照を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-144">EDI promoted properties are only available if your application has a reference to the BizTalk EDI application</span></span>  
 <span data-ttu-id="6b7b4-145">**現象**</span><span class="sxs-lookup"><span data-stu-id="6b7b4-145">**Symptom**</span></span>  
  
 <span data-ttu-id="6b7b4-146">EDI 名前空間で昇格させたプロパティを使用しようとしている昇格させたプロパティの一覧で、たとえば、オーケストレーションまたは送信ポートのフィルター条件では表示されません。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-146">Promoted properties under the EDI namespace are not displayed in the list of promoted properties that you are trying to use, for example, in an orchestration or in the filter conditions for a send port.</span></span>  
  
 <span data-ttu-id="6b7b4-147">**考えられる原因**</span><span class="sxs-lookup"><span data-stu-id="6b7b4-147">**Possible Cause**</span></span>  
  
 <span data-ttu-id="6b7b4-148">使用している BizTalk アプリケーションには、BizTalk EDI アプリケーションへの参照はありません。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-148">The BizTalk application that you are using does not have a reference to the BizTalk EDI Application.</span></span> <span data-ttu-id="6b7b4-149">EDI が昇格させたプロパティのプロパティ スキーマは、BizTalk EDI アプリケーションのリソース フォルダーに含まれている Microsoft.BizTalk.Edi.BaseArtifacts.dll 内です。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-149">The property schemas for the EDI promoted properties are in Microsoft.BizTalk.Edi.BaseArtifacts.dll, which is included in the Resources folder of BizTalk EDI Application.</span></span>  
  
 <span data-ttu-id="6b7b4-150">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="6b7b4-150">**Resolution**</span></span>  
  
 <span data-ttu-id="6b7b4-151">作業している BizTalk アプリケーションには、BizTalk EDI アプリケーションへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-151">To the BizTalk application that you are working in, add a reference to the BizTalk EDI Application.</span></span>  
  
## <a name="the-data-element-name-in-a-context-property-name-contains-an-underscore-not-a-period"></a><span data-ttu-id="6b7b4-152">コンテキスト プロパティ名でデータ要素名にアンダー スコア、ピリオドではありませんが含まれています</span><span class="sxs-lookup"><span data-stu-id="6b7b4-152">The Data Element Name in a Context Property Name Contains an Underscore, Not a Period</span></span>  
 <span data-ttu-id="6b7b4-153">EDI セグメント内のデータ要素の名前には、たとえば、UNB2.1、UNB2 送信者セグメントの id フィールドである、ピリオドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-153">The name of a data element within an EDI segment contains a period, for example, UNB2.1, which is the identification field for the UNB2 Sender segment.</span></span> <span data-ttu-id="6b7b4-154">ただし、データ要素名は、EDI コンテキスト プロパティの一部として含まれていますが、期間は、アンダー スコアに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-154">However, when the data element name is included as part of an EDI context property, the period is replaced with an underscore.</span></span> <span data-ttu-id="6b7b4-155">たとえば、送信者 Id データ要素のコンテキスト プロパティには、EDI です。UNB2_1、EDI ではありません。UNB2.1 します。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-155">For example, the context property for the Sender Identification data element is EDI.UNB2_1, not EDI.UNB2.1.</span></span> <span data-ttu-id="6b7b4-156">この理由は、コンテキスト プロパティ名でピリオドがサポートされていないことです。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-156">The reason for this is that a period is not supported in a context property name.</span></span>  
  
## <a name="irrelevant-string-is-appended-to-instance-validation-error-message"></a><span data-ttu-id="6b7b4-157">インスタンスの検証エラー メッセージに関連のない文字列が追加されます。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-157">Irrelevant string is appended to instance validation error message</span></span>  
 <span data-ttu-id="6b7b4-158">インスタンスの検証中にエラーを受信したときに、エラー メッセージに「BEC 2004」という文字列が追加されます。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-158">Whenever you receive an error during instance validation, the string "BEC 2004" will be appended to the error message.</span></span> <span data-ttu-id="6b7b4-159">この文字列を無視することができます。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-159">You can ignore this string.</span></span>  
  
## <a name="edifact-schema-names-are-case-sensitive"></a><span data-ttu-id="6b7b4-160">EDIFACT スキーマの名前が区別されます。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-160">EDIFACT Schema Names Are Case-Sensitive</span></span>  
 <span data-ttu-id="6b7b4-161">EDIFACT スキーマのスキーマ名、スキーマの root_reference データ要素で示すように小文字は区別されます。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-161">The schema name of an EDIFACT schema, as shown in the root_reference data element of the schema, is case-sensitive.</span></span> <span data-ttu-id="6b7b4-162">たとえば、EFACT_D98B_ORDERS と EFACT_d98B_Orders は 2 つの異なるスキーマです。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-162">For example, EFACT_D98B_ORDERS and EFACT_d98B_Orders would be two different schemas.</span></span>  
  
## <a name="invalid-edi-messages-can-be-suspended-even-if-edi-type-validation-is-disabled"></a><span data-ttu-id="6b7b4-163">EDI 型の検証が無効になっている場合でも、無効な EDI メッセージを中断することができます。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-163">Invalid EDI Messages Can Be Suspended Even If EDI Type Validation Is Disabled</span></span>  
 <span data-ttu-id="6b7b4-164">EDI 型の検証が無効になっている場合でも、EDI 構造検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-164">EDI structural validation is performed even if the EDI Type validation is disabled.</span></span> <span data-ttu-id="6b7b4-165">EDI 型の検証が無効になっている場合でも、基本的な構造検証に失敗したインターチェンジは保留されます。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-165">An interchange that fails the basic structural validations will be suspended, even if the EDI Type validation is disabled.</span></span>  
  
## <a name="the-edi-assembler-will-serialize-an-unbatched-interchange-even-if-a-separator-character-is-used-in-an-envelope-header"></a><span data-ttu-id="6b7b4-166">エンベロープ ヘッダーに区切り文字が使用される場合でも、EDI アセンブラーがバッチ処理されていないインターチェンジをシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-166">The EDI Assembler Will Serialize an Unbatched Interchange Even If a Separator Character Is Used in an Envelope Header</span></span>  
 <span data-ttu-id="6b7b4-167">インターチェンジ受信者としてのパーティに対して定義されている、ヘッダーおよびトレーラのフィールドを区切るために使用する区切り文字は、インターチェンジ、グループ、またはトランザクション セット ヘッダーやトレーラ フィールドのいずれかの定義では使用されませんする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-167">The separator characters used to separate header and trailer fields must not be used in the definition of any of the interchange, group, or transaction set header or trailer fields, as defined for the party as interchange receiver.</span></span> <span data-ttu-id="6b7b4-168">場合は、インターチェンジは送信側 BizTalk Server の EDI アセンブラーまたは受信側パーティの逆アセンブラーで処理に失敗します。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-168">If they are, the interchange will fail processing either in the EDI Assembler of the sending BizTalk Server or in the disassembler of the receiving party.</span></span> <span data-ttu-id="6b7b4-169">インターチェンジ失敗 EDI アセンブラーで、送信バッチの場合、アセンブラーはヘッダー制御 (サービス) スキーマと照らし合わせたエンベロープを検証します。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-169">The interchange will fail in the EDI Assembler if it is an outbound batch, because the Assembler will validate the envelope against the header control (service) schema.</span></span> <span data-ttu-id="6b7b4-170">インターチェンジがバッチでない場合、EDI アセンブラーがシリアル化できますが、受信側パーティの逆アセンブラーで処理は失敗します。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-170">If the interchange is unbatched, the EDI Assembler will serialize it, but it will fail processing in the disassembler at the receiving party.</span></span>  
  
## <a name="mismatched-character-sets-can-result-in-suspended-interchanges"></a><span data-ttu-id="6b7b4-171">文字セットの不一致によりインターチェンジの中断が生じる</span><span class="sxs-lookup"><span data-stu-id="6b7b4-171">Mismatched Character Sets Can Result in Suspended Interchanges</span></span>  
 <span data-ttu-id="6b7b4-172">送信インターチェンジに対して使用する文字セットは、インターチェンジに挿入するトランザクション セットを作成するために使用する文字セットと同じになります。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-172">The character set used for an outgoing interchange should be the same as the character set used to create the transaction sets inserted into the interchange.</span></span> <span data-ttu-id="6b7b4-173">ない場合は、無効な文字があったことを示すエラー メッセージでは、インターチェンジは中断可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-173">If not, the interchange will likely be suspended with an error message indicating that there were invalid characters.</span></span>  
  
 <span data-ttu-id="6b7b4-174">例: EDIFACT バッチを作成する場合、UNOA を使用して文字セットしますが、バッチに追加するトランザクション セットには、小文字の文字が含まれて、UNOA は小文字を許可していないために、バッチ処理オーケストレーションがメッセージを中断します。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-174">For example, if you create an EDIFACT batch using the UNOA character set, but a transaction set added to the batch has lower-case characters, the batching orchestration will suspend the message because UNOA does not allow lower-case characters.</span></span>  
  
 <span data-ttu-id="6b7b4-175">別の例として、"Basic"の文字セットでの X12 インターチェンジが X12 のバッチ処理に EDI 送信パイプラインを構成する場合がインターチェンジに小文字のため、X12 文字セットが X12 で選択したインターチェンジのエンベロープの生成 ページのパーティ エンベロープの設定が適用されると、インターチェンジの受信者は、「拡張」または"UTF8/Unicode"に設定されている、バッチのメッセージが中断されます。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-175">As another example, if you configure the EDI send pipeline for X12 interchanges with the "Basic" character set, but an X12 batched interchange has lower-case characters because the X12 character set selected in the X12 Interchange Envelop Generation page for the party as an interchange receiver is set to "Extended" or "UTF8/Unicode", the batched message will be suspended when envelope settings are applied.</span></span>  
  
## <a name="using-unh25-for-schema-resolution-requires-an-update-to-the-schema"></a><span data-ttu-id="6b7b4-176">スキーマの解決に UNH2.5 を使用して、スキーマの更新プログラムが必要です。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-176">Using UNH2.5 for schema resolution requires an update to the schema</span></span>  
 <span data-ttu-id="6b7b4-177">受信 EDIFACT インターチェンジのスキーマの解決に UNH2.5 (関連付けの割り当てコード) を使用する場合は、\Program Files\Microsoft BizTalk Server 20xx \schema フォルダーにある関連するドキュメント スキーマを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-177">If you use UNH2.5 (the Association assigned code) for schema resolution of an incoming EDIFACT interchange, you will need to update the relevant document schema in the \Program Files\Microsoft BizTalk Server 20xx\Schema folder.</span></span> <span data-ttu-id="6b7b4-178">Root_reference、display_reference、および xs:element name の既存の値に UNH2.5 の値を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-178">You will need to append the value of UNH2.5 to the existing values for the root_reference, display_reference, and xs:element name.</span></span> <span data-ttu-id="6b7b4-179">たとえば、UNH2.5 が"EAN008"EFACT_D96A_INVOIC スキーマを使用している場合は、root_reference、display_reference、および xs:element name を"EFACT_D96A_INVOIC_EAN008"を設定するとします。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-179">For example, if UNH2.5 is "EAN008" and you are using the EFACT_D96A_INVOIC schema, you would set root_reference, display_reference, and xs:element name to "EFACT_D96A_INVOIC_EAN008".</span></span>  
  
## <a name="the-compressed-file-of-schemas-will-be-replaced-when-an-upgrade-is-performed"></a><span data-ttu-id="6b7b4-180">アップグレードを実行するときに、スキーマの圧縮ファイルを置き換え、</span><span class="sxs-lookup"><span data-stu-id="6b7b4-180">The compressed file of schemas will be replaced when an upgrade is performed</span></span>  
 <span data-ttu-id="6b7b4-181">Microsoft をアップグレードする場合は[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アップグレードに関連付けられた MicrosoftEdiXSDTemplates.exe ファイルとそれ以降のビルドに、インストール内の MicrosoftEdiXSDTemplates.exe ファイルが置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-181">If you upgrade Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to a later build, the MicrosoftEdiXSDTemplates.exe file in your installation will be replaced with the MicrosoftEdiXSDTemplates.exe file associated with the upgrade.</span></span> <span data-ttu-id="6b7b4-182">引き続き古い圧縮ファイルからスキーマを使用する場合は、不要になったアクセスことは、圧縮ファイルに、アップグレード後に古い圧縮ファイルをバックアップする場合を除き。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-182">If you plan to continue to use the schemas from the old compressed file, you will no longer have access to the compressed file after the upgrade unless you back up the old compressed file.</span></span>  
  
## <a name="if-a-group-contains-multiple-x12-transaction-sets-all-must-be-of-the-same-type"></a><span data-ttu-id="6b7b4-183">グループには、複数の X12 が含まれている場合、トランザクション セットと同じ型のあるすべて必要があります</span><span class="sxs-lookup"><span data-stu-id="6b7b4-183">If a group contains multiple X12 transaction sets, all must be of the same type</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="6b7b4-184">同じグループ内の別のトランザクション セットの混在をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-184">does not support mixing different transaction sets within the same group.</span></span> <span data-ttu-id="6b7b4-185">グループに複数のトランザクションが含まれている場合、すべてのトランザクションの同じ ST01 の値がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-185">When a group contains multiple transactions, the value of ST01 must be the same for all transactions.</span></span>  
  
## <a name="receiving-x12-interchanges-that-contain-non-ascii-delimiters-may-result-in-the-message-becoming-suspended"></a><span data-ttu-id="6b7b4-186">受信 X12 インターチェンジが非 ASCII 区切り記号が含まれている可能性が、メッセージが中断</span><span class="sxs-lookup"><span data-stu-id="6b7b4-186">Receiving X12 interchanges that contain non-ASCII delimiters may result in the message becoming suspended</span></span>  
 <span data-ttu-id="6b7b4-187">**現象**</span><span class="sxs-lookup"><span data-stu-id="6b7b4-187">**Symptom**</span></span>  
  
 <span data-ttu-id="6b7b4-188">使用が非 ASCII 区切り記号の値、メッセージが中断されると、アプリケーション イベント ログに書き込まれるエラーの場合インターチェンジ受信 X12 です。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-188">When receiving an X12 interchange that uses non-ASCII delimiter values, the message may become suspended and an error written to the application event log.</span></span>  
  
 <span data-ttu-id="6b7b4-189">**考えられる原因**</span><span class="sxs-lookup"><span data-stu-id="6b7b4-189">**Possible Cause**</span></span>  
  
 <span data-ttu-id="6b7b4-190">この問題は、インターチェンジが utf-8 としてエンコードされていない場合に発生することができます。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-190">This problem can occur if the interchange is not encoded as UTF-8.</span></span>  
  
 <span data-ttu-id="6b7b4-191">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="6b7b4-191">**Resolution**</span></span>  
  
 <span data-ttu-id="6b7b4-192">非 ASCII 区切り記号を含むインターチェンジが utf-8 としてエンコードされた受信 X12 を確認します。</span><span class="sxs-lookup"><span data-stu-id="6b7b4-192">Ensure that any incoming X12 interchange that contains non-ASCII delimiters is encoded as UTF-8.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b7b4-193">参照</span><span class="sxs-lookup"><span data-stu-id="6b7b4-193">See Also</span></span>  
 <span data-ttu-id="6b7b4-194">[EDI の処理に関する既知の問題](../core/known-issues-with-edi-processing.md) </span><span class="sxs-lookup"><span data-stu-id="6b7b4-194">[Known Issues with EDI Processing](../core/known-issues-with-edi-processing.md) </span></span>  
 <span data-ttu-id="6b7b4-195">[EDI メッセージング](../core/edi-messaging.md) </span><span class="sxs-lookup"><span data-stu-id="6b7b4-195">[EDI Messaging](../core/edi-messaging.md) </span></span>  
 <span data-ttu-id="6b7b4-196">[EDI メッセージの検証](../core/edi-message-validation.md) </span><span class="sxs-lookup"><span data-stu-id="6b7b4-196">[EDI Message Validation](../core/edi-message-validation.md) </span></span>  
 <span data-ttu-id="6b7b4-197">[EDI スキーマ](../core/edi-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="6b7b4-197">[EDI Schemas](../core/edi-schemas.md) </span></span>  
 [<span data-ttu-id="6b7b4-198">EDI スキーマの開発</span><span class="sxs-lookup"><span data-stu-id="6b7b4-198">Developing EDI Schemas</span></span>](../core/developing-edi-schemas.md)