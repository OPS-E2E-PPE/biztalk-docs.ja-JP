---
title: Oracle データベースとトランザクション分離レベルとトランザクションのタイムアウトの構成 |Microsoft Docs
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
ms.openlocfilehash: b7b0969feb6d22ea05e054c17ad4f584009e1b19
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529472"
---
# <a name="configure-transaction-isolation-level-and-transaction-timeout-with-oracle-database"></a><span data-ttu-id="8eb55-102">Oracle データベースとトランザクション分離レベルとトランザクションのタイムアウトを構成します。</span><span class="sxs-lookup"><span data-stu-id="8eb55-102">Configure transaction isolation level and transaction timeout with Oracle Database</span></span>
<span data-ttu-id="8eb55-103">使用して受信操作 (ポーリング) を実行中に、[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、トランザクション分離レベルとトランザクションのタイムアウト値を適切に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8eb55-103">While performing inbound operation (Polling) using the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you should appropriately configure the transaction isolation level and the transaction timeout values.</span></span> <span data-ttu-id="8eb55-104">これを行うには :</span><span class="sxs-lookup"><span data-stu-id="8eb55-104">To do this:</span></span>  

1. <span data-ttu-id="8eb55-105">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="8eb55-105">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="8eb55-106">コンソール ツリーで、展開、 **BizTalk グループ**、順に展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="8eb55-106">In the console tree, expand the **BizTalk Group**, and then expand **Applications**.</span></span>  

3. <span data-ttu-id="8eb55-107">使用してメタデータを生成した後で展開されている BizTalk アプリケーションを展開し、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="8eb55-107">Expand the BizTalk application that you have deployed after generating the metadata using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  

4. <span data-ttu-id="8eb55-108">右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="8eb55-108">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  

5. <span data-ttu-id="8eb55-109">**受信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、受信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="8eb55-109">In the **Receive Port Properties** dialog box, on the **General** tab, type a name for the receive port.</span></span>  

6. <span data-ttu-id="8eb55-110">左側のウィンドウで、**受信ポートのプロパティ**ダイアログ ボックスで、をクリックして**受信場所**、順にクリックします**新規**右側のウィンドウで、新しい定義には、受信場所。</span><span class="sxs-lookup"><span data-stu-id="8eb55-110">In the left pane of the **Receive Port Properties** dialog box, click **Receive Locations**, and then click **New** in the right pane to define a new receive location.</span></span>  

7. <span data-ttu-id="8eb55-111">**受信場所のプロパティ**ダイアログ ボックスで、をクリックして**Wcf-custom**で、**型**一覧。</span><span class="sxs-lookup"><span data-stu-id="8eb55-111">In the **Receive Location Properties** dialog box, click **WCF-Custom** in the **Type** list.</span></span>  

8. <span data-ttu-id="8eb55-112">クリックして**構成**の横にある、**型**一覧。</span><span class="sxs-lookup"><span data-stu-id="8eb55-112">Click **Configure** adjacent to the **Type** list.</span></span>  

9. <span data-ttu-id="8eb55-113">**Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**動作**タブ。</span><span class="sxs-lookup"><span data-stu-id="8eb55-113">In the **WCF-Custom Transport Properties** dialog box, click the **Behavior** tab.</span></span>  

10. <span data-ttu-id="8eb55-114">**動作**一覧で、右クリックして**ServiceBehavior**、 をクリック**拡張機能の追加**します。</span><span class="sxs-lookup"><span data-stu-id="8eb55-114">In the **Behavior** list, right-click **ServiceBehavior**, and click **Add extension**.</span></span>  

11. <span data-ttu-id="8eb55-115">**動作拡張機能の選択**ダイアログ ボックスで、 **oracleDBAdapterInboundTransactionBehavior**、 をクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="8eb55-115">In the **Select Behavior Extension** dialog box, select **oracleDBAdapterInboundTransactionBehavior**, and click **OK**.</span></span>  

12. <span data-ttu-id="8eb55-116">左側のウィンドウで、 **Wcf-custom トランスポートのプロパティ**を選択、 **oracleDBAdapterInboundTransactionBehavior**サービス**ServiceBehavior**します。</span><span class="sxs-lookup"><span data-stu-id="8eb55-116">In the left pane of the **WCF-Custom Transport Properties**, select the **oracleDBAdapterInboundTransactionBehavior** service under **ServiceBehavior**.</span></span>  

13. <span data-ttu-id="8eb55-117">右側のウィンドウで、 **Wcf-custom トランスポートのプロパティ**、適切な値を指定、 **transactionIsolationLevel**と**transactionTimeout**パラメーター。</span><span class="sxs-lookup"><span data-stu-id="8eb55-117">In the right pane of the **WCF-Custom Transport Properties**, specify appropriate values for the **transactionIsolationLevel** and **transactionTimeout** parameters.</span></span> <span data-ttu-id="8eb55-118">次のトランザクション分離レベルのいずれかを選択できます。**シリアル化可能な**、 **RepeatableRead**、 **ReadCommitted**、 **ReadUncommitted**、**スナップショット**、 **Chaos**、および**未指定**します。</span><span class="sxs-lookup"><span data-stu-id="8eb55-118">You can select any of the following transaction isolation levels: **Serializable**, **RepeatableRead**, **ReadCommitted**, **ReadUncommitted**, **Snapshot**, **Chaos**, and **Unspecified**.</span></span> <span data-ttu-id="8eb55-119">これらのトランザクション分離レベルについては、次を参照してください。、**メンバー**セクションで[ http://go.microsoft.com/fwlink/?LinkId=126983](http://go.microsoft.com/fwlink/?LinkId=126983)します。</span><span class="sxs-lookup"><span data-stu-id="8eb55-119">For information about these transaction isolation levels, see the **Members** section at [http://go.microsoft.com/fwlink/?LinkId=126983](http://go.microsoft.com/fwlink/?LinkId=126983).</span></span>  

    > [!IMPORTANT]
    >  <span data-ttu-id="8eb55-120">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]次の 2 つのトランザクション分離レベルのみをサポートしています。ReadCommitted とシリアル化可能な。</span><span class="sxs-lookup"><span data-stu-id="8eb55-120">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports only the following two transaction isolation levels: ReadCommitted and Serializable.</span></span>  

     <span data-ttu-id="8eb55-121">![トランザクション分離レベルの設定](../../adapters-and-accelerators/adapter-oracle-database/media/96a66f86-0321-4aa6-9e72-ada30d7de064.gif "96a66f86-0321-4aa6-9e72-ada30d7de064")</span><span class="sxs-lookup"><span data-stu-id="8eb55-121">![Setting Transaction Isolation Level](../../adapters-and-accelerators/adapter-oracle-database/media/96a66f86-0321-4aa6-9e72-ada30d7de064.gif "96a66f86-0321-4aa6-9e72-ada30d7de064")</span></span>  

14. <span data-ttu-id="8eb55-122">クリックして**OK**で、 **Wcf-custom トランスポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="8eb55-122">Click **OK** in the **WCF-Custom Transport Properties** dialog box.</span></span>  

15. <span data-ttu-id="8eb55-123">をクリックして**OK**変更を保存する [開く] ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="8eb55-123">Click **OK** in the open dialog boxes to save the changes.</span></span>
