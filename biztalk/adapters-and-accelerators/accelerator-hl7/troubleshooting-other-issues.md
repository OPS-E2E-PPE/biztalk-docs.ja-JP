---
title: その他の問題のトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting
ms.assetid: 1f115f64-45ce-445d-ab18-092f4a6a232c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2753d85050506d5b8ca05ca3b3438bb767a26322
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009499"
---
# <a name="troubleshooting-other-issues"></a><span data-ttu-id="1b849-102">その他の問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="1b849-102">Troubleshooting Other Issues</span></span>
<span data-ttu-id="1b849-103">Microsoft に関連するその他の問題に対処[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="1b849-103">Addresses other issues related to Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)].</span></span>  
  
## <a name="message-rejected-by-the-btahl7-engine"></a><span data-ttu-id="1b849-104">メッセージは、BTAHL7 エンジンによって拒否されました</span><span class="sxs-lookup"><span data-stu-id="1b849-104">Message rejected by the BTAHL7 engine</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="1b849-105">現象</span><span class="sxs-lookup"><span data-stu-id="1b849-105">Symptom</span></span>  
 <span data-ttu-id="1b849-106">メッセージは、メッセージ エンジンによってランダムに拒否されます。</span><span class="sxs-lookup"><span data-stu-id="1b849-106">Messages are randomly rejected by the message engine.</span></span>  
  
<span data-ttu-id="1b849-107">**考えられる原因**: HL7 標準に従って列挙の値に 0338 の表には、"L & は"の値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1b849-107">**Possible Cause** : According to the HL7 standard, enumeration values for table 0338 contains the "L&I" value.</span></span> <span data-ttu-id="1b849-108">PRA セグメントのフィールド 6 では、この値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="1b849-108">Field 6 of the PRA segment may contain this value.</span></span> <span data-ttu-id="1b849-109">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] "&"の文字を扱う、区切り記号として、メッセージは拒否されます。</span><span class="sxs-lookup"><span data-stu-id="1b849-109">Since [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] treats the "&" character as a delimiter, the message is rejected.</span></span>  
  
<span data-ttu-id="1b849-110">**解像度**: この問題の 3 つの考えられる解決策があります。</span><span class="sxs-lookup"><span data-stu-id="1b849-110">**Resolution** : There are three potential resolutions for this issue:</span></span>  
  
1.  <span data-ttu-id="1b849-111">メッセージのインスタンスでは、L\T\I 文字の組み合わせを使用するなど、エスケープ シーケンスを"&"の文字を処理します。</span><span class="sxs-lookup"><span data-stu-id="1b849-111">In the message instance, handle the "&" character through an escape sequence, such as using the character combination L\T\I.</span></span>  
  
2.  <span data-ttu-id="1b849-112">スキーマで PRA 6 で"LI"の列挙値を追加し、メッセージ インスタンスでこの値を代わりに使用します。</span><span class="sxs-lookup"><span data-stu-id="1b849-112">Add an enumeration value of "LI" at PRA 6 in the schema and use this value instead in the message instance.</span></span>  
  
3.  <span data-ttu-id="1b849-113">MSH2; でまったく異なるサブコンポーネントの区切り記号を使用します。ただし、この特定のソリューションは、環境に応じて現実的でない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1b849-113">Use a completely different subcomponent separator in MSH2; however, this particular solution may not be practical depending upon your environment.</span></span>  
  
## <a name="cannot-edit-the-hl7-schema-using-visual-studio"></a><span data-ttu-id="1b849-114">Visual Studio を使用して、HL7 スキーマを編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="1b849-114">Cannot edit the HL7 schema using Visual Studio</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="1b849-115">現象</span><span class="sxs-lookup"><span data-stu-id="1b849-115">Symptom</span></span>  
 <span data-ttu-id="1b849-116">Microsoft を使用して、HL7 スキーマを編集することはできません[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="1b849-116">Cannot edit the HL7 schema using Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
<span data-ttu-id="1b849-117">**考えられる原因**:[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]一部 HL7 スキーマはサポートしません。</span><span class="sxs-lookup"><span data-stu-id="1b849-117">**Possible Cause** : [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] does not support some HL7 schemas.</span></span>  
  
<span data-ttu-id="1b849-118">**解像度**: Microsoft メモ帳などの他のエディターを使用して、HL7 スキーマを編集します。</span><span class="sxs-lookup"><span data-stu-id="1b849-118">**Resolution** : Use other editors, such as Microsoft Notepad, to edit HL7 schemas.</span></span>  
  
## <a name="message-handling-fails-with-no-errors-logged"></a><span data-ttu-id="1b849-119">ログイン エラーのないメッセージの処理が失敗します。</span><span class="sxs-lookup"><span data-stu-id="1b849-119">Message handling fails with no errors logged</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="1b849-120">現象</span><span class="sxs-lookup"><span data-stu-id="1b849-120">Symptom</span></span>  
 <span data-ttu-id="1b849-121">システムは、エラー メッセージを記録または中断されたメッセージ キューにメッセージを配置することがなく、メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="1b849-121">The system processes messages without logging error messages or placing messages in the suspended message queue.</span></span>  
  
<span data-ttu-id="1b849-122">**考えられる原因**: **HeaderSpecType**と**DocumentSpecType**プロパティの値は大文字小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="1b849-122">**Possible Cause** : The **HeaderSpecType** and **DocumentSpecType** property values are case-sensitive.</span></span> <span data-ttu-id="1b849-123">パイプラインを展開するときにこれらの名前で入力ミスにメッセージをログに記録するエラーなしで削除し、べき可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1b849-123">When you deploy your pipelines, a typographical error in these names can cause messages to be mishandled and dropped with no errors logged.</span></span>  
  
<span data-ttu-id="1b849-124">**解像度**: を使用する場合は、大文字小文字の区別を観察、 **HeaderSpecType**と**DocumentSpecType**プロパティ値の名前。</span><span class="sxs-lookup"><span data-stu-id="1b849-124">**Resolution** : Observe case-sensitivity when using the **HeaderSpecType** and **DocumentSpecType** property value names.</span></span>  
  
## <a name="message-header-fields-are-not-validated-correctly"></a><span data-ttu-id="1b849-125">メッセージ ヘッダー フィールドが正しく検証されていません</span><span class="sxs-lookup"><span data-stu-id="1b849-125">Message header fields are not validated correctly</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="1b849-126">現象</span><span class="sxs-lookup"><span data-stu-id="1b849-126">Symptom</span></span>  
 <span data-ttu-id="1b849-127">ヘッダー フィールドの検証に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="1b849-127">Validation of a header field failed.</span></span>  
  
 <span data-ttu-id="1b849-128">理由:[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]シリアライザーは、実際のヘッダー フィールドのコンテキスト プロパティではなく、昇格されたプロパティを検証します。</span><span class="sxs-lookup"><span data-stu-id="1b849-128">Reason: The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] serializer validated a promoted property, not the actual header-field context property.</span></span>  
  
<span data-ttu-id="1b849-129">**考えられる原因**: を通じて、オーケストレーションやマップをヘッダーに対応する昇格させたプロパティに変更が発生しました。</span><span class="sxs-lookup"><span data-stu-id="1b849-129">**Possible Cause** : A change occurred to the promoted property corresponding to the header through an orchestration or a map.</span></span>  
  
<span data-ttu-id="1b849-130">**解像度**: MSH1、MSH2、および MSH5 メッセージ ヘッダーのコンテキスト プロパティ{1-3}のデータと同期されているように更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b849-130">**Resolution** : The context properties of message headers MSH1, MSH2, and MSH5{1-3} need to be updated so that they are in synchronization with the data.</span></span>  
  
## <a name="the-mllp-adapter-is-not-removed-during-uninstall"></a><span data-ttu-id="1b849-131">MLLP アダプターがアンインストール中に削除されません。</span><span class="sxs-lookup"><span data-stu-id="1b849-131">The MLLP adapter is not removed during uninstall</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="1b849-132">現象</span><span class="sxs-lookup"><span data-stu-id="1b849-132">Symptom</span></span>  
 <span data-ttu-id="1b849-133">BTAHL7 セットアップ プログラムは、BTAHL7 のアンインストール時に MLLP アダプターを削除できませんでした。</span><span class="sxs-lookup"><span data-stu-id="1b849-133">The BTAHL7 setup program did not remove the MLLP adapter during uninstallation of BTAHL7.</span></span>  
  
<span data-ttu-id="1b849-134">**考えられる原因**: トランスポートの種類が MLLP の受信場所または送信ポートが発生しました。</span><span class="sxs-lookup"><span data-stu-id="1b849-134">**Possible Cause** : There was a receive location or send port with a transport type of MLLP.</span></span> <span data-ttu-id="1b849-135">いずれかの BizTalk Server プロジェクトで参照されている場合、BTAHL7 セットアップは MLLP アダプターを削除できません。</span><span class="sxs-lookup"><span data-stu-id="1b849-135">BTAHL7 setup cannot remove the MLLP adapter if it is being referenced in any of the BizTalk Server projects.</span></span>  
  
<span data-ttu-id="1b849-136">**解像度**: BTAHL7 のアンインストールが完了すると、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1b849-136">**Resolution** : After uninstallation of BTAHL7 has completed, do the following:</span></span>  
  
1.  <span data-ttu-id="1b849-137">BizTalk Server 管理コンソールでは、すべての受信場所を削除し、トランスポートの種類が MLLP の受信場所のトランスポートの種類を変更または別の型への送信ポートまたはポートを送信します。</span><span class="sxs-lookup"><span data-stu-id="1b849-137">In the BizTalk Server Administration Console, remove all receive locations and send ports that have a transport type of MLLP, or change the transport type of the receive locations or send ports to another type.</span></span>  
  
2.  <span data-ttu-id="1b849-138">管理コンソールで、MLLP アダプターを削除します。</span><span class="sxs-lookup"><span data-stu-id="1b849-138">In the Administration Console, delete the MLLP adapter.</span></span>  
  
3.  <span data-ttu-id="1b849-139">ホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="1b849-139">Restart the host instance.</span></span>  
  
## <a name="btahl7-cannot-be-uninstalled-if-biztalk-server-has-already-been-uninstalled"></a><span data-ttu-id="1b849-140">BizTalk Server が既にアンインストールされている場合は、BTAHL7 をアンインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="1b849-140">BTAHL7 cannot be uninstalled if BizTalk Server has already been uninstalled</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="1b849-141">現象</span><span class="sxs-lookup"><span data-stu-id="1b849-141">Symptom</span></span>  
 <span data-ttu-id="1b849-142">アンインストール[!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]次のエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="1b849-142">Uninstalling [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)] results in the following error:</span></span>  
  
`A network error while attempting to read from file C:\Windows\Installer\Microsoft BizTalk <version\> Accelerator for HL7.msi`
  
<span data-ttu-id="1b849-143">**考えられる原因**:[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]のアンインストールの前にアンインストールされました[!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]しようとしました。</span><span class="sxs-lookup"><span data-stu-id="1b849-143">**Possible Cause** : [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] was uninstalled before uninstallation of [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)] was attempted.</span></span> <span data-ttu-id="1b849-144">アンインストールする必要があります[!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]アンインストールする前に[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="1b849-144">You must uninstall [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)] before uninstalling [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
<span data-ttu-id="1b849-145">**解像度**: 再インストール[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]をアンインストールして[!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]、し、アンインストール[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="1b849-145">**Resolution** : Reinstall [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)], then uninstall [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)], and then uninstall [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="messages-are-still-sent-after-the-applicable-mllp-send-port-has-been-stopped"></a><span data-ttu-id="1b849-146">MLLP 送信ポートが停止した後、メッセージは送信もされます。</span><span class="sxs-lookup"><span data-stu-id="1b849-146">Messages are still sent after the applicable MLLP send port has been stopped</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="1b849-147">現象</span><span class="sxs-lookup"><span data-stu-id="1b849-147">Symptom</span></span>  
 <span data-ttu-id="1b849-148">した後、MLLP 送信ポート、送信ポート経由で送信されたメッセージの停止が停止しないを引き続き送信されます。</span><span class="sxs-lookup"><span data-stu-id="1b849-148">After you stop an MLLP send port, the messages that are sent through that send port do not stop, but continue to be sent.</span></span>  
  
<span data-ttu-id="1b849-149">**考えられる原因**: 送信ポートを停止すると、BizTalk ホストを停止することで削除されるまで、接続が確立されているのままになります。</span><span class="sxs-lookup"><span data-stu-id="1b849-149">**Possible Cause** : When you stop a send port, the connection remains established until it is removed by stopping the BizTalk host.</span></span> <span data-ttu-id="1b849-150">その結果、送信ポートが停止した後、メッセージは送信も。</span><span class="sxs-lookup"><span data-stu-id="1b849-150">As a result, messages are still sent after the send port has been stopped.</span></span> <span data-ttu-id="1b849-151">これには、Biztalk Server の起動または送信ポートの停止中に呼び出し、MLLP アダプターを行わないために発生します。</span><span class="sxs-lookup"><span data-stu-id="1b849-151">This occurs because Biztalk Server does not call into the MLLP adapter during start or stop of the send port.</span></span> <span data-ttu-id="1b849-152">BizTalk Server は、開始およびホスト サービスの停止中にのみ、MLLP アダプターを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="1b849-152">BizTalk Server calls into the MLLP adapter only during the start and stop of the host service.</span></span>  
  
<span data-ttu-id="1b849-153">**解像度**: メッセージの送信接続と停止を削除するには、停止する送信ポートの送信ハンドラーのホスト インスタンスを停止しています。</span><span class="sxs-lookup"><span data-stu-id="1b849-153">**Resolution** : You can remove the connection and stop transmission of messages by stopping the host instance that is the send handler for the send port that you stopped.</span></span> <span data-ttu-id="1b849-154">ただし、そのホスト インスタンスを停止すると停止したくないその他のメッセージが影響する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1b849-154">However, stopping that host instance might affect other messages that you do not want to stop.</span></span> <span data-ttu-id="1b849-155">ケースであることがわかっている場合、作成するときに異なる方法で送信ポートを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b849-155">If you know that this is the case, you should configure the send port differently when you create it.</span></span> <span data-ttu-id="1b849-156">この MLLP 送信ポートのみ (または、送信ポートのサブセット) の送信ハンドラーとして機能する別のホスト インスタンスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b849-156">You should create another host instance to serve as the send handler for only this MLLP send port (or a subset of your send ports).</span></span> <span data-ttu-id="1b849-157">このホスト インスタンスを停止することで、この送信ポートからメッセージの送信を停止できます。</span><span class="sxs-lookup"><span data-stu-id="1b849-157">You can then stop transmission of messages from this send port by stopping this host instance.</span></span> <span data-ttu-id="1b849-158">影響はありません他の送信ハンドラーを使用するその他の送信ポートの他のメッセージの送信。</span><span class="sxs-lookup"><span data-stu-id="1b849-158">This will then not affect transmission of other messages on other send ports that use other send handlers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b849-159">参照</span><span class="sxs-lookup"><span data-stu-id="1b849-159">See Also</span></span>  
 [<span data-ttu-id="1b849-160">HL7 のトラブルシューティングと既知の問題</span><span class="sxs-lookup"><span data-stu-id="1b849-160">Troubleshooting and known issues in HL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-and-known-issues-in-hl7.md)