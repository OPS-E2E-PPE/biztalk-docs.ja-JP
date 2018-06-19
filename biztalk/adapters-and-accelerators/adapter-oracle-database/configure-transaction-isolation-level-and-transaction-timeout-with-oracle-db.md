---
title: Oracle データベースとトランザクション分離レベルとトランザクションのタイムアウトを構成する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4b66e764-2330-441b-89ef-29118f27b366
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13d1beea3be34dbd818a94986fb8cae876bcdd81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214514"
---
# <a name="configure-transaction-isolation-level-and-transaction-timeout-with-oracle-database"></a><span data-ttu-id="ecdaa-102">Oracle データベースとトランザクション分離レベルとトランザクションのタイムアウトを構成します。</span><span class="sxs-lookup"><span data-stu-id="ecdaa-102">Configure transaction isolation level and transaction timeout with Oracle Database</span></span>
<span data-ttu-id="ecdaa-103">使用して受信操作 (ポーリング) を実行中に、[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、トランザクション分離レベルとトランザクションのタイムアウト値を適切に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ecdaa-103">While performing inbound operation (Polling) using the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you should appropriately configure the transaction isolation level and the transaction timeout values.</span></span> <span data-ttu-id="ecdaa-104">これを行うには :</span><span class="sxs-lookup"><span data-stu-id="ecdaa-104">To do this:</span></span>  
  
1.  <span data-ttu-id="ecdaa-105">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="ecdaa-105">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="ecdaa-106">コンソール ツリーで、展開、 **BizTalk グループ**、順に展開**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="ecdaa-106">In the console tree, expand the **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="ecdaa-107">使用してメタデータの生成後に展開した BizTalk アプリケーションを展開し、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ecdaa-107">Expand the BizTalk application that you have deployed after generating the metadata using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
4.  <span data-ttu-id="ecdaa-108">右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="ecdaa-108">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
5.  <span data-ttu-id="ecdaa-109">**受信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、受信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="ecdaa-109">In the **Receive Port Properties** dialog box, on the **General** tab, type a name for the receive port.</span></span>  
  
6.  <span data-ttu-id="ecdaa-110">左側のウィンドウで、**受信ポートのプロパティ**ダイアログ ボックスで、をクリックして**受信場所**、順にクリック**新規**受信場所を新しい定義の右側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="ecdaa-110">In the left pane of the **Receive Port Properties** dialog box, click **Receive Locations**, and then click **New** in the right pane to define a new receive location.</span></span>  
  
7.  <span data-ttu-id="ecdaa-111">**受信場所のプロパティ**ダイアログ ボックスで、をクリックして**Wcf-custom**で、**型** ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="ecdaa-111">In the **Receive Location Properties** dialog box, click **WCF-Custom** in the **Type** list.</span></span>  
  
8.  <span data-ttu-id="ecdaa-112">をクリックして**構成**の横にある、**型** ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="ecdaa-112">Click **Configure** adjacent to the **Type** list.</span></span>  
  
9. <span data-ttu-id="ecdaa-113">**Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**動作**タブです。</span><span class="sxs-lookup"><span data-stu-id="ecdaa-113">In the **WCF-Custom Transport Properties** dialog box, click the **Behavior** tab.</span></span>  
  
10. <span data-ttu-id="ecdaa-114">**動作**ボックスの一覧を右クリックして**ServiceBehavior**、 をクリック**拡張機能を追加**です。</span><span class="sxs-lookup"><span data-stu-id="ecdaa-114">In the **Behavior** list, right-click **ServiceBehavior**, and click **Add extension**.</span></span>  
  
11. <span data-ttu-id="ecdaa-115">**動作拡張機能の選択**ダイアログ ボックスで、 **oracleDBAdapterInboundTransactionBehavior**、 をクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="ecdaa-115">In the **Select Behavior Extension** dialog box, select **oracleDBAdapterInboundTransactionBehavior**, and click **OK**.</span></span>  
  
12. <span data-ttu-id="ecdaa-116">左側のウィンドウで、 **Wcf-custom トランスポートのプロパティ**、select、 **oracleDBAdapterInboundTransactionBehavior**下にあるサービス**ServiceBehavior**です。</span><span class="sxs-lookup"><span data-stu-id="ecdaa-116">In the left pane of the **WCF-Custom Transport Properties**, select the **oracleDBAdapterInboundTransactionBehavior** service under **ServiceBehavior**.</span></span>  
  
13. <span data-ttu-id="ecdaa-117">右側のペインで、 **Wcf-custom トランスポートのプロパティ**、適切な値を指定、 **transactionIsolationLevel**と**transactionTimeout**パラメーター。</span><span class="sxs-lookup"><span data-stu-id="ecdaa-117">In the right pane of the **WCF-Custom Transport Properties**, specify appropriate values for the **transactionIsolationLevel** and **transactionTimeout** parameters.</span></span> <span data-ttu-id="ecdaa-118">次のトランザクション分離レベルのいずれかを選択することができます: **Serializable**、 **RepeatableRead**、 **ReadCommitted**、 **ReadUncommitted**、**スナップショット**、 **Chaos**、および**未指定**です。</span><span class="sxs-lookup"><span data-stu-id="ecdaa-118">You can select any of the following transaction isolation levels: **Serializable**, **RepeatableRead**, **ReadCommitted**, **ReadUncommitted**, **Snapshot**, **Chaos**, and **Unspecified**.</span></span> <span data-ttu-id="ecdaa-119">これらのトランザクション分離レベルについては、次を参照してください。、**メンバー**セクションで[http://go.microsoft.com/fwlink/?LinkId=126983](http://go.microsoft.com/fwlink/?LinkId=126983)です。</span><span class="sxs-lookup"><span data-stu-id="ecdaa-119">For information about these transaction isolation levels, see the **Members** section at [http://go.microsoft.com/fwlink/?LinkId=126983](http://go.microsoft.com/fwlink/?LinkId=126983).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="ecdaa-120">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]次の 2 つのトランザクション分離レベルのみをサポートしています: ReadCommitted および Serializable です。</span><span class="sxs-lookup"><span data-stu-id="ecdaa-120">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports only the following two transaction isolation levels: ReadCommitted and Serializable.</span></span>  
  
     <span data-ttu-id="ecdaa-121">![トランザクション分離レベルに設定する](../../adapters-and-accelerators/adapter-oracle-database/media/96a66f86-0321-4aa6-9e72-ada30d7de064.gif "96a66f86-0321-4aa6-9e72-ada30d7de064")</span><span class="sxs-lookup"><span data-stu-id="ecdaa-121">![Setting Transaction Isolation Level](../../adapters-and-accelerators/adapter-oracle-database/media/96a66f86-0321-4aa6-9e72-ada30d7de064.gif "96a66f86-0321-4aa6-9e72-ada30d7de064")</span></span>  
  
14. <span data-ttu-id="ecdaa-122">をクリックして**OK**で、 **Wcf-custom トランスポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="ecdaa-122">Click **OK** in the **WCF-Custom Transport Properties** dialog box.</span></span>  
  
15. <span data-ttu-id="ecdaa-123">をクリックして**OK**変更を保存する開いているダイアログ ボックスでします。</span><span class="sxs-lookup"><span data-stu-id="ecdaa-123">Click **OK** in the open dialog boxes to save the changes.</span></span>