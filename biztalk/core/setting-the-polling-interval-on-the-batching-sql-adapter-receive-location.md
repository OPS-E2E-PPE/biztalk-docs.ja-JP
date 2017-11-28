---
title: "バッチ処理 SQL アダプターのポーリング間隔の設定の受信場所 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- polling interval [receive adapters]
- SQL adapters, polling interval
- receive locations, polling interval
- SQL adapters, receive locations
- receive locations, SQL adapters
ms.assetid: 9053b20d-145a-4445-b414-c0482cf975a0
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 830cafc89c87ce84048bad8f6e4e9f2feb34f565
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="setting-the-polling-interval-on-the-batching-sql-adapter-receive-location"></a><span data-ttu-id="31056-102">バッチ処理 SQL アダプター受信場所のポーリング間隔の設定</span><span class="sxs-lookup"><span data-stu-id="31056-102">Setting the Polling Interval on the Batching SQL Adapter Receive Location</span></span>
<span data-ttu-id="31056-103">設定できます、ポーリング間隔でバッチ処理 SQL アダプター受信場所 (**BatchControlMessageRecvLoc**) の開発と実稼働のコンピューターでそれぞれ異なる。</span><span class="sxs-lookup"><span data-stu-id="31056-103">You can set the polling interval on the batching SQL adapter receive location (**BatchControlMessageRecvLoc**) differently on development and production computers.</span></span> <span data-ttu-id="31056-104">開発サーバーでは、ポーリング間隔は 30 秒の既定値のままにして、アグリーメントのバッチ処理オーケストレーションをすばやくアクティブ化できるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="31056-104">On a development server, Microsoft recommends that you keep the polling interval at the default of 30 seconds, for quick activation of the batching orchestration for an agreement.</span></span> <span data-ttu-id="31056-105">ただし実稼働サーバーでは、30 秒に設定するとパフォーマンスに影響する場合があります。</span><span class="sxs-lookup"><span data-stu-id="31056-105">However, on a production server, a setting of 30 seconds may affect performance.</span></span> <span data-ttu-id="31056-106">バッチをアクティブ化した後、ポーリング間隔を 5 分などの高い値に設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="31056-106">Once you have activated a batch, you may want to set the polling interval to a higher value, such as five minutes.</span></span>  
  
 <span data-ttu-id="31056-107">パーティの詳細については、次を参照してください。[を管理するパーティ](../core/managing-parties.md)です。</span><span class="sxs-lookup"><span data-stu-id="31056-107">For more information about parties, see [Managing Parties](../core/managing-parties.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="31056-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="31056-108">Prerequisites</span></span>  
 <span data-ttu-id="31056-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="31056-109">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-set-the-polling-interval-on-the-batching-sql-adapter-receive-location"></a><span data-ttu-id="31056-110">バッチ処理 SQL アダプタ受信場所のポーリング間隔を設定するには</span><span class="sxs-lookup"><span data-stu-id="31056-110">To set the Polling Interval on the Batching SQL Adapter Receive Location</span></span>  
  
1.  <span data-ttu-id="31056-111">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして**BizTalk EDI アプリケーション**、クリックして**受信場所**です。</span><span class="sxs-lookup"><span data-stu-id="31056-111">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click **BizTalk EDI Application**, and then click **Receive Locations**.</span></span> <span data-ttu-id="31056-112">右クリック**BatchControlMessageRecvLoc**、 をクリック**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="31056-112">Right-click **BatchControlMessageRecvLoc**, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="31056-113">**受信場所のプロパティ**] ダイアログ ボックスで、**トランスポート**セクションで、[**構成**です。</span><span class="sxs-lookup"><span data-stu-id="31056-113">In the **Receive Location Properties** dialog box, in the **Transport** section, click **Configure**.</span></span>  
  
3.  <span data-ttu-id="31056-114">**SQL トランスポートのプロパティ** ダイアログ ボックスの値を変更**のポーリング間隔**目的の値を「30」の既定値からです。</span><span class="sxs-lookup"><span data-stu-id="31056-114">In the **SQL Transport Properties** dialog box, change the value for **Polling Interval** from the default value of "30" to the desired value.</span></span> <span data-ttu-id="31056-115">実稼働サーバーの推奨値は "5" です。</span><span class="sxs-lookup"><span data-stu-id="31056-115">The recommended value for a production server is "5".</span></span>  
  
4.  <span data-ttu-id="31056-116">値を変更**ポーリング単位**の既定値から**秒**に**分**です。</span><span class="sxs-lookup"><span data-stu-id="31056-116">Change the value of **Polling Unit of Measure** from the default value of **Seconds** to **Minutes**.</span></span>  
  
5.  <span data-ttu-id="31056-117">をクリックして**[ok]**、順にクリック**OK**再度</span><span class="sxs-lookup"><span data-stu-id="31056-117">Click **OK**, and then click **OK** again</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31056-118">参照</span><span class="sxs-lookup"><span data-stu-id="31056-118">See Also</span></span>  
 [<span data-ttu-id="31056-119">EDI および AS2 ソリューションの管理</span><span class="sxs-lookup"><span data-stu-id="31056-119">Managing EDI and AS2 Solutions</span></span>](../core/managing-edi-and-as2-solutions.md)