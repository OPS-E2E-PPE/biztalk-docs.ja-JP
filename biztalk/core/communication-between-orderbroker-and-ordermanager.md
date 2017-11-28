---
title: "OrderBroker と OrderManager 間の通信 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, publishing [MessageBox database]
- MessageBox database, publishing
ms.assetid: 1b77dcd2-f7a5-4013-b9a2-c06ace161792
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f438b0dfe744aae5867943f4b1493bb163994f4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="communication-between-orderbroker-and-ordermanager"></a><span data-ttu-id="4651d-102">OrderBroker と OrderManager 間の通信</span><span class="sxs-lookup"><span data-stu-id="4651d-102">Communication between OrderBroker and OrderManager</span></span>
<span data-ttu-id="4651d-103">注文ブローカと注文マネージャーのオーケストレーション (**OrderBroker**、 **OrderManager**)、メッセージ ボックス データベースはなくのパートナーの直接バインド経由で通信します。</span><span class="sxs-lookup"><span data-stu-id="4651d-103">The order broker and the order manager orchestrations (**OrderBroker**, **OrderManager**) communicate through the MessageBox database rather than being direct partner bound.</span></span> <span data-ttu-id="4651d-104">これにより、ブローカとマネージャは疎結合して、必要に応じて個別の BizTalk グループおよび地理的に分散した場所に存在できます。</span><span class="sxs-lookup"><span data-stu-id="4651d-104">This ensures that the broker and manager are loosely coupled so that they can, if necessary, be located in separate BizTalk groups and in geographically-separated locations.</span></span> <span data-ttu-id="4651d-105">このようにオーケストレーションを分割するときに必要なのは、管理の構成だけです。コードの変更は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="4651d-105">Separating the orchestrations this way requires only administrative configuration and does not require any code changes.</span></span>  
  
 <span data-ttu-id="4651d-106">現在構成されているソリューションでは、注文ブローカは、特定の注文マネージャのメッセージをマークし、それらのメッセージをメッセージ ボックス データベースに送信します。</span><span class="sxs-lookup"><span data-stu-id="4651d-106">In the solution as presently configured, the order broker marks messages for a particular order manager and sends them to the MessageBox.</span></span> <span data-ttu-id="4651d-107">次に、注文マネージャは、対象のメッセージのフィルタ処理を行い、メッセージ ボックス データベースからそれらのメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="4651d-107">In turn, the order manager filters for messages intended for it and takes those messages from the MessageBox.</span></span> <span data-ttu-id="4651d-108">間接的なこの方法 (直接バインドではなくメッセージ ボックス データベースを通じた通信) により、ブローカとマネージャを個別のグループに簡単に移動できます。</span><span class="sxs-lookup"><span data-stu-id="4651d-108">This indirection—communicating through the MessageBox rather than direct binding—makes it easy to move the broker and manager to separate groups.</span></span>  
  
 <span data-ttu-id="4651d-109">ブローカとマネージャを保存するさまざまなグループが存在する場合または地理的に分散した場所にブローカとマネージャを格納する場合も、この設計によって、簡単に対応できます。</span><span class="sxs-lookup"><span data-stu-id="4651d-109">If there are different groups responsible for maintaining the broker and manager or if they need to be in geographically separate locations, the design makes it easy to accommodate this.</span></span> <span data-ttu-id="4651d-110">必要な作業は、オーケストレーションを異なる BizTalk グループに移動するだけです。</span><span class="sxs-lookup"><span data-stu-id="4651d-110">All you need to do is move the orchestrations to different BizTalk groups.</span></span> <span data-ttu-id="4651d-111">オーケストレーションを個別のグループに格納した後にポートを作成するには、オーケストレーションの再接続だけが必要です。</span><span class="sxs-lookup"><span data-stu-id="4651d-111">After the orchestrations are in separate groups, reconnecting them only requires creating ports.</span></span> <span data-ttu-id="4651d-112">注文ブローカ グループで、注文マネージャと同じフィルタを使用している (メッセージを新しいグループに転送する) 送信ポートを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4651d-112">In the order broker group, you must create a send port that has the same filter as the order manager, but that forwards the message to the new group.</span></span> <span data-ttu-id="4651d-113">注文マネージャ グループで、メッセージを受信してメッセージ ボックス データベースにメッセージを配置する受信ポートを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4651d-113">In the order manager group, you must create a receive port that receives the message and puts it in the MessageBox database.</span></span>  
  
 <span data-ttu-id="4651d-114">アプリケーションをエクスポートして MSI ファイル (ブローカとマネージャに 1 つずつ) を作成することにより、アプリケーションを移動できます。</span><span class="sxs-lookup"><span data-stu-id="4651d-114">You can move the applications by exporting them to create MSI files, one each for the broker and manager.</span></span> <span data-ttu-id="4651d-115">アプリケーションのエクスポートの詳細については、次を参照してください。[を BizTalk アプリケーションをエクスポートする方法](../core/how-to-export-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="4651d-115">For more information about exporting applications, see [How to Export a BizTalk Application](../core/how-to-export-a-biztalk-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4651d-116">参照</span><span class="sxs-lookup"><span data-stu-id="4651d-116">See Also</span></span>  
 [<span data-ttu-id="4651d-117">ビジネス プロセス管理ソリューションの実装の要点</span><span class="sxs-lookup"><span data-stu-id="4651d-117">Implementation Highlights of the Business Process Management Solution</span></span>](../core/implementation-highlights-of-the-business-process-management-solution.md)