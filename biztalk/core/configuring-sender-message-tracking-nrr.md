---
title: 送信者メッセージ追跡 (NRR) の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e6ca2709-ac4b-48c0-82f8-8a43971a86cb
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c920328b86569a24c510d463f55aaaea6480fbe1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390756"
---
# <a name="configuring-sender-message-tracking-nrr"></a><span data-ttu-id="816c8-102">送信者メッセージ追跡 (NRR) を構成します。</span><span class="sxs-lookup"><span data-stu-id="816c8-102">Configuring Sender Message Tracking (NRR)</span></span>
<span data-ttu-id="816c8-103">このページの設定の一部として、送信メッセージとその確認 (Mdn) が、否認不可データベースに格納されているかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="816c8-103">As part of the settings on this page, you can specify whether the outbound messages and their acknowledgements (MDNs) are stored in the non-repudiation database.</span></span> <span data-ttu-id="816c8-104">詳細については、次を参照してください。 [BizTalk Server での AS2 処理](../core/as2-processing-in-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="816c8-104">For more information, see [AS2 Processing in BizTalk Server](../core/as2-processing-in-biztalk-server.md).</span></span>  
  
 <span data-ttu-id="816c8-105">否認不可データベースにメッセージを保存するには、は、パーティが AS2 アグリーメントのプロパティの一部として NRR (受信の否認) を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="816c8-105">To store messages in the non-repudiation database, the parties must enable NRR (Non-repudiation of receipt) as part of the AS2 agreement properties.</span></span> <span data-ttu-id="816c8-106">NRR によって、メッセージの受信者からの署名の確認メッセージを送信者のパーティが確認する必要があること。</span><span class="sxs-lookup"><span data-stu-id="816c8-106">NRR ensures that the sender party has verified the signed receipt from the message recipient.</span></span> <span data-ttu-id="816c8-107">概念的には、NRR は変更されずに送信先に到達するメッセージの送信者に否定の証拠です。</span><span class="sxs-lookup"><span data-stu-id="816c8-107">Conceptually, an NRR is an undeniable proof for the message sender that the message reached the destination unaltered.</span></span> <span data-ttu-id="816c8-108">元のメッセージと確認メッセージがデジタル署名されている場合にのみ、NRR を確立できます。</span><span class="sxs-lookup"><span data-stu-id="816c8-108">NRR can be established only when the original message and the receipt are digitally signed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="816c8-109">オフにした場合、このページで、すべてのプロパティが無効に、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する**チェック ボックスを作成するパーティを作成するときに、契約です。</span><span class="sxs-lookup"><span data-stu-id="816c8-109">All the properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
>   
>  <span data-ttu-id="816c8-110">プロパティが無効になるのは、パーティから受信中のインターチェンジのプロパティに対応する一方向のアグリーメント タブ上のみです。</span><span class="sxs-lookup"><span data-stu-id="816c8-110">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="816c8-111">たとえば、2 つのパーティのパーティ A とパーティ B を作成するチェック ボックスをオフにしたパーティ A の場合は、上記のプロパティが無効になります、**パーティ A にパーティ B]-> [** 一方向アグリーメント タブ。</span><span class="sxs-lookup"><span data-stu-id="816c8-111">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="816c8-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="816c8-112">Prerequisites</span></span>  
 <span data-ttu-id="816c8-113">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="816c8-113">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-message-tracking-for-outbound-as2-messages-and-inbound-mdn"></a><span data-ttu-id="816c8-114">送信 AS2 メッセージのメッセージの追跡と受信 MDN を構成するには</span><span class="sxs-lookup"><span data-stu-id="816c8-114">To configure message tracking for outbound AS2 messages and inbound MDN</span></span>  
  
1.  <span data-ttu-id="816c8-115">AS2 契約の作成」の説明に従って[全般設定の構成 (AS2)](../core/configuring-general-settings-as2.md)します。</span><span class="sxs-lookup"><span data-stu-id="816c8-115">Create an AS2 agreement as described in [Configuring General Settings (AS2)](../core/configuring-general-settings-as2.md).</span></span> <span data-ttu-id="816c8-116">既存の AS2 アグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="816c8-116">To update an existing AS2 agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="816c8-117">一方向アグリーメント タブで、**ローカル ホスト設定**セクションで、**送信者メッセージ追跡 (NRR)** します。</span><span class="sxs-lookup"><span data-stu-id="816c8-117">On a one-way agreement tab, under **Local Host Settings** section, click **Sender Message Tracking (NRR)**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="816c8-118">受信の否認を保証するためには、認証とメッセージの整合性を確立する必要があります。</span><span class="sxs-lookup"><span data-stu-id="816c8-118">To guarantee non-repudiation of receipt, you must establish the authentication and integrity of the message.</span></span> <span data-ttu-id="816c8-119">実行のお勧めの方法は、メッセージのデジタル署名を使用してためです。</span><span class="sxs-lookup"><span data-stu-id="816c8-119">The recommended way of doing so is by using a digital signature on the message.</span></span> <span data-ttu-id="816c8-120">その結果、否認不可データベースにメッセージを格納するプロパティのいずれかを選択した場合はメッセージに署名するを選択して、**メッセージに署名する必要があります**プロパティを**検証**ページ。</span><span class="sxs-lookup"><span data-stu-id="816c8-120">As a result, if you select any of the properties to store messages in the non-repudiation database, you should sign the message by selecting the **Message should be signed** property on the **Validation** page.</span></span>  
  
3.  <span data-ttu-id="816c8-121">選択**エンコードされた送信の AS2 メッセージに対して有効な NRR**エンコードされた AS2 メッセージを送信を否認不可データベースに格納します。</span><span class="sxs-lookup"><span data-stu-id="816c8-121">Select **NRR enabled for outbound encoded AS2 messages** to store outbound encoded AS2 messages in the non-repudiation database.</span></span>  
  
4.  <span data-ttu-id="816c8-122">選択**送信のデコードされた AS2 メッセージに対して有効な NRR**デコードされた AS2 メッセージを送信を否認不可データベースに格納します。</span><span class="sxs-lookup"><span data-stu-id="816c8-122">Select **NRR enabled for outbound decoded AS2 messages** to store outbound decoded AS2 messages in the non-repudiation database.</span></span>  
  
5.  <span data-ttu-id="816c8-123">選択**受信 MDN の NRR の有効化**受信 MDN を否認不可データベースに格納します。</span><span class="sxs-lookup"><span data-stu-id="816c8-123">Select **NRR enabled for inbound MDN** to store inbound MDN in the non-repudiation database.</span></span>  
  
6.  <span data-ttu-id="816c8-124">をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="816c8-124">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="816c8-125">参照</span><span class="sxs-lookup"><span data-stu-id="816c8-125">See Also</span></span>  
 [<span data-ttu-id="816c8-126">ローカル ホスト設定の構成 (AS2)</span><span class="sxs-lookup"><span data-stu-id="816c8-126">Configuring Local Host Settings (AS2)</span></span>](../core/configuring-local-host-settings-as2.md)