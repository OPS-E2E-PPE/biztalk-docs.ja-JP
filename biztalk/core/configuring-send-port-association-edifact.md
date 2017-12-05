---
title: "送信ポートの関連付け (EDIFACT) の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d7faabc7-072c-408c-bbd5-f0a039be81f8
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 629bde13f8edc9074b3e6bcb4741746e3de8e1a6
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="configuring-send-port-association-edifact"></a><span data-ttu-id="639ac-102">送信ポートの関連付けの構成 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="639ac-102">Configuring Send Port Association (EDIFACT)</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="639ac-103"> では送信ポートの関連付けを使用して、送信 EDI インターチェンジのアグリーメントを解決します。</span><span class="sxs-lookup"><span data-stu-id="639ac-103"> uses send port association to resolve an agreement for an outgoing EDI interchange.</span></span> <span data-ttu-id="639ac-104">メッセージにサブスクライブする送信ポートをアグリーメントと関連付けられた送信ポートと一致させることで、EDI インターチェンジはアグリーメントに解決されます。</span><span class="sxs-lookup"><span data-stu-id="639ac-104">An EDI interchange is resolved to an agreement by matching the send port that subscribed to the message with the send port associated with an agreement.</span></span> <span data-ttu-id="639ac-105">このトピックでは、送信ポートをアグリーメントと関連付ける方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="639ac-105">This topic provides instructions on how to associate send ports to an agreement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="639ac-106">1 つの送信ポートが複数のアグリーメントに関連付けられていると、BizTalk Server によってエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="639ac-106">If the same send port is associated with multiple agreements, BizTalk Server will generate an error.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="639ac-107">BizTalk Server では、送信ポートの関連付けはアグリーメント レベルでのみ行われます。</span><span class="sxs-lookup"><span data-stu-id="639ac-107">In BizTalk Server, the send port association is done only at the agreement level.</span></span> <span data-ttu-id="639ac-108">ただし、BizTalk Server 2009 で送信ポートはパーティ レベルで関連付けられました。</span><span class="sxs-lookup"><span data-stu-id="639ac-108">However, in BizTalk Server 2009, the send ports were associated at the party level.</span></span> <span data-ttu-id="639ac-109">旧バージョンとの互換性のため、**送信ポート**ページも用意されて、パーティのプロパティの一部として (を参照してください[全般的なパーティ プロパティを構成する](../core/configuring-general-party-properties.md))。</span><span class="sxs-lookup"><span data-stu-id="639ac-109">For backward compatibility, a **Send Ports** page is also available as part of the party properties (see [Configuring General Party Properties](../core/configuring-general-party-properties.md)).</span></span> <span data-ttu-id="639ac-110">送信ポートをアグリーメントと関連付けるたびに、送信ポート設定がパーティ設定にも反映され、このページにも送信ポートの関連付けが表示されます。</span><span class="sxs-lookup"><span data-stu-id="639ac-110">Whenever you associate a send port with an agreement, the send port setting is also propagated to the party setting and you can see the send port association in this page as well.</span></span> <span data-ttu-id="639ac-111">ただし、その逆は真ではありません。</span><span class="sxs-lookup"><span data-stu-id="639ac-111">However, the reverse is not true.</span></span> <span data-ttu-id="639ac-112">送信ポートをパーティと関連付け、その送信ポートをアグリーメント設定の一部として自動的に利用可能にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="639ac-112">You cannot associate a send port with a party and then have that send port be automatically available as part of the agreement settings.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="639ac-113">オフにした場合に、このページで、送信ポートの関連付けグリッドが無効になって、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する**チェック ボックスを作成するパーティを作成中にはアグリーメント。</span><span class="sxs-lookup"><span data-stu-id="639ac-113">The send port association grid is disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
>   
>  <span data-ttu-id="639ac-114">グリッドは、パーティから送信されるインターチェンジのプロパティに対応する一方向のアグリーメント タブでのみ無効になります。</span><span class="sxs-lookup"><span data-stu-id="639ac-114">The grid is disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="639ac-115">たとえば、2 つのパーティのパーティ A とパーティ B を作成して、パーティ A に対しては、チェック ボックスをオフ、グリッドが無効な場合、**パーティ A にパーティ B]-> [**一方向アグリーメント タブです。</span><span class="sxs-lookup"><span data-stu-id="639ac-115">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the grid is disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="639ac-116">前提条件</span><span class="sxs-lookup"><span data-stu-id="639ac-116">Prerequisites</span></span>  
 <span data-ttu-id="639ac-117">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="639ac-117">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-associate-send-ports-with-an-agreement"></a><span data-ttu-id="639ac-118">送信ポートをアグリーメントと関連付けるには</span><span class="sxs-lookup"><span data-stu-id="639ac-118">To associate send ports with an agreement</span></span>  
  
1.  <span data-ttu-id="639ac-119">EDIFACT」の説明に従ってエンコード アグリーメントを作成する[を構成する一般的な設定 (EDIFACT)](../core/configuring-general-settings-edifact.md)です。</span><span class="sxs-lookup"><span data-stu-id="639ac-119">Create an EDIFACT encoding agreement as described in [Configuring General Settings (EDIFACT)](../core/configuring-general-settings-edifact.md).</span></span> <span data-ttu-id="639ac-120">既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル** ページで、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="639ac-120">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="639ac-121">一方向アグリーメント タブの下にある**インターチェンジの設定**セクションで、**送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="639ac-121">On a one-way agreement tab, under **Interchange Settings** section, click **Send Ports**.</span></span>  
  
3.  <span data-ttu-id="639ac-122">下の空のセルをクリックして、**名前**列で、ドロップダウン リストからアグリーメントと関連付ける送信ポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="639ac-122">Click the empty cell under the **Name** column, and from the drop-down list, select the send port to associate with the agreement.</span></span> <span data-ttu-id="639ac-123">**URI**列には、送信ポートのアドレスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="639ac-123">The **URI** column displays the send port address.</span></span>  
  
4.  <span data-ttu-id="639ac-124">送信ポートの関連付けを削除する送信ポートの行を選択し、をクリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="639ac-124">To remove a send port association, select the row for a send port and click **Remove**.</span></span>  
  
5.  <span data-ttu-id="639ac-125">送信ポートのプロパティを表示する送信ポートの行を選択し、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="639ac-125">To see the properties for a send port, select the row for a send port and click **Properties**.</span></span>  
  
6.  <span data-ttu-id="639ac-126">をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="639ac-126">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="639ac-127">参照</span><span class="sxs-lookup"><span data-stu-id="639ac-127">See Also</span></span>  
 [<span data-ttu-id="639ac-128">インターチェンジの設定の構成 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="639ac-128">Configuring Interchange Settings (EDIFACT)</span></span>](../core/configuring-interchange-settings-edifact.md)