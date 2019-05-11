---
title: 既知の問題では、EDI 受信処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bbb3fd6a-381b-479e-a9f2-7b6371fac39e
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 734a093a554f01b8625d8cd1ba8f154153d33979
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330239"
---
# <a name="known-issues-with-edi-receive-processing"></a><span data-ttu-id="4a2a4-102">既知の問題では、EDI 受信処理</span><span class="sxs-lookup"><span data-stu-id="4a2a4-102">Known Issues with EDI Receive Processing</span></span>
<span data-ttu-id="4a2a4-103">このトピックでは、処理に関する既知の問題を説明します。 edi 受信パイプライン。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-103">This topic describes known issues with processing in the EDI receive pipeline.</span></span>  
  
## <a name="receive-side-processing-of-trailing-separators-fails"></a><span data-ttu-id="4a2a4-104">末尾の区切り記号の受信側処理に失敗します。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-104">Receive-Side Processing of Trailing Separators Fails</span></span>  
 <span data-ttu-id="4a2a4-105">**現象**</span><span class="sxs-lookup"><span data-stu-id="4a2a4-105">**Symptom**</span></span>  
  
 <span data-ttu-id="4a2a4-106">末尾の区切り記号と、トランザクション セットが失敗し、エラー コード AK403 = 6、X12 でエンコードされたメッセージまたはエラー コードの UCM3 = 4/UCD1 = 45、EDIFACT でエンコードされたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-106">A transaction set with a trailing separator fails with error code AK403= 6 for an X12-encoded message or error codes UCM3=4/UCD1=45 for an EDIFACT-encoded message.</span></span>  
  
 <span data-ttu-id="4a2a4-107">**考えられる原因**</span><span class="sxs-lookup"><span data-stu-id="4a2a4-107">**Possible Cause**</span></span>  
  
 <span data-ttu-id="4a2a4-108">末尾の区切り記号の処理が有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-108">Processing of trailing separators is not enabled.</span></span>  
  
 <span data-ttu-id="4a2a4-109">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="4a2a4-109">**Resolution**</span></span>  
  
 <span data-ttu-id="4a2a4-110">メッセージを送信したパーティの EDI のプロパティを開きます。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-110">Open the EDI Properties for the party that sent the message.</span></span> <span data-ttu-id="4a2a4-111">(X12 または EDIFACT) の EDI のプロパティ ダイアログ ボックスの 検証と確認の生成 ページでは、"末尾の区切り記号/区切り記号を許可する を選択します。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-111">In the Validation and ACK Generation page of the EDI Properties dialog box (for either X12 or EDIFACT), select "Allow trailing delimiter/separators".</span></span> <span data-ttu-id="4a2a4-112">このチェック ボックスをクリックすると、末尾の区切り記号の中間 XML で"末尾の区切り記号に空の XML タグを作成 をクリックして、空の XML タグが作成されたことを指定できます。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-112">After clicking this checkbox, you can specify that empty XML tags are created for trailing separators in the intermediate XML by clicking "Create empty XML tags for trailing separators".</span></span>  
  
## <a name="contrl-ack-is-enabled-but-not-generated"></a><span data-ttu-id="4a2a4-113">CONTRL 確認を有効にするが生成されません。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-113">CONTRL ACK is enabled, but not generated</span></span>  
 <span data-ttu-id="4a2a4-114">**現象**</span><span class="sxs-lookup"><span data-stu-id="4a2a4-114">**Symptom**</span></span>  
  
 <span data-ttu-id="4a2a4-115">検証と確認の生成で機能確認の生成のチェック ボックス、送信元パーティがオンになっていますが、EDI 受信パイプラインが生成されません CONTRL 受信確認。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-115">The Generate Functional ACK checkbox in the Validation and ACK Generation for the sending party is checked, but the EDI receive pipeline has not generated a CONTRL acknowledgment.</span></span>  
  
 <span data-ttu-id="4a2a4-116">**考えられる原因**</span><span class="sxs-lookup"><span data-stu-id="4a2a4-116">**Possible Cause**</span></span>  
  
 <span data-ttu-id="4a2a4-117">CONTRL メッセージには、インターチェンジからコピーする必要があるいくつかの必須データ要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-117">The CONTRL message contains several mandatory data elements that must be copied from the interchange.</span></span> <span data-ttu-id="4a2a4-118">場合は、インターチェンジのデータ要素が存在しないか、構文が無効、受信パイプラインは構文的に有効な CONTRL メッセージを生成できません。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-118">If the data element in the interchange is missing or is syntactically invalid, the receive pipeline cannot generate a syntactically valid CONTRL message.</span></span>  
  
 <span data-ttu-id="4a2a4-119">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="4a2a4-119">**Resolution**</span></span>  
  
 <span data-ttu-id="4a2a4-120">CONTRL 確認以外の他の方法でエラーを報告します。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-120">Report the error condition by some other means than a CONTRL acknowledgment.</span></span>  
  
## <a name="there-was-a-failure-executing-the-receive-pipeline-error-message"></a><span data-ttu-id="4a2a4-121">「...、受信パイプラインの実行中にエラーが発生しました」エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="4a2a4-121">"There Was a Failure Executing the Receive Pipeline…" Error Message</span></span>  
 <span data-ttu-id="4a2a4-122">**現象**</span><span class="sxs-lookup"><span data-stu-id="4a2a4-122">**Symptom**</span></span>  
  
 <span data-ttu-id="4a2a4-123">AS2 を実行しようとしています。 受信パイプライン、80040154 エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-123">Attempting to run an AS2 receive pipeline results in an 80040154 error.</span></span>  
  
 <span data-ttu-id="4a2a4-124">**考えられる原因**</span><span class="sxs-lookup"><span data-stu-id="4a2a4-124">**Possible Cause**</span></span>  
  
 <span data-ttu-id="4a2a4-125">パイプラインは、64 ビット ホスト インスタンスではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-125">Pipelines are not supported on 64-bit host instances.</span></span>  
  
 <span data-ttu-id="4a2a4-126">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="4a2a4-126">**Resolution**</span></span>  
  
 <span data-ttu-id="4a2a4-127">パイプラインを 32 ビットのホストに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-127">Associate the pipeline with a 32-bit host.</span></span>  
  
## <a name="an-x12-encoded-message-is-suspended-if-port-based-authentication-is-enabled-and-biztalk-server-does-not-have-access-to-the-authorization-and-security-information"></a><span data-ttu-id="4a2a4-128">ポート ベースの認証が有効になっているし、BizTalk Server では、承認、およびセキュリティ情報にアクセスできない場合、X12 でエンコードされたメッセージが中断されます。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-128">An X12-Encoded Message Is Suspended If Port-Based Authentication Is Enabled and BizTalk Server Does Not Have Access to the Authorization and Security Information</span></span>  
 <span data-ttu-id="4a2a4-129">**現象**</span><span class="sxs-lookup"><span data-stu-id="4a2a4-129">**Symptom**</span></span>  
  
 <span data-ttu-id="4a2a4-130">認証が有効になっていると、メッセージを特定できないを送信したパーティの受信ポートでメッセージが受信されると、BizTalk Server には、メッセージが中断されます。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-130">When a message is received over a receive port for which authentication is enabled, and the party that sent the message cannot be determined, BizTalk Server will suspend the message.</span></span>  
  
 <span data-ttu-id="4a2a4-131">**考えられる原因**</span><span class="sxs-lookup"><span data-stu-id="4a2a4-131">**Possible Cause**</span></span>  
  
 <span data-ttu-id="4a2a4-132">BizTalk Server が、「ISA1-2 (認証修飾子およびセキュリティ情報)」の設定が必要です (受信ポートの [認証なし] プロパティがオフ)、受信ポートの認証が有効な場合、「ISA3 ~ 4 (セキュリティ修飾子およびセキュリティ情報)」インターチェンジを処理するためにプロパティです。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-132">If authentication is enabled for a receive port (the "No Authentication" property for the receive port is cleared), BizTalk Server requires settings for the "ISA1-2 (Authorization qualifier and information)" and "ISA3-4 (Security qualifier and information)" properties in order to process the interchange.</span></span> <span data-ttu-id="4a2a4-133">これらのプロパティは、x12 の場合、パーティの設定は、インターチェンジの送信者としてのパーティのインターチェンジ処理のプロパティ ページ。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-133">These properties are set for a party in the X12 Interchange Processing Properties page for the party as an interchange sender.</span></span> <span data-ttu-id="4a2a4-134">BizTalk Server がこれらのプロパティの値を判別できない場合、メッセージは中断されます。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-134">If BizTalk Server cannot determine the values of these properties, it will suspend the message.</span></span>  
  
 <span data-ttu-id="4a2a4-135">これは、2 つの方法で発生します。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-135">This can occur in two ways.</span></span> <span data-ttu-id="4a2a4-136">最初のケースでは、BizTalk Server は、メッセージを送信したパーティを決定できない場合は EDI グローバル プロパティを使用し、承認およびセキュリティ設定へのアクセスはありません。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-136">In the first case, if BizTalk Server cannot determine the party that sent the message, it will use the EDI global properties and will not have access to the authorization and security settings.</span></span> <span data-ttu-id="4a2a4-137">その結果、メッセージは中断されます。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-137">As a result, it will suspend the message.</span></span> <span data-ttu-id="4a2a4-138">2 番目のケースでは、BizTalk Server は、パーティを決定しますが、パーティの ISA1 2 および ISA3 ~ 4 のプロパティが構成されていない場合、BizTalk Server がもう一度、承認およびセキュリティ情報へのアクセスと、メッセージは中断されます。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-138">In the second case, if BizTalk Server determines the party, but the ISA1-2 and ISA3-4 properties for the party are not configured, BizTalk Server will again not have access to authorization and security information and will suspend the message.</span></span>  
  
 <span data-ttu-id="4a2a4-139">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="4a2a4-139">**Resolution**</span></span>  
  
 <span data-ttu-id="4a2a4-140">メッセージの送信元パーティを識別でき、パーティ アグリーメントで ISA1 ~ 2 および ISA3 ~ 4 のプロパティが定義されているようにします。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-140">Make sure that the sending party for the message can be identified and that the ISA1-2 and ISA3-4 properties are defined in the party agreement.</span></span>  
  
## <a name="incorrect-se01-in-a-split-hipaa-subdocument"></a><span data-ttu-id="4a2a4-141">分割された HIPAA サブドキュメントの SE01 が正しくないです。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-141">Incorrect SE01 in a split HIPAA subdocument</span></span>  
 <span data-ttu-id="4a2a4-142">**現象**</span><span class="sxs-lookup"><span data-stu-id="4a2a4-142">**Symptom**</span></span>  
  
 <span data-ttu-id="4a2a4-143">トランザクション セット トレーラー (SE01 フィールド) は、X12 または HIPAA ドキュメントのヘッダーおよびトレーラ セグメントを含む、データ セグメントの数を提供します。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-143">The transaction set trailer (SE01 field) provides a count of the data segments, including the header and trailer segments of an X12/HIPAA document.</span></span> <span data-ttu-id="4a2a4-144">ただし、分割 HIPAA をサブ ドキュメントの場合、EDI 受信パイプラインには再計算ではなく、元のドキュメントと同じ SE01 値が適用されます。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-144">However, for a split HIPAA sub document, the EDI receive pipeline applies the same SE01 value as the original document, instead of re-computing it.</span></span>  
  
 <span data-ttu-id="4a2a4-145">**原因**</span><span class="sxs-lookup"><span data-stu-id="4a2a4-145">**Cause**</span></span>  
  
 <span data-ttu-id="4a2a4-146">EDI 受信パイプラインのコピーの SE01 値元の HIPAA ドキュメントから分割サブ ドキュメントにします。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-146">The EDI receive pipeline copies the value of SE01 from the original HIPAA document to a split sub document.</span></span>  
  
## <a name="error-message-for-duplicate-unb5-or-unh1-is-not-descriptive"></a><span data-ttu-id="4a2a4-147">重複する UNB5 または UNH1 のエラー メッセージの説明がないです。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-147">Error Message for Duplicate UNB5 or UNH1 Is Not Descriptive</span></span>  
 <span data-ttu-id="4a2a4-148">BizTalk Server は、重複する UNB5 を持つメッセージを受信した場合 (インターチェンジ制御番号) または UNH1 (トランザクション セット参照番号) は、エラー コードとポストバックの説明は明確に示しません問題の種類。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-148">If BizTalk Server receives a message that has a duplicate UNB5 (interchange control number) or UNH1 (transaction set reference number), the error code and description that it posts will not clearly indicate the nature of the problem.</span></span>  
  
## <a name="biztalk-server-will-suspend-a-very-large-interchange-if-it-runs-out-of-memory"></a><span data-ttu-id="4a2a4-149">BizTalk Server は、メモリが不足している場合、大容量のインターチェンジは中断します。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-149">BizTalk Server Will Suspend a Very Large Interchange If It Runs Out of Memory</span></span>  
 <span data-ttu-id="4a2a4-150">BizTalk Server は、大容量のインターチェンジを解析するときにメモリ不足実行可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-150">BizTalk Server may run out of memory when it parses a very large interchange.</span></span> <span data-ttu-id="4a2a4-151">その場合が、エラーが送信され、インターチェンジを中断します。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-151">If it does, it will post an error and suspend the interchange.</span></span> <span data-ttu-id="4a2a4-152">グループ ハブ ページでは、すべての中断された大容量のインターチェンジの内容を表示できませんされます。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-152">In the Group Hub page, you will not be able to see all of the contents of a very large interchange that has been suspended.</span></span> <span data-ttu-id="4a2a4-153">メッセージの最初の部分を表示することができますが、BizTalk Server が表示できる中断されたインターチェンジからのデータの量に制限されています。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-153">You will be able to see the initial part of the message, but BizTalk Server is limited in the amount of data from a suspended interchange that it can display.</span></span>  
  
## <a name="korean-characters-added-to-an-enumeration-in-a-kedifact-schema-must-be-in-unicode"></a><span data-ttu-id="4a2a4-154">KEDIFACT スキーマで列挙に追加された韓国語の文字が UNICODE である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-154">Korean Characters Added to an Enumeration in a KEDIFACT Schema Must Be in UNICODE</span></span>  
 <span data-ttu-id="4a2a4-155">BizTalk サーバーでは、韓国語の文字で KEDIFACT でエンコードされたインターチェンジを受信すると、インターチェンジを処理するのにコード ページ/文字セット値 UNB2 フィールドで使用されます。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-155">When BizTalk Server receives a KEDIFACT-encoded interchange with Korean characters, it will use the code page/character set value in the UNB2 field to process the interchange.</span></span> <span data-ttu-id="4a2a4-156">ただし、列挙型に ID データ型の韓国語の文字を追加して KEDIFACT スキーマを変更する場合スキーマの上部にある指定された値、utf-16 UNICODE に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-156">However, if you modify a KEDIFACT schema by adding a Korean character with an ID data type to an enumeration, you must add the value in UTF-16 UNICODE, as specified at the top of the schema.</span></span>  
  
## <a name="executing-an-edi-receive-pipeline-from-within-an-orchestration-is-not-supported"></a><span data-ttu-id="4a2a4-157">受信パイプラインの実行、EDI 内から、オーケストレーションはサポートされていません</span><span class="sxs-lookup"><span data-stu-id="4a2a4-157">Executing an EDI Receive Pipeline from within an Orchestration Is Not Supported</span></span>  
 <span data-ttu-id="4a2a4-158">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、通常実行することができます、オーケストレーションの式図形内からパイプラインを受信します。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-158">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can typically execute receive pipelines within an Expression shape in an orchestration.</span></span> <span data-ttu-id="4a2a4-159">この機能は、EDIReceive パイプラインまたは AS2EdiReceive パイプラインは、サポートされていないためにテストされていません。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-159">This functionality has not been tested for the EDIReceive pipeline or the AS2EdiReceive pipeline, so is not supported.</span></span>  
  
## <a name="biztalk-edi-application-must-not-be-modified"></a><span data-ttu-id="4a2a4-160">BizTalk EDI アプリケーションを変更する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-160">BizTalk EDI Application Must Not Be Modified</span></span>  
 <span data-ttu-id="4a2a4-161">BizTalk EDI アプリケーションのアイテムを変更または削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-161">Artifacts in the BizTalk EDI Application must not be modified or deleted.</span></span> <span data-ttu-id="4a2a4-162">このアプリケーションが変更された場合は、構成を解除し、EDI および AS2 機能を再構成して、元のアプリケーションを復元する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="4a2a4-162">If this application is modified, there is no way for you to revert to the original application by unconfiguring and reconfiguring the EDI and AS2 features.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a2a4-163">参照</span><span class="sxs-lookup"><span data-stu-id="4a2a4-163">See Also</span></span>  
 <span data-ttu-id="4a2a4-164">[EDI の処理に関する既知の問題](../core/known-issues-with-edi-processing.md) </span><span class="sxs-lookup"><span data-stu-id="4a2a4-164">[Known Issues with EDI Processing](../core/known-issues-with-edi-processing.md) </span></span>  
 <span data-ttu-id="4a2a4-165">[BizTalk Server が EDI メッセージを受信する方法](../core/how-biztalk-server-receives-edi-messages.md) </span><span class="sxs-lookup"><span data-stu-id="4a2a4-165">[How BizTalk Server Receives EDI Messages](../core/how-biztalk-server-receives-edi-messages.md) </span></span>  
 [<span data-ttu-id="4a2a4-166">チュートリアル (X12):EDI インターチェンジの受信と受信確認の送信</span><span class="sxs-lookup"><span data-stu-id="4a2a4-166">Walkthrough (X12): Receiving EDI Interchanges and Sending Back an Acknowledgement</span></span>](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md)