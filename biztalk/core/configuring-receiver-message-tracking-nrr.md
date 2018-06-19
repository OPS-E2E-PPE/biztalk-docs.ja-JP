---
title: 受信者メッセージの追跡 (NRR) の構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce30737a-341b-45be-81a0-a7336219185e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 942a9c62e69f9f39bf445f0b3028a4e6707f48d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233362"
---
# <a name="configuring-receiver-message-tracking-nrr"></a><span data-ttu-id="69c0f-102">受信者メッセージの追跡 (NRR) の構成</span><span class="sxs-lookup"><span data-stu-id="69c0f-102">Configuring Receiver Message Tracking (NRR)</span></span>
<span data-ttu-id="69c0f-103">このページの設定では、受信メッセージとその確認 (MDN) を否認不可データベースに格納するかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="69c0f-103">As part of the settings on this page, you can specify whether the inbound messages and their acknowledgements (MDNs) are stored in the non-repudiation database.</span></span> <span data-ttu-id="69c0f-104">詳細については、次を参照してください。 [BizTalk Server での AS2 処理](../core/as2-processing-in-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="69c0f-104">For more information, see [AS2 Processing in BizTalk Server](../core/as2-processing-in-biztalk-server.md).</span></span>  
  
 <span data-ttu-id="69c0f-105">否認不可データベースにメッセージを保存するには、AS2 アグリーメント プロパティの一部として NRR (Non-repudiation of receipt) を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="69c0f-105">To store messages in the non-repudiation database, the parties must enable NRR (Non-repudiation of receipt) as part of the AS2 agreement properties.</span></span> <span data-ttu-id="69c0f-106">NRR によって、送信側パーティは、メッセージ受信者からの署名付きの確認メッセージを検証できます。</span><span class="sxs-lookup"><span data-stu-id="69c0f-106">NRR ensures that the sender party has verified the signed receipt from the message recipient.</span></span> <span data-ttu-id="69c0f-107">概念上、NRR は、メッセージ送信者にとって、メッセージが変更されずに送信先に到達したことを示す確実な証拠です。</span><span class="sxs-lookup"><span data-stu-id="69c0f-107">Conceptually, an NRR is an undeniable proof for the message sender that the message reached the destination unaltered.</span></span> <span data-ttu-id="69c0f-108">NRR を確立できるのは、元のメッセージと確認メッセージが電子署名されている場合のみです。</span><span class="sxs-lookup"><span data-stu-id="69c0f-108">NRR can be established only when the original message and the receipt are digitally signed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="69c0f-109">プロパティが無効**パーティ A にパーティ B->** をオフにした場合は、一方向アグリーメント タブの**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する** チェック ボックスパーティ A の同じ ページで、ただし、すべてのプロパティが無効にします**パーティ B には、パーティ A が->**   タブの A の作成中に、チェック ボックスを選択した場合</span><span class="sxs-lookup"><span data-stu-id="69c0f-109">No properties are disabled on **Party A->Party B** one-way agreement tab if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box for Party A. However, all the properties are disabled on the same page in the **Party B->Party A** tab if you selected the check box while creating Party A.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="69c0f-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="69c0f-110">Prerequisites</span></span>  
 <span data-ttu-id="69c0f-111">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="69c0f-111">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-message-tracking-for-inbound-as2-messages-and-outbound-mdn"></a><span data-ttu-id="69c0f-112">受信 AS2 メッセージと送信 MDN のメッセージ追跡を構成するには</span><span class="sxs-lookup"><span data-stu-id="69c0f-112">To configure message tracking for inbound AS2 messages and outbound MDN</span></span>  
  
1.  <span data-ttu-id="69c0f-113">AS2 アグリーメントを作成する」の説明に従って[全般設定の構成 (AS2)](../core/configuring-general-settings-as2.md)です。</span><span class="sxs-lookup"><span data-stu-id="69c0f-113">Create an AS2 agreement as described in [Configuring General Settings (AS2)](../core/configuring-general-settings-as2.md).</span></span> <span data-ttu-id="69c0f-114">既存の AS2 アグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル** ページで、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="69c0f-114">To update an existing AS2 agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="69c0f-115">一方向アグリーメント タブの下にある**ローカル ホストの設定**セクションで、**受信者メッセージの追跡 (NRR)** です。</span><span class="sxs-lookup"><span data-stu-id="69c0f-115">On a one-way agreement tab, under **Local Host Settings** section, click **Receiver Message Tracking (NRR)**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="69c0f-116">受信の否認不可を確実に行うには、メッセージの認証と整合性を保証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69c0f-116">To guarantee non-repudiation of receipt, you must establish the authentication and integrity of the message.</span></span> <span data-ttu-id="69c0f-117">メッセージのデジタル署名を使用して認証と整合性を確立することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="69c0f-117">The recommended way of doing so is by using a digital signature on the message.</span></span> <span data-ttu-id="69c0f-118">結果として、否認不可データベースにメッセージを格納するプロパティのいずれかを選択した場合はメッセージに署名する を選択して、**メッセージに署名する必要があります**プロパティを**検証**ページ。</span><span class="sxs-lookup"><span data-stu-id="69c0f-118">As a result, if you select any of the properties to store messages in the non-repudiation database, you should sign the message by selecting the **Message should be signed** property on the **Validation** page.</span></span>  
  
3.  <span data-ttu-id="69c0f-119">選択**受信のエンコードされた AS2 メッセージの有効な NRR**にエンコードされた送信の AS2 メッセージを否認不可データベースに格納します。</span><span class="sxs-lookup"><span data-stu-id="69c0f-119">Select **NRR enabled for inbound encoded AS2 messages** to store outbound encoded AS2 messages in the non-repudiation database.</span></span>  
  
4.  <span data-ttu-id="69c0f-120">選択**受信のデコードされた AS2 メッセージの有効な NRR**送信のデコードされた AS2 メッセージを否認不可データベースに格納します。</span><span class="sxs-lookup"><span data-stu-id="69c0f-120">Select **NRR enabled for inbound decoded AS2 messages** to store outbound decoded AS2 messages in the non-repudiation database.</span></span>  
  
5.  <span data-ttu-id="69c0f-121">選択**送信 MDN の NRR の有効化**受信 MDN を否認不可データベースに格納します。</span><span class="sxs-lookup"><span data-stu-id="69c0f-121">Select **NRR enabled for outbound MDN** to store inbound MDN in the non-repudiation database.</span></span>  
  
6.  <span data-ttu-id="69c0f-122">をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="69c0f-122">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69c0f-123">参照</span><span class="sxs-lookup"><span data-stu-id="69c0f-123">See Also</span></span>  
 [<span data-ttu-id="69c0f-124">ローカル ホスト設定の構成 (AS2)</span><span class="sxs-lookup"><span data-stu-id="69c0f-124">Configuring Local Host Settings (AS2)</span></span>](../core/configuring-local-host-settings-as2.md)