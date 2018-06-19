---
title: SQL を使用したトランザクションの分離レベルとトランザクションのタイムアウトを構成する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55355272-60c0-49e4-b37e-9198458ab305
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e75d63118c24602439434c9c7ba281fa9cbc7805
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222370"
---
# <a name="configure-transaction-isolation-level-and-transaction-timeout-with-sql"></a><span data-ttu-id="5ec30-102">SQL を使用したトランザクションの分離レベルとトランザクションのタイムアウトを構成します。</span><span class="sxs-lookup"><span data-stu-id="5ec30-102">Configure Transaction Isolation Level and Transaction Timeout with SQL</span></span>
<span data-ttu-id="5ec30-103">入力方向の操作 (ポーリングおよび通知) を実行中を使用して、[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、トランザクション分離レベルとトランザクションのタイムアウト値を適切に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ec30-103">While performing inbound operations (Polling and Notification) using the [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you should appropriately configure the transaction isolation level and the transaction timeout values.</span></span> <span data-ttu-id="5ec30-104">これを行うには :</span><span class="sxs-lookup"><span data-stu-id="5ec30-104">To do this:</span></span>  
  
1.  <span data-ttu-id="5ec30-105">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="5ec30-105">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="5ec30-106">コンソール ツリーで、展開、 **BizTalk グループ**、順に展開**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="5ec30-106">In the console tree, expand the **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="5ec30-107">展開するアプリケーションを展開し、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="5ec30-107">Expand the application under which you want to deploy the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
4.  <span data-ttu-id="5ec30-108">右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="5ec30-108">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
5.  <span data-ttu-id="5ec30-109">**受信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、受信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="5ec30-109">In the **Receive Port Properties** dialog box, on the **General** tab, type a name for the receive port.</span></span>  
  
6.  <span data-ttu-id="5ec30-110">左側のウィンドウで、**受信ポートのプロパティ**ダイアログ ボックスで、をクリックして**受信場所**、順にクリック**新規**受信場所を新しい定義の右側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="5ec30-110">In the left pane of the **Receive Port Properties** dialog box, click **Receive Locations**, and then click **New** in the right pane to define a new receive location.</span></span>  
  
7.  <span data-ttu-id="5ec30-111">**受信場所のプロパティ**ダイアログ ボックスで、をクリックして**Wcf-custom**で、**型** ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="5ec30-111">In the **Receive Location Properties** dialog box, click **WCF-Custom** in the **Type** list.</span></span>  
  
8.  <span data-ttu-id="5ec30-112">をクリックして**構成**の横にある、**型** ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="5ec30-112">Click **Configure** adjacent to the **Type** list.</span></span>  
  
9. <span data-ttu-id="5ec30-113">**Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**動作**タブです。</span><span class="sxs-lookup"><span data-stu-id="5ec30-113">In the **WCF-Custom Transport Properties** dialog box, click the **Behavior** tab.</span></span>  
  
10. <span data-ttu-id="5ec30-114">**動作**ボックスの一覧を右クリックして**ServiceBehavior**、 をクリック**拡張機能を追加**です。</span><span class="sxs-lookup"><span data-stu-id="5ec30-114">In the **Behavior** list, right-click **ServiceBehavior**, and click **Add extension**.</span></span>  
  
11. <span data-ttu-id="5ec30-115">**動作拡張機能の選択**ダイアログ ボックスで、 **sqlAdapterInboundTransactionBehavior**、 をクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="5ec30-115">In the **Select Behavior Extension** dialog box, select **sqlAdapterInboundTransactionBehavior**, and click **OK**.</span></span>  
  
12. <span data-ttu-id="5ec30-116">左側のウィンドウで、 **Wcf-custom トランスポートのプロパティ**、select、 **sqlAdapterInboundTransactionBehavior**下にあるサービス**ServiceBehavior**です。</span><span class="sxs-lookup"><span data-stu-id="5ec30-116">In the left pane of the **WCF-Custom Transport Properties**, select the **sqlAdapterInboundTransactionBehavior** service under **ServiceBehavior**.</span></span> <span data-ttu-id="5ec30-117">受信 (受信操作のメッセージ)、1 つを使用して、sqlAdapterInboundTransactionBehavior 分離レベルを制御し、既定値は**ReadCommitted**です。</span><span class="sxs-lookup"><span data-stu-id="5ec30-117">For receive (Inbound operation message), one can use the sqlAdapterInboundTransactionBehavior to control the isolation level and the default value is **ReadCommitted**.</span></span>  
  
13. <span data-ttu-id="5ec30-118">右側のペインで、 **Wcf-custom トランスポートのプロパティ**、適切な値を指定、 **transactionIsolationLevel**と**transactionTimeout**パラメーター。</span><span class="sxs-lookup"><span data-stu-id="5ec30-118">In the right pane of the **WCF-Custom Transport Properties**, specify appropriate values for the **transactionIsolationLevel** and **transactionTimeout** parameters.</span></span> <span data-ttu-id="5ec30-119">次のトランザクション分離レベルのいずれかを選択することができます: **Serializable**、 **RepeatableRead**、 **ReadCommitted**、 **ReadUncommitted**、**スナップショット**、 **Chaos**、および**未指定**です。</span><span class="sxs-lookup"><span data-stu-id="5ec30-119">You can select any of the following transaction isolation levels: **Serializable**, **RepeatableRead**, **ReadCommitted**, **ReadUncommitted**, **Snapshot**, **Chaos**, and **Unspecified**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5ec30-120">トランザクション分離レベルの既定値は**Serializable** WCF-SQL アダプターの受信と送信の両方の操作をします。</span><span class="sxs-lookup"><span data-stu-id="5ec30-120">The default value of Transaction Isolation Level is **Serializable** for the WCF-SQL adapter for both inbound and outbound operations.</span></span> <span data-ttu-id="5ec30-121">これらのトランザクション分離レベルについては、次を参照してください。、**メンバー**セクションで[分離レベルの列挙体](http://go.microsoft.com/fwlink/?LinkId=126983)(http://go.microsoft.com/fwlink/?LinkId=126983)。</span><span class="sxs-lookup"><span data-stu-id="5ec30-121">For information about these transaction isolation levels, see the **Members** section at [Isolation Level Enumeration](http://go.microsoft.com/fwlink/?LinkId=126983) (http://go.microsoft.com/fwlink/?LinkId=126983).</span></span>  
  
     <span data-ttu-id="5ec30-122">![トランザクション分離レベルに設定する](../../adapters-and-accelerators/adapter-sql/media/b39c180e-ca9f-48ca-9550-f4837826d00e.gif "b39c180e-ca9f-48ca-9550-f4837826d00e")</span><span class="sxs-lookup"><span data-stu-id="5ec30-122">![Setting Transaction Isolation Level](../../adapters-and-accelerators/adapter-sql/media/b39c180e-ca9f-48ca-9550-f4837826d00e.gif "b39c180e-ca9f-48ca-9550-f4837826d00e")</span></span>  
  
14. <span data-ttu-id="5ec30-123">をクリックして**OK**で、 **Wcf-custom トランスポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="5ec30-123">Click **OK** in the **WCF-Custom Transport Properties** dialog box.</span></span>  
  
15. <span data-ttu-id="5ec30-124">をクリックして**OK**変更を保存する開いているダイアログ ボックスでします。</span><span class="sxs-lookup"><span data-stu-id="5ec30-124">Click **OK** in the open dialog boxes to save the changes.</span></span>