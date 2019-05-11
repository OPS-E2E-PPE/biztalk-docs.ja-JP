---
title: 送信ポートの関連付け (AS2) の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8624d4c-cee8-4072-bff7-2468d83a06de
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00240fb0214d2c73cbe49920143399b5ca79c327
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355292"
---
# <a name="configuring-send-port-association-as2"></a><span data-ttu-id="7fd70-102">送信ポートの関連付けの構成 (AS2)</span><span class="sxs-lookup"><span data-stu-id="7fd70-102">Configuring Send Port Association (AS2)</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="7fd70-103">送信 AS2 メッセージのアグリーメントを解決するのには、ポートの関連付けを送信します。</span><span class="sxs-lookup"><span data-stu-id="7fd70-103">uses send port association to resolve an agreement for an outgoing AS2 message.</span></span> <span data-ttu-id="7fd70-104">AS2 メッセージは、アグリーメントに関連付けられている送信ポートとメッセージをサブスクライブした送信ポートを照合してアグリーメントに解決されます。</span><span class="sxs-lookup"><span data-stu-id="7fd70-104">An AS2 message is resolved to an agreement by matching the send port that subscribed to the message with the send port associated with an agreement.</span></span> <span data-ttu-id="7fd70-105">このトピックでは、アグリーメントに送信ポートに関連付ける方法の手順を示します。</span><span class="sxs-lookup"><span data-stu-id="7fd70-105">This topic provides instructions on how to associate send ports to an agreement.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7fd70-106">BizTalk Server では、送信ポートの関連付けはアグリーメント レベルでのみ行われます。</span><span class="sxs-lookup"><span data-stu-id="7fd70-106">In BizTalk Server, the send port association is done only at the agreement level.</span></span> <span data-ttu-id="7fd70-107">ただし、BizTalk Server 2009 で送信ポートが関連付けられているパーティ レベルで。</span><span class="sxs-lookup"><span data-stu-id="7fd70-107">However, in BizTalk Server 2009, the send ports were associated at the party level.</span></span> <span data-ttu-id="7fd70-108">旧バージョンとの互換性のため、**送信ポート**ページも用意されて、パーティのプロパティの一部として (を参照してください[構成の全般的なパーティ プロパティ (AS2)](../core/configuring-general-party-properties-as2.md))。</span><span class="sxs-lookup"><span data-stu-id="7fd70-108">For backward compatibility, a **Send Ports** page is also available as part of the party properties (see [Configuring General Party Properties (AS2)](../core/configuring-general-party-properties-as2.md)).</span></span> <span data-ttu-id="7fd70-109">送信ポートをアグリーメントと関連付けるたびに、送信ポート設定がパーティ設定にも反映され、このページにも送信ポートの関連付けが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7fd70-109">Whenever you associate a send port with an agreement, the send port setting is also propagated to the party setting and you can see the send port association in this page as well.</span></span> <span data-ttu-id="7fd70-110">ただし、その逆は真ではありません。</span><span class="sxs-lookup"><span data-stu-id="7fd70-110">However, the reverse is not true.</span></span> <span data-ttu-id="7fd70-111">送信ポートをパーティと関連付け、その送信ポートをアグリーメント設定の一部として自動的に利用可能にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7fd70-111">You cannot associate a send port with a party and then have that send port be automatically available as part of the agreement settings.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7fd70-112">オフにした場合に、このページで、送信ポートの関連付けグリッドが無効になって、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する**チェック ボックスを作成するパーティを作成するときにアグリーメント。</span><span class="sxs-lookup"><span data-stu-id="7fd70-112">The send port association grid is disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
>   
>  <span data-ttu-id="7fd70-113">グリッドは、パーティから送信されるインターチェンジのプロパティに対応する一方向アグリーメント タブでのみ無効になります。</span><span class="sxs-lookup"><span data-stu-id="7fd70-113">The grid is disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="7fd70-114">たとえば、2 つのパーティのパーティ A とパーティ B を作成して、チェック ボックスをオフにしたパーティ A について、グリッドが無効になりますで、**パーティ A にパーティ B]-> [** 一方向アグリーメント タブ。</span><span class="sxs-lookup"><span data-stu-id="7fd70-114">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the grid is disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7fd70-115">前提条件</span><span class="sxs-lookup"><span data-stu-id="7fd70-115">Prerequisites</span></span>  
 <span data-ttu-id="7fd70-116">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fd70-116">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-send-port-association"></a><span data-ttu-id="7fd70-117">送信ポートの関連付けを構成するには</span><span class="sxs-lookup"><span data-stu-id="7fd70-117">To configure send port association</span></span>  
  
1.  <span data-ttu-id="7fd70-118">AS2 契約の作成」の説明に従って[全般設定の構成 (AS2)](../core/configuring-general-settings-as2.md)します。</span><span class="sxs-lookup"><span data-stu-id="7fd70-118">Create an AS2 agreement as described in [Configuring General Settings (AS2)](../core/configuring-general-settings-as2.md).</span></span> <span data-ttu-id="7fd70-119">既存の AS2 アグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="7fd70-119">To update an existing AS2 agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="7fd70-120">一方向アグリーメント タブで、次のようにクリックします。**送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="7fd70-120">On a one-way agreement tab, click **Send Ports**.</span></span>  
  
3.  <span data-ttu-id="7fd70-121">空のセルをクリックして、**名前**列で、ドロップダウン リストから、アグリーメントと関連付ける送信ポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="7fd70-121">Click the empty cell under the **Name** column, and from the drop-down list, select the send port to associate with the agreement.</span></span> <span data-ttu-id="7fd70-122">**URI**列には、送信ポートのアドレスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7fd70-122">The **URI** column displays the send port address.</span></span>  
  
4.  <span data-ttu-id="7fd70-123">送信ポートの関連付けを削除する送信ポートの行を選択し、をクリックして**削除**します。</span><span class="sxs-lookup"><span data-stu-id="7fd70-123">To remove a send port association, select the row for a send port and click **Remove**.</span></span>  
  
5.  <span data-ttu-id="7fd70-124">送信ポートのプロパティを表示する送信ポートの行を選択し、をクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="7fd70-124">To see the properties for a send port, select the row for a send port and click **Properties**.</span></span>  
  
6.  <span data-ttu-id="7fd70-125">をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7fd70-125">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fd70-126">参照</span><span class="sxs-lookup"><span data-stu-id="7fd70-126">See Also</span></span>  
 [<span data-ttu-id="7fd70-127">AS2 アグリーメントのプロパティの構成</span><span class="sxs-lookup"><span data-stu-id="7fd70-127">Configuring AS2 Agreement Properties</span></span>](../core/configuring-as2-agreement-properties.md)