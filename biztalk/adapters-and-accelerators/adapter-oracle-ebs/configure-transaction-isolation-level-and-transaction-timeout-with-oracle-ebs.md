---
title: Oracle E-business Suite でのトランザクション分離レベルとトランザクションのタイムアウトの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db3d64ad-037d-486a-bdde-45c8199613f1
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8bbff645105feb4732afdf86aa3a591252c0d88c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969219"
---
# <a name="configure-transaction-isolation-level-and-transaction-timeout-with-oracle-e-business-suite"></a><span data-ttu-id="eadba-102">Oracle E-business Suite でのトランザクション分離レベルとトランザクションのタイムアウトを構成します。</span><span class="sxs-lookup"><span data-stu-id="eadba-102">Configure transaction isolation level and transaction timeout with Oracle E-Business Suite</span></span>
<span data-ttu-id="eadba-103">(ポーリングと通知) の受信操作の実行中を使用して、[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、トランザクション分離レベルとトランザクションのタイムアウト値を適切に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eadba-103">While performing inbound operations (Polling and Notification) using the [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you should appropriately configure the transaction isolation level and the transaction timeout values.</span></span> <span data-ttu-id="eadba-104">これを行うには :</span><span class="sxs-lookup"><span data-stu-id="eadba-104">To do this:</span></span>  

1. <span data-ttu-id="eadba-105">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="eadba-105">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="eadba-106">コンソール ツリーで、展開、 **BizTalk グループ**、順に展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="eadba-106">In the console tree, expand the **BizTalk Group**, and then expand **Applications**.</span></span>  

3. <span data-ttu-id="eadba-107">使用してメタデータを生成した後で展開されている BizTalk アプリケーションを展開し、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="eadba-107">Expand the BizTalk application that you have deployed after generating the metadata using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  

4. <span data-ttu-id="eadba-108">右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="eadba-108">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  

5. <span data-ttu-id="eadba-109">**受信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、受信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="eadba-109">In the **Receive Port Properties** dialog box, on the **General** tab, type a name for the receive port.</span></span>  

6. <span data-ttu-id="eadba-110">左側のウィンドウで、**受信ポートのプロパティ**ダイアログ ボックスで、をクリックして**受信場所**、順にクリックします**新規**右側のウィンドウで、新しい定義には、受信場所。</span><span class="sxs-lookup"><span data-stu-id="eadba-110">In the left pane of the **Receive Port Properties** dialog box, click **Receive Locations**, and then click **New** in the right pane to define a new receive location.</span></span>  

7. <span data-ttu-id="eadba-111">**受信場所のプロパティ**ダイアログ ボックスで、をクリックして**Wcf-custom**で、**型**一覧。</span><span class="sxs-lookup"><span data-stu-id="eadba-111">In the **Receive Location Properties** dialog box, click **WCF-Custom** in the **Type** list.</span></span>  

8. <span data-ttu-id="eadba-112">クリックして**構成**の横にある、**型**一覧。</span><span class="sxs-lookup"><span data-stu-id="eadba-112">Click **Configure** adjacent to the **Type** list.</span></span>  

9. <span data-ttu-id="eadba-113">**Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**動作**タブ。</span><span class="sxs-lookup"><span data-stu-id="eadba-113">In the **WCF-Custom Transport Properties** dialog box, click the **Behavior** tab.</span></span>  

10. <span data-ttu-id="eadba-114">**動作**一覧で、右クリックして**ServiceBehavior**、 をクリック**拡張機能の追加**します。</span><span class="sxs-lookup"><span data-stu-id="eadba-114">In the **Behavior** list, right-click **ServiceBehavior**, and click **Add extension**.</span></span>  

11. <span data-ttu-id="eadba-115">**動作拡張機能の選択**ダイアログ ボックスで、 **oracleEBSAdapterInboundTransactionBehavior**、 をクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="eadba-115">In the **Select Behavior Extension** dialog box, select **oracleEBSAdapterInboundTransactionBehavior**, and click **OK**.</span></span>  

12. <span data-ttu-id="eadba-116">左側のウィンドウで、 **Wcf-custom トランスポートのプロパティ**を選択、 **oracleEBSAdapterInboundTransactionBehavior**サービス**ServiceBehavior**します。</span><span class="sxs-lookup"><span data-stu-id="eadba-116">In the left pane of the **WCF-Custom Transport Properties**, select the **oracleEBSAdapterInboundTransactionBehavior** service under **ServiceBehavior**.</span></span>  

13. <span data-ttu-id="eadba-117">右側のウィンドウで、 **Wcf-custom トランスポートのプロパティ**、適切な値を指定、 **transactionIsolationLevel**と**transactionTimeout**パラメーター。</span><span class="sxs-lookup"><span data-stu-id="eadba-117">In the right pane of the **WCF-Custom Transport Properties**, specify appropriate values for the **transactionIsolationLevel** and **transactionTimeout** parameters.</span></span> <span data-ttu-id="eadba-118">次のトランザクション分離レベルのいずれかを選択することができます: **Serializable**、 **RepeatableRead**、 **ReadCommitted**、 **ReadUncommitted**、**スナップショット**、**混乱**、および**未指定**します。</span><span class="sxs-lookup"><span data-stu-id="eadba-118">You can select any of the following transaction isolation levels: **Serializable**, **RepeatableRead**, **ReadCommitted**, **ReadUncommitted**, **Snapshot**, **Chaos**, and **Unspecified**.</span></span> <span data-ttu-id="eadba-119">これらのトランザクション分離レベルについては、次を参照してください。、**メンバー**セクションで[ http://go.microsoft.com/fwlink/?LinkId=126983](http://go.microsoft.com/fwlink/?LinkId=126983)します。</span><span class="sxs-lookup"><span data-stu-id="eadba-119">For information about these transaction isolation levels, see the **Members** section at [http://go.microsoft.com/fwlink/?LinkId=126983](http://go.microsoft.com/fwlink/?LinkId=126983).</span></span>  

    > [!IMPORTANT]
    >  <span data-ttu-id="eadba-120">Oracle E-business Suite は、次の 2 つのトランザクション分離レベルのみをサポートしています。 ReadCommitted および Serializable。</span><span class="sxs-lookup"><span data-stu-id="eadba-120">Oracle E-Business Suite supports only the following two transaction isolation levels: ReadCommitted and Serializable.</span></span>  

     <span data-ttu-id="eadba-121">![トランザクション分離レベルの設定](../../adapters-and-accelerators/adapter-oracle-ebs/media/2bafbb9d-4daa-43c0-abcb-35220e6a3cb5.gif "2bafbb9d-4daa-43c0-abcb-35220e6a3cb5")</span><span class="sxs-lookup"><span data-stu-id="eadba-121">![Setting Transaction Isolation Level](../../adapters-and-accelerators/adapter-oracle-ebs/media/2bafbb9d-4daa-43c0-abcb-35220e6a3cb5.gif "2bafbb9d-4daa-43c0-abcb-35220e6a3cb5")</span></span>  

14. <span data-ttu-id="eadba-122">クリックして**OK**で、 **Wcf-custom トランスポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="eadba-122">Click **OK** in the **WCF-Custom Transport Properties** dialog box.</span></span>  

15. <span data-ttu-id="eadba-123">をクリックして**OK**変更を保存する [開く] ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="eadba-123">Click **OK** in the open dialog boxes to save the changes.</span></span>
