---
title: "送信ポートの関連付け (X12) の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 496beb0a-fabf-416e-bc3c-d8537097b50e
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d81eee157c84677470e542c5d4ee5f9bf2cb5df5
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="configuring-send-port-association-x12"></a><span data-ttu-id="f2625-102">送信ポートの関連付けの構成 (X12)</span><span class="sxs-lookup"><span data-stu-id="f2625-102">Configuring Send Port Association (X12)</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="f2625-103"> では送信ポートの関連付けを使用して、送信 EDI インターチェンジのアグリーメントを解決します。</span><span class="sxs-lookup"><span data-stu-id="f2625-103"> uses send port association to resolve an agreement for an outgoing EDI interchange.</span></span> <span data-ttu-id="f2625-104">メッセージにサブスクライブする送信ポートをアグリーメントと関連付けられた送信ポートと一致させることで、EDI インターチェンジはアグリーメントに解決されます。</span><span class="sxs-lookup"><span data-stu-id="f2625-104">An EDI interchange is resolved to an agreement by matching the send port that subscribed to the message with the send port associated with an agreement.</span></span> <span data-ttu-id="f2625-105">このトピックでは、送信ポートをアグリーメントと関連付ける方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f2625-105">This topic provides instructions on how to associate send ports to an agreement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f2625-106">1 つの送信ポートが複数のアグリーメントに関連付けられていると、BizTalk Server によってエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="f2625-106">If the same send port is associated with multiple agreements, BizTalk Server will generate an error.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f2625-107">BizTalk Server では、送信ポートの関連付けはアグリーメント レベルでのみ行われます。</span><span class="sxs-lookup"><span data-stu-id="f2625-107">In BizTalk Server, the send port association is done only at the agreement level.</span></span> <span data-ttu-id="f2625-108">ただし、BizTalk Server 2009 で送信ポートはパーティ レベルで関連付けられました。</span><span class="sxs-lookup"><span data-stu-id="f2625-108">However, in BizTalk Server 2009, the send ports were associated at the party level.</span></span> <span data-ttu-id="f2625-109">旧バージョンとの互換性のため、**送信ポート**ページも用意されて、パーティのプロパティの一部として (を参照してください[全般的なパーティ プロパティを構成する](../core/configuring-general-party-properties.md))。</span><span class="sxs-lookup"><span data-stu-id="f2625-109">For backward compatibility, a **Send Ports** page is also available as part of the party properties (see [Configuring General Party Properties](../core/configuring-general-party-properties.md)).</span></span> <span data-ttu-id="f2625-110">送信ポートをアグリーメントと関連付けるたびに、送信ポート設定がパーティ設定にも反映され、このページにも送信ポートの関連付けが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2625-110">Whenever you associate a send port with an agreement, the send port setting is also propagated to the party setting and you can see the send port association in this page as well.</span></span> <span data-ttu-id="f2625-111">ただし、その逆は真ではありません。</span><span class="sxs-lookup"><span data-stu-id="f2625-111">However, the reverse is not true.</span></span> <span data-ttu-id="f2625-112">送信ポートをパーティと関連付け、その送信ポートをアグリーメント設定の一部として自動的に利用可能にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f2625-112">You cannot associate a send port with a party and then have that send port be automatically available as part of the agreement settings.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f2625-113">ここで説明する設定は、HIPAA インターチェンジにも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="f2625-113">The settings described here also apply to HIPAA interchanges.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f2625-114">オフにした場合に、このページで、送信ポートの関連付けグリッドが無効になって、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する**チェック ボックスを作成するパーティを作成中にはアグリーメント。</span><span class="sxs-lookup"><span data-stu-id="f2625-114">The send port association grid is disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
>   
>  <span data-ttu-id="f2625-115">グリッドは、パーティから送信されるインターチェンジのプロパティに対応する一方向のアグリーメント タブでのみ無効になります。</span><span class="sxs-lookup"><span data-stu-id="f2625-115">The grid is disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="f2625-116">たとえば、2 つのパーティのパーティ A とパーティ B を作成して、パーティ A に対しては、チェック ボックスをオフ、グリッドが無効な場合、**パーティ A にパーティ B]-> [**一方向アグリーメント タブです。</span><span class="sxs-lookup"><span data-stu-id="f2625-116">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the grid is disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f2625-117">前提条件</span><span class="sxs-lookup"><span data-stu-id="f2625-117">Prerequisites</span></span>  
 <span data-ttu-id="f2625-118">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2625-118">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-associate-send-ports-with-an-agreement"></a><span data-ttu-id="f2625-119">送信ポートをアグリーメントと関連付けるには</span><span class="sxs-lookup"><span data-stu-id="f2625-119">To associate send ports with an agreement</span></span>  
  
1.  <span data-ttu-id="f2625-120">X12 エンコード アグリーメント」の説明に従って作成[全般設定を構成する (X12)](../core/configuring-general-settings-x12.md)です。</span><span class="sxs-lookup"><span data-stu-id="f2625-120">Create an X12 encoding agreement as described in [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span> <span data-ttu-id="f2625-121">既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル** ページで、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="f2625-121">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="f2625-122">一方向アグリーメント タブの下にある**インターチェンジの設定**セクションで、**送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="f2625-122">On a one-way agreement tab, under **Interchange Settings** section, click **Send Ports**.</span></span>  
  
3.  <span data-ttu-id="f2625-123">下の空のセルをクリックして、**名前**列で、ドロップダウン リストからアグリーメントと関連付ける送信ポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="f2625-123">Click the empty cell under the **Name** column, and from the drop-down list, select the send port to associate with the agreement.</span></span> <span data-ttu-id="f2625-124">**URI**列には、送信ポートのアドレスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2625-124">The **URI** column displays the send port address.</span></span>  
  
4.  <span data-ttu-id="f2625-125">送信ポートの関連付けを削除する送信ポートの行を選択し、をクリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="f2625-125">To remove a send port association, select the row for a send port and click **Remove**.</span></span>  
  
5.  <span data-ttu-id="f2625-126">送信ポートのプロパティを表示する送信ポートの行を選択し、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="f2625-126">To see the properties for a send port, select the row for a send port and click **Properties**.</span></span>  
  
6.  <span data-ttu-id="f2625-127">をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="f2625-127">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2625-128">参照</span><span class="sxs-lookup"><span data-stu-id="f2625-128">See Also</span></span>  
 [<span data-ttu-id="f2625-129">インターチェンジの設定の構成 (X12)</span><span class="sxs-lookup"><span data-stu-id="f2625-129">Configuring Interchange Settings (X12)</span></span>](../core/configuring-interchange-settings-x12.md)