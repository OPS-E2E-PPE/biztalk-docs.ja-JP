---
title: 既知の問題 EDI 受信処理 |Microsoft ドキュメント
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
ms.openlocfilehash: 75ab2769ab4a6eacf885dbf675a6bd3fda371007
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262962"
---
# <a name="known-issues-with-edi-receive-processing"></a><span data-ttu-id="dc68c-102">EDI 受信処理に関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="dc68c-102">Known Issues with EDI Receive Processing</span></span>
<span data-ttu-id="dc68c-103">このトピックでは、EDI 受信パイプラインでの処理に関する既知の問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="dc68c-103">This topic describes known issues with processing in the EDI receive pipeline.</span></span>  
  
## <a name="receive-side-processing-of-trailing-separators-fails"></a><span data-ttu-id="dc68c-104">末尾の区切り記号の受信側での処理が失敗する</span><span class="sxs-lookup"><span data-stu-id="dc68c-104">Receive-Side Processing of Trailing Separators Fails</span></span>  
 <span data-ttu-id="dc68c-105">**現象**</span><span class="sxs-lookup"><span data-stu-id="dc68c-105">**Symptom**</span></span>  
  
 <span data-ttu-id="dc68c-106">末尾に区切り記号のあるトランザクション セットは、X12 でエンコードされたメッセージの場合はエラー コード AK403= 6、EDIFACT でエンコードされたメッセージの場合はエラー コード UCM3=4/UCD1=45 によって失敗します。</span><span class="sxs-lookup"><span data-stu-id="dc68c-106">A transaction set with a trailing separator fails with error code AK403= 6 for an X12-encoded message or error codes UCM3=4/UCD1=45 for an EDIFACT-encoded message.</span></span>  
  
 <span data-ttu-id="dc68c-107">**考えられる原因**</span><span class="sxs-lookup"><span data-stu-id="dc68c-107">**Possible Cause**</span></span>  
  
 <span data-ttu-id="dc68c-108">末尾の区切り記号の処理が有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="dc68c-108">Processing of trailing separators is not enabled.</span></span>  
  
 <span data-ttu-id="dc68c-109">**解決策**</span><span class="sxs-lookup"><span data-stu-id="dc68c-109">**Resolution**</span></span>  
  
 <span data-ttu-id="dc68c-110">メッセージを送信したパーティの [EDI のプロパティ] を開きます。</span><span class="sxs-lookup"><span data-stu-id="dc68c-110">Open the EDI Properties for the party that sent the message.</span></span> <span data-ttu-id="dc68c-111">X12 または EDIFACT の [EDI のプロパティ] ダイアログ ボックスの [検証と確認の生成] ページで、[末尾の区切り記号を許可する] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="dc68c-111">In the Validation and ACK Generation page of the EDI Properties dialog box (for either X12 or EDIFACT), select "Allow trailing delimiter/separators".</span></span> <span data-ttu-id="dc68c-112">次に、[末尾の区切り記号に空の XML タグを作成する] をオンにすることにより、中間 XML で末尾の区切り記号として空の XML タグが作成されるように指定できます。</span><span class="sxs-lookup"><span data-stu-id="dc68c-112">After clicking this checkbox, you can specify that empty XML tags are created for trailing separators in the intermediate XML by clicking "Create empty XML tags for trailing separators".</span></span>  
  
## <a name="contrl-ack-is-enabled-but-not-generated"></a><span data-ttu-id="dc68c-113">CONTRL 確認は有効であるのに生成されない</span><span class="sxs-lookup"><span data-stu-id="dc68c-113">CONTRL ACK is enabled, but not generated</span></span>  
 <span data-ttu-id="dc68c-114">**現象**</span><span class="sxs-lookup"><span data-stu-id="dc68c-114">**Symptom**</span></span>  
  
 <span data-ttu-id="dc68c-115">送信元パーティの [検証と確認の生成] の [機能確認を生成する] チェック ボックスがオンになっているにもかかわらず、EDI 受信パイプラインによって CONTRL 確認が生成されていません。</span><span class="sxs-lookup"><span data-stu-id="dc68c-115">The Generate Functional ACK checkbox in the Validation and ACK Generation for the sending party is checked, but the EDI receive pipeline has not generated a CONTRL acknowledgment.</span></span>  
  
 <span data-ttu-id="dc68c-116">**考えられる原因**</span><span class="sxs-lookup"><span data-stu-id="dc68c-116">**Possible Cause**</span></span>  
  
 <span data-ttu-id="dc68c-117">CONTRL メッセージにはインターチェンジからコピーする必要のある必須データ要素がいくつか含まれています。</span><span class="sxs-lookup"><span data-stu-id="dc68c-117">The CONTRL message contains several mandatory data elements that must be copied from the interchange.</span></span> <span data-ttu-id="dc68c-118">インターチェンジ内のデータ要素が欠落しているか、構文が無効である場合、受信パイプラインは構文が有効な CONTRL メッセージを生成できません。</span><span class="sxs-lookup"><span data-stu-id="dc68c-118">If the data element in the interchange is missing or is syntactically invalid, the receive pipeline cannot generate a syntactically valid CONTRL message.</span></span>  
  
 <span data-ttu-id="dc68c-119">**解決策**</span><span class="sxs-lookup"><span data-stu-id="dc68c-119">**Resolution**</span></span>  
  
 <span data-ttu-id="dc68c-120">CONTRL 確認以外の方法でエラー状態を報告します。</span><span class="sxs-lookup"><span data-stu-id="dc68c-120">Report the error condition by some other means than a CONTRL acknowledgment.</span></span>  
  
## <a name="there-was-a-failure-executing-the-receive-pipeline-error-message"></a><span data-ttu-id="dc68c-121">「...、受信パイプラインを実行中にエラーが発生しました」</span><span class="sxs-lookup"><span data-stu-id="dc68c-121">"There Was a Failure Executing the Receive Pipeline…"</span></span> <span data-ttu-id="dc68c-122">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="dc68c-122">Error Message</span></span>  
 <span data-ttu-id="dc68c-123">**現象**</span><span class="sxs-lookup"><span data-stu-id="dc68c-123">**Symptom**</span></span>  
  
 <span data-ttu-id="dc68c-124">AS2 受信パイプラインを実行しようとすると、80040154 エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="dc68c-124">Attempting to run an AS2 receive pipeline results in an 80040154 error.</span></span>  
  
 <span data-ttu-id="dc68c-125">**考えられる原因**</span><span class="sxs-lookup"><span data-stu-id="dc68c-125">**Possible Cause**</span></span>  
  
 <span data-ttu-id="dc68c-126">64 ビットのホスト インスタンスではパイプラインがサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="dc68c-126">Pipelines are not supported on 64-bit host instances.</span></span>  
  
 <span data-ttu-id="dc68c-127">**解決策**</span><span class="sxs-lookup"><span data-stu-id="dc68c-127">**Resolution**</span></span>  
  
 <span data-ttu-id="dc68c-128">パイプラインを 32 ビットのホストと関連付けます。</span><span class="sxs-lookup"><span data-stu-id="dc68c-128">Associate the pipeline with a 32-bit host.</span></span>  
  
## <a name="an-x12-encoded-message-is-suspended-if-port-based-authentication-is-enabled-and-biztalk-server-does-not-have-access-to-the-authorization-and-security-information"></a><span data-ttu-id="dc68c-129">ポートベースの認証が有効で、BizTalk Server が認証情報およびセキュリティ情報にアクセスできない場合、X12 でエンコードされたメッセージが中断される</span><span class="sxs-lookup"><span data-stu-id="dc68c-129">An X12-Encoded Message Is Suspended If Port-Based Authentication Is Enabled and BizTalk Server Does Not Have Access to the Authorization and Security Information</span></span>  
 <span data-ttu-id="dc68c-130">**現象**</span><span class="sxs-lookup"><span data-stu-id="dc68c-130">**Symptom**</span></span>  
  
 <span data-ttu-id="dc68c-131">BizTalk Server は、認証が有効になっている受信ポートでメッセージを受信したときに、そのメッセージを送信したパーティを特定できなければ、メッセージを中断します。</span><span class="sxs-lookup"><span data-stu-id="dc68c-131">When a message is received over a receive port for which authentication is enabled, and the party that sent the message cannot be determined, BizTalk Server will suspend the message.</span></span>  
  
 <span data-ttu-id="dc68c-132">**考えられる原因**</span><span class="sxs-lookup"><span data-stu-id="dc68c-132">**Possible Cause**</span></span>  
  
 <span data-ttu-id="dc68c-133">受信ポートで認証が有効になっている (受信ポートの "認証しない" プロパティがオフになっている) 場合、インターチェンジを処理するためには、BizTalk Server で ISA1 ～ ISA2 (認証修飾子および認証情報) プロパティおよび ISA3 ～ ISA4 (セキュリティ修飾子およびセキュリティ情報) プロパティが設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc68c-133">If authentication is enabled for a receive port (the "No Authentication" property for the receive port is cleared), BizTalk Server requires settings for the "ISA1-2 (Authorization qualifier and information)" and "ISA3-4 (Security qualifier and information)" properties in order to process the interchange.</span></span> <span data-ttu-id="dc68c-134">これらのパーティのプロパティは、パーティの [X12 インターチェンジ処理のプロパティ] ページでインターチェンジの送信者として設定されます。</span><span class="sxs-lookup"><span data-stu-id="dc68c-134">These properties are set for a party in the X12 Interchange Processing Properties page for the party as an interchange sender.</span></span> <span data-ttu-id="dc68c-135">これらのプロパティの値を決定できない場合、BizTalk Server はメッセージを中断します。</span><span class="sxs-lookup"><span data-stu-id="dc68c-135">If BizTalk Server cannot determine the values of these properties, it will suspend the message.</span></span>  
  
 <span data-ttu-id="dc68c-136">これは、2 つの方法で発生します。</span><span class="sxs-lookup"><span data-stu-id="dc68c-136">This can occur in two ways.</span></span> <span data-ttu-id="dc68c-137">最初のケースでは、メッセージを送信したパーティを特定できない場合、BizTalk Server は EDI グローバル プロパティを使用するため、認証およびセキュリティの設定にアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="dc68c-137">In the first case, if BizTalk Server cannot determine the party that sent the message, it will use the EDI global properties and will not have access to the authorization and security settings.</span></span> <span data-ttu-id="dc68c-138">その結果、メッセージは中断されます。</span><span class="sxs-lookup"><span data-stu-id="dc68c-138">As a result, it will suspend the message.</span></span> <span data-ttu-id="dc68c-139">2 番目のケースでは、BizTalk Server には、パーティが決定されますが、パーティの ISA1 2 および ISA3 ~ 4 のプロパティが構成されていない場合、BizTalk Server がもう一度アクセス権がない承認およびセキュリティ情報にし、メッセージは中断されます。</span><span class="sxs-lookup"><span data-stu-id="dc68c-139">In the second case, if BizTalk Server determines the party, but the ISA1-2 and ISA3-4 properties for the party are not configured, BizTalk Server will again not have access to authorization and security information and will suspend the message.</span></span>  
  
 <span data-ttu-id="dc68c-140">**解決策**</span><span class="sxs-lookup"><span data-stu-id="dc68c-140">**Resolution**</span></span>  
  
 <span data-ttu-id="dc68c-141">メッセージの送信側パーティを識別できること、およびパーティ アグリーメントで ISA1 ～ ISA2 および ISA3 ～ ISA4 プロパティが定義されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dc68c-141">Make sure that the sending party for the message can be identified and that the ISA1-2 and ISA3-4 properties are defined in the party agreement.</span></span>  
  
## <a name="incorrect-se01-in-a-split-hipaa-subdocument"></a><span data-ttu-id="dc68c-142">分割された HIPAA サブドキュメントの SE01 に誤りがある</span><span class="sxs-lookup"><span data-stu-id="dc68c-142">Incorrect SE01 in a split HIPAA subdocument</span></span>  
 <span data-ttu-id="dc68c-143">**現象**</span><span class="sxs-lookup"><span data-stu-id="dc68c-143">**Symptom**</span></span>  
  
 <span data-ttu-id="dc68c-144">トランザクション セット トレーラー (SE01 フィールド) は、X12/HIPAA ドキュメントのヘッダー セグメントとトレーラー セグメントを含めたデータ セグメントの数を提供します。</span><span class="sxs-lookup"><span data-stu-id="dc68c-144">The transaction set trailer (SE01 field) provides a count of the data segments, including the header and trailer segments of an X12/HIPAA document.</span></span> <span data-ttu-id="dc68c-145">ただし、分割された HIPAA サブドキュメントの場合、EDI 受信パイプラインでは元のドキュメントと同じ SE01 値が適用され、再計算が行われません。</span><span class="sxs-lookup"><span data-stu-id="dc68c-145">However, for a split HIPAA sub document, the EDI receive pipeline applies the same SE01 value as the original document, instead of re-computing it.</span></span>  
  
 <span data-ttu-id="dc68c-146">**原因**</span><span class="sxs-lookup"><span data-stu-id="dc68c-146">**Cause**</span></span>  
  
 <span data-ttu-id="dc68c-147">EDI 受信パイプラインでは、元の HIPAA ドキュメントの SE01 値が分割されたサブドキュメントにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="dc68c-147">The EDI receive pipeline copies the value of SE01 from the original HIPAA document to a split sub document.</span></span>  
  
## <a name="error-message-for-duplicate-unb5-or-unh1-is-not-descriptive"></a><span data-ttu-id="dc68c-148">UNB5 または UNH1 の重複に対するエラー メッセージの記述内容が明確でない</span><span class="sxs-lookup"><span data-stu-id="dc68c-148">Error Message for Duplicate UNB5 or UNH1 Is Not Descriptive</span></span>  
 <span data-ttu-id="dc68c-149">UNB5 (インターチェンジ制御番号) または UNH1 (トランザクション セット参照番号) が重複したメッセージを受信した場合に表示されるエラー コードと説明は、問題の内容を明確に示しません。</span><span class="sxs-lookup"><span data-stu-id="dc68c-149">If BizTalk Server receives a message that has a duplicate UNB5 (interchange control number) or UNH1 (transaction set reference number), the error code and description that it posts will not clearly indicate the nature of the problem.</span></span>  
  
## <a name="biztalk-server-will-suspend-a-very-large-interchange-if-it-runs-out-of-memory"></a><span data-ttu-id="dc68c-150">メモリ不足になると BizTalk Server が大容量のインターチェンジを中断する</span><span class="sxs-lookup"><span data-stu-id="dc68c-150">BizTalk Server Will Suspend a Very Large Interchange If It Runs Out of Memory</span></span>  
 <span data-ttu-id="dc68c-151">大容量のインターチェンジを解析するとき、BizTalk Server はメモリ不足になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="dc68c-151">BizTalk Server may run out of memory when it parses a very large interchange.</span></span> <span data-ttu-id="dc68c-152">その場合、エラーが送信され、インターチェンジが中断されます。</span><span class="sxs-lookup"><span data-stu-id="dc68c-152">If it does, it will post an error and suspend the interchange.</span></span> <span data-ttu-id="dc68c-153">[グループ ハブ] ページでは、中断された大容量のインターチェンジの内容を確認できません。</span><span class="sxs-lookup"><span data-stu-id="dc68c-153">In the Group Hub page, you will not be able to see all of the contents of a very large interchange that has been suspended.</span></span> <span data-ttu-id="dc68c-154">メッセージの最初の部分を表示することができますが、BizTalk Server は表示できるように中断されたインターチェンジからのデータの量に制限されます。</span><span class="sxs-lookup"><span data-stu-id="dc68c-154">You will be able to see the initial part of the message, but BizTalk Server is limited in the amount of data from a suspended interchange that it can display.</span></span>  
  
## <a name="korean-characters-added-to-an-enumeration-in-a-kedifact-schema-must-be-in-unicode"></a><span data-ttu-id="dc68c-155">KEDIFACT スキーマで列挙に追加する韓国語の文字は UNICODE 形式である必要がある</span><span class="sxs-lookup"><span data-stu-id="dc68c-155">Korean Characters Added to an Enumeration in a KEDIFACT Schema Must Be in UNICODE</span></span>  
 <span data-ttu-id="dc68c-156">BizTalk Server は、KEDIFACT でエンコードされた韓国語の文字を含むインターチェンジを受信すると、UNB2 フィールドのコード ページ/文字セット値を使用してこのインターチェンジを処理します。</span><span class="sxs-lookup"><span data-stu-id="dc68c-156">When BizTalk Server receives a KEDIFACT-encoded interchange with Korean characters, it will use the code page/character set value in the UNB2 field to process the interchange.</span></span> <span data-ttu-id="dc68c-157">ただし、ID データ型の韓国語の文字を列挙に追加して KEDIFACT スキーマを変更する場合は、スキーマの冒頭で指定されているとおり、UTF-16 UNICODE の値を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc68c-157">However, if you modify a KEDIFACT schema by adding a Korean character with an ID data type to an enumeration, you must add the value in UTF-16 UNICODE, as specified at the top of the schema.</span></span>  
  
## <a name="executing-an-edi-receive-pipeline-from-within-an-orchestration-is-not-supported"></a><span data-ttu-id="dc68c-158">オーケストレーション内からの EDI 受信パイプラインの実行がサポートされない</span><span class="sxs-lookup"><span data-stu-id="dc68c-158">Executing an EDI Receive Pipeline from within an Orchestration Is Not Supported</span></span>  
 <span data-ttu-id="dc68c-159">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、通常はオーケストレーションの式図形内から受信パイプラインを実行できます。</span><span class="sxs-lookup"><span data-stu-id="dc68c-159">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can typically execute receive pipelines within an Expression shape in an orchestration.</span></span> <span data-ttu-id="dc68c-160">この機能は、EDIReceive パイプラインまたは AS2EdiReceive パイプラインについてはテストされていないため、サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="dc68c-160">This functionality has not been tested for the EDIReceive pipeline or the AS2EdiReceive pipeline, so is not supported.</span></span>  
  
## <a name="biztalk-edi-application-must-not-be-modified"></a><span data-ttu-id="dc68c-161">BizTalk EDI アプリケーションを変更できない</span><span class="sxs-lookup"><span data-stu-id="dc68c-161">BizTalk EDI Application Must Not Be Modified</span></span>  
 <span data-ttu-id="dc68c-162">BizTalk EDI アプリケーション内のアイテムは、変更または削除できません。</span><span class="sxs-lookup"><span data-stu-id="dc68c-162">Artifacts in the BizTalk EDI Application must not be modified or deleted.</span></span> <span data-ttu-id="dc68c-163">このアプリケーションを変更すると、EDI 機能や AS2 機能の構成を解除して再構成しても、元のアプリケーションを復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="dc68c-163">If this application is modified, there is no way for you to revert to the original application by unconfiguring and reconfiguring the EDI and AS2 features.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc68c-164">参照</span><span class="sxs-lookup"><span data-stu-id="dc68c-164">See Also</span></span>  
 <span data-ttu-id="dc68c-165">[EDI 処理に関する既知の問題](../core/known-issues-with-edi-processing.md) </span><span class="sxs-lookup"><span data-stu-id="dc68c-165">[Known Issues with EDI Processing](../core/known-issues-with-edi-processing.md) </span></span>  
 <span data-ttu-id="dc68c-166">[BizTalk Server が EDI メッセージを受信する方法](../core/how-biztalk-server-receives-edi-messages.md) </span><span class="sxs-lookup"><span data-stu-id="dc68c-166">[How BizTalk Server Receives EDI Messages](../core/how-biztalk-server-receives-edi-messages.md) </span></span>  
 [<span data-ttu-id="dc68c-167">チュートリアル (X12): EDI インターチェンジの受信と送信、受信確認</span><span class="sxs-lookup"><span data-stu-id="dc68c-167">Walkthrough (X12): Receiving EDI Interchanges and Sending Back an Acknowledgement</span></span>](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md)