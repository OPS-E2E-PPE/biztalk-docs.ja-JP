---
title: エラーのトラブルシューティング |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- errors, troubleshooting
- troubleshooting, errors
ms.assetid: 08cc95a3-4be9-450f-a015-e031011158f7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae7ad99b699da29d4d8680375f88e4d4a74ff66a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207170"
---
# <a name="troubleshooting-errors"></a><span data-ttu-id="6a73c-102">エラーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="6a73c-102">Troubleshooting Errors</span></span>
<span data-ttu-id="6a73c-103">このセクションの内容に関連する問題に対処[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]でエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="6a73c-103">This section addresses issues related to [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] generated errors.</span></span>  
  
## <a name="the-mllp-adapter-can-run-only-on-a-single-host-instance"></a><span data-ttu-id="6a73c-104">MLLP アダプターを 1 つのホスト インスタンスでのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="6a73c-104">The MLLP adapter can run only on a single host instance</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="6a73c-105">現象</span><span class="sxs-lookup"><span data-stu-id="6a73c-105">Symptom</span></span>  
 <span data-ttu-id="6a73c-106">トランスポートの種類が MLLP の受信場所と別の既存の受信場所よりも別の受信ハンドラーを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="6a73c-106">You cannot enable a receive location with a transport type of MLLP and a different receive handler than another existing receive location.</span></span> <span data-ttu-id="6a73c-107">さらに、参加させるし、別の既存の送信ポートよりも別の送信ハンドラーに送信ポートを開始できません。</span><span class="sxs-lookup"><span data-stu-id="6a73c-107">In addition, you cannot enlist and start a send port with a different send handler than another existing send port.</span></span>  
  
<span data-ttu-id="6a73c-108">**考えられる原因**: 使用できるは 1 つの MLLP のみハンドラーを単一のサーバー上の受信 (または送信) します。</span><span class="sxs-lookup"><span data-stu-id="6a73c-108">**Possible Cause** : You can only use one MLLP receive (or send) handler on a single server.</span></span> <span data-ttu-id="6a73c-109">さらに、URI が指定されている受信場所 (または送信ポート) の (MLLP トランスポートのプロパティ内のホスト名) は、"localhost"をする必要がありますか、または受信 (または送信) のアダプター ハンドラーのホストのインスタンスでサーバー名が実行されています。</span><span class="sxs-lookup"><span data-stu-id="6a73c-109">In addition, the URI designated for the receive location (or send port) (the Host name in the MLLP Transport Properties) must either be "localhost" or the server name where the host instance for the receive (or send) adapter handler is running.</span></span>  
  
<span data-ttu-id="6a73c-110">**解像度**: 単一のサーバーにすべて MLLP の受信場所 (または送信ポート) の同じ受信 (または送信) のハンドラーを指定します。</span><span class="sxs-lookup"><span data-stu-id="6a73c-110">**Resolution** : Designate the same receive (or send) handler for all MLLP receive locations (or send ports) on a single server.</span></span>  
  
## <a name="msh-and-ack-schemas-must-be-added-to-only-one-project"></a><span data-ttu-id="6a73c-111">MSH と確認のスキーマは、1 つしかプロジェクトに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a73c-111">MSH and ACK schemas must be added to only one project</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="6a73c-112">現象</span><span class="sxs-lookup"><span data-stu-id="6a73c-112">Symptom</span></span>  
 <span data-ttu-id="6a73c-113">プロジェクトをビルドしようとすると、次のエラーのいずれかを取得します。</span><span class="sxs-lookup"><span data-stu-id="6a73c-113">When you attempt to build a project, you get one of the following errors:</span></span>  
  
`Error: Cannot locate document specification as multiple schemas match the message type "http://microsoft.com/HealthCare/HL7/2X#MSH_24_GLO_DEF"`
  
`Schema http://microsoft.com/HealthCare/HL7/2X#MSH_24_GLO_DEF not found`
  
<span data-ttu-id="6a73c-114">**考えられる原因**:「MSH と確認のスキーマ (MSH_25_GLO_DEF.xsd と ACK_24_GLO_DEF.xsd) は、複数のプロジェクトで配置されています。</span><span class="sxs-lookup"><span data-stu-id="6a73c-114">**Possible Cause** : The MSH and ACK schemas (MSH_25_GLO_DEF.xsd and ACK_24_GLO_DEF.xsd) have been deployed in multiple projects.</span></span>  
  
<span data-ttu-id="6a73c-115">**解像度**: MSH_25_GLO_DEF.xsd と ACK_24_GLO_DEF.xsd が 1 つしかプロジェクトに追加されたことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6a73c-115">**Resolution** : Ensure that MSH_25_GLO_DEF.xsd and ACK_24_GLO_DEF.xsd have been added to only one project.</span></span>  
  
## <a name="exception-of-type-systemoutofmemoryexception-has-thrown-an-error-in-the-event-log"></a><span data-ttu-id="6a73c-116">System.OutOfMemoryException の種類の例外が、イベント ログにエラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="6a73c-116">Exception of type System.OutOfMemoryException has thrown an error in the Event Log</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="6a73c-117">現象</span><span class="sxs-lookup"><span data-stu-id="6a73c-117">Symptom</span></span>  
 <span data-ttu-id="6a73c-118">イベント ログに、次のようなエラーを取得します。</span><span class="sxs-lookup"><span data-stu-id="6a73c-118">You get the following or similar error in the Event Log:</span></span>  
  
`Exception of type System.OutOfMemoryException has thrown an error.`
  
<span data-ttu-id="6a73c-119">**考えられる原因**: 一部のメッセージの数が多いの処理中に[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]エンジン コンポーネント メモリ リークが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6a73c-119">**Possible Cause** : While processing a large number of messages, some [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] engine components may exhibit memory leaks.</span></span>  
  
<span data-ttu-id="6a73c-120">**解像度**: 再起動[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="6a73c-120">**Resolution** : Restart [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="header-serialization-generates-an-error-in-the-event-viewer"></a><span data-ttu-id="6a73c-121">ヘッダーのシリアル化では、イベント ビューアーにエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="6a73c-121">Header serialization generates an error in the Event Viewer</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="6a73c-122">現象</span><span class="sxs-lookup"><span data-stu-id="6a73c-122">Symptom</span></span>  
 <span data-ttu-id="6a73c-123">状態と動作状況の追跡 (HAT) ツールでメッセージが成功を示す場合でもは、イベント ログ内の次のようなエラーを取得します。</span><span class="sxs-lookup"><span data-stu-id="6a73c-123">You get the following or similar error in the Event Log, even though the message in the Health and Activity Tracking (HAT) tool indicates success:</span></span>  
  
`An error happened in the header during serialization.`
  
<span data-ttu-id="6a73c-124">**考えられる原因**: メッセージ ヘッダーの変換の値が正しく設定されていない[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。</span><span class="sxs-lookup"><span data-stu-id="6a73c-124">**Possible Cause** : The message header transformation value is not set correctly in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span>  
  
<span data-ttu-id="6a73c-125">**解像度**: の値が確認 MSH マップ[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。</span><span class="sxs-lookup"><span data-stu-id="6a73c-125">**Resolution** : Verify MSH map values in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span>  
  
## <a name="duplicate-event-id-4133-serializer-errors-are-logged"></a><span data-ttu-id="6a73c-126">イベント ID 4133 シリアライザーの重複エラーが記録されます。</span><span class="sxs-lookup"><span data-stu-id="6a73c-126">Duplicate Event ID 4133 serializer errors are logged</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="6a73c-127">現象</span><span class="sxs-lookup"><span data-stu-id="6a73c-127">Symptom</span></span>  
 <span data-ttu-id="6a73c-128">イベント ID 4133:「エラーが発生したヘッダーのシリアル化中に」は、無効な MSH11 値を持つメッセージのすべてのインスタンスに対して 2 回発生します。</span><span class="sxs-lookup"><span data-stu-id="6a73c-128">Event ID 4133 – "Error happened in header during serialization" occurs twice for every instance of a message with a MSH11 value that is not valid.</span></span>  
  
<span data-ttu-id="6a73c-129">**考えられる原因**: イベント ログに重複するエラーが発生しない (コミットおよびアプリケーション Ack) の 2 つの受信確認の処理中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="6a73c-129">**Possible Cause** : An error occurred while processing two acknowledgments (Commit and Application ACKs) without duplicate errors in the Event Log.</span></span> <span data-ttu-id="6a73c-130">代わりに、2 つの Ack の各イベント ID 4133 の 1 つが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6a73c-130">Instead, you receive one Event ID 4133 for each of the two ACKs.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="6a73c-131">各 ACK 生成用のログ エントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="6a73c-131"> creates a log entry for each ACK it generates.</span></span>  
  
<span data-ttu-id="6a73c-132">**解像度**: メッセージが正しく書式設定とデータが設定された MSH11 フィールドを持つことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6a73c-132">**Resolution** : Ensure that your messages have a correctly formatted and populated MSH11 field.</span></span>  
  
## <a name="send-pipeline-generates-an-error-when-using-the-2-way-mllp-adapter"></a><span data-ttu-id="6a73c-133">送信パイプラインで両方向 MLLP アダプターを使用するときにエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="6a73c-133">Send pipeline generates an error when using the 2-way MLLP adapter</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="6a73c-134">現象</span><span class="sxs-lookup"><span data-stu-id="6a73c-134">Symptom</span></span>  
 <span data-ttu-id="6a73c-135">イベント ログに、次のようなエラーを取得します。</span><span class="sxs-lookup"><span data-stu-id="6a73c-135">You get the following or similar error in the Event Log:</span></span>  
  
`There was a failure executing the send pipeline: "[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2XPipelines.[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2XSendPipeline" Source: "[!INCLUDE[btsCoName](../../includes/btsconame-md.md)].Solutions.[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].HL72fAsm" Send Port: "<*host name: port number*>" Reason: Message does not contain a part with name MSHSegment.`
  
<span data-ttu-id="6a73c-136">**考えられる原因**: 受信確認の受信側のアプリケーションが応答しないと[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]受信側のアプリケーションからの応答を指定してください。</span><span class="sxs-lookup"><span data-stu-id="6a73c-136">**Possible Cause** : The receiving application does not respond with an Acknowledgment and [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] is expecting a response from the receiving application.</span></span>  
  
<span data-ttu-id="6a73c-137">**解像度**: 仕様では、これは、エラー メッセージを無視することができます。</span><span class="sxs-lookup"><span data-stu-id="6a73c-137">**Resolution** : This is by design, and you can ignore the error message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a73c-138">参照</span><span class="sxs-lookup"><span data-stu-id="6a73c-138">See Also</span></span>  
 [<span data-ttu-id="6a73c-139">HL7 のトラブルシューティングと既知の問題</span><span class="sxs-lookup"><span data-stu-id="6a73c-139">Troubleshooting and known issues in HL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-and-known-issues-in-hl7.md)