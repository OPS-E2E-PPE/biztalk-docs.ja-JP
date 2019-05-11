---
title: OrderBroker と OrderManager 間の通信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, publishing [MessageBox database]
- MessageBox database, publishing
ms.assetid: 1b77dcd2-f7a5-4013-b9a2-c06ace161792
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43af6f47a53f28875b77b5089ffe2d343681f140
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357110"
---
# <a name="communication-between-orderbroker-and-ordermanager"></a><span data-ttu-id="6b16a-102">OrderBroker と OrderManager 間の通信</span><span class="sxs-lookup"><span data-stu-id="6b16a-102">Communication between OrderBroker and OrderManager</span></span>
<span data-ttu-id="6b16a-103">注文ブローカと注文マネージャーのオーケストレーション (**OrderBroker**、 **OrderManager**)、メッセージ ボックスされているのではなく、データベースのパートナーの直接バインド経由で通信します。</span><span class="sxs-lookup"><span data-stu-id="6b16a-103">The order broker and the order manager orchestrations (**OrderBroker**, **OrderManager**) communicate through the MessageBox database rather than being direct partner bound.</span></span> <span data-ttu-id="6b16a-104">これにより、ブローカとマネージャは疎結合できるようにする、必要に応じて、別の BizTalk グループおよび地理的に離れた場所に配置されています。</span><span class="sxs-lookup"><span data-stu-id="6b16a-104">This ensures that the broker and manager are loosely coupled so that they can, if necessary, be located in separate BizTalk groups and in geographically-separated locations.</span></span> <span data-ttu-id="6b16a-105">このように、オーケストレーションを分離することにより、管理の構成だけを必要とし、コード変更の必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6b16a-105">Separating the orchestrations this way requires only administrative configuration and does not require any code changes.</span></span>  
  
 <span data-ttu-id="6b16a-106">として現在構成されているソリューションでは、注文ブローカは、特定の順序のマネージャーのメッセージをマークし、メッセージ ボックス データベースに送信します。</span><span class="sxs-lookup"><span data-stu-id="6b16a-106">In the solution as presently configured, the order broker marks messages for a particular order manager and sends them to the MessageBox.</span></span> <span data-ttu-id="6b16a-107">さらに、注文マネージャは、対象のメッセージのフィルターをし、それらのメッセージでは、メッセージ ボックス データベースから取得します。</span><span class="sxs-lookup"><span data-stu-id="6b16a-107">In turn, the order manager filters for messages intended for it and takes those messages from the MessageBox.</span></span> <span data-ttu-id="6b16a-108">この間接参照-直接バインドするのではなく、メッセージ ボックスを経由して通信-ブローカとマネージャを個別のグループの移動が容易になります。</span><span class="sxs-lookup"><span data-stu-id="6b16a-108">This indirection—communicating through the MessageBox rather than direct binding—makes it easy to move the broker and manager to separate groups.</span></span>  
  
 <span data-ttu-id="6b16a-109">別のグループがある、ブローカとマネージャの保守を担当している場合、または地理的に離れた場所に置く必要がある場合は、デザイン簡単に対応します。</span><span class="sxs-lookup"><span data-stu-id="6b16a-109">If there are different groups responsible for maintaining the broker and manager or if they need to be in geographically separate locations, the design makes it easy to accommodate this.</span></span> <span data-ttu-id="6b16a-110">行う必要があるすべては、オーケストレーションを別の BizTalk グループに移動します。</span><span class="sxs-lookup"><span data-stu-id="6b16a-110">All you need to do is move the orchestrations to different BizTalk groups.</span></span> <span data-ttu-id="6b16a-111">オーケストレーションは、別のグループが、再接続は、ポートを作成する必要をのみです。</span><span class="sxs-lookup"><span data-stu-id="6b16a-111">After the orchestrations are in separate groups, reconnecting them only requires creating ports.</span></span> <span data-ttu-id="6b16a-112">注文ブローカ グループで、注文マネージャと同じフィルターを持つが、新しいグループにメッセージを転送する送信ポートを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b16a-112">In the order broker group, you must create a send port that has the same filter as the order manager, but that forwards the message to the new group.</span></span> <span data-ttu-id="6b16a-113">注文マネージャ グループでは、メッセージを受信し、メッセージ ボックス データベース内に配置される受信ポートを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b16a-113">In the order manager group, you must create a receive port that receives the message and puts it in the MessageBox database.</span></span>  
  
 <span data-ttu-id="6b16a-114">エクスポートする、ブローカとマネージャに対して 1 つずつ MSI ファイルを作成することによって、アプリケーションを移動できます。</span><span class="sxs-lookup"><span data-stu-id="6b16a-114">You can move the applications by exporting them to create MSI files, one each for the broker and manager.</span></span> <span data-ttu-id="6b16a-115">アプリケーションのエクスポートの詳細については、次を参照してください。 [BizTalk アプリケーションのエクスポート方法](../core/how-to-export-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="6b16a-115">For more information about exporting applications, see [How to Export a BizTalk Application](../core/how-to-export-a-biztalk-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b16a-116">参照</span><span class="sxs-lookup"><span data-stu-id="6b16a-116">See Also</span></span>  
 [<span data-ttu-id="6b16a-117">ビジネス プロセス管理ソリューションの実装の重要なポイント</span><span class="sxs-lookup"><span data-stu-id="6b16a-117">Implementation Highlights of the Business Process Management Solution</span></span>](../core/implementation-highlights-of-the-business-process-management-solution.md)