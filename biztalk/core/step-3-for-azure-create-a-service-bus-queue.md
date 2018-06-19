---
title: '(Azure) の手順 3: Service Bus キューを作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7192c3c-4ebf-49c4-b8ce-46a6e9fb5f4a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d55b3222798edb245000cdde8de52565c39758a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277338"
---
# <a name="step-3-for-azure-create-a-service-bus-queue"></a><span data-ttu-id="c8397-102">(Azure) の手順 3: Service Bus キューを作成します。</span><span class="sxs-lookup"><span data-stu-id="c8397-102">Step 3 (For Azure): Create a Service Bus Queue</span></span>
<span data-ttu-id="c8397-103">このトピックでは、EDI アグリーメントを使用して X12 販売注文が処理および変換された後に X12 販売注文の送信先になる、Service Bus キューを作成します。</span><span class="sxs-lookup"><span data-stu-id="c8397-103">In this topic, you create a Service Bus Queue to which the X12 sales order is sent after it is processed and transformed using the EDI agreement.</span></span>  
  
### <a name="to-create-a-service-bus-queue"></a><span data-ttu-id="c8397-104">Service Bus キューを作成するには</span><span class="sxs-lookup"><span data-stu-id="c8397-104">To create a Service Bus Queue</span></span>  
  
1.  <span data-ttu-id="c8397-105">ログインに、 [Windows Azure CTP 管理ポータル](http://go.microsoft.com/fwlink/p/?LinkId=202886)Microsoft アカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="c8397-105">Log in to the [Windows Azure CTP Management Portal](http://go.microsoft.com/fwlink/p/?LinkId=202886) using your Microsoft account.</span></span>  
  
2.  <span data-ttu-id="c8397-106">ページの下部左側にある、をクリックして**AppFabric**です。</span><span class="sxs-lookup"><span data-stu-id="c8397-106">On the lower left-hand side of the page, click **AppFabric**.</span></span>  
  
3.  <span data-ttu-id="c8397-107">左側のツリーでサービスを展開し、サブスクリプションを展開して、作成済みの名前空間をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8397-107">Expand Services in the tree on the left-hand side, expand your subscription, and click a namespace that you must have already created.</span></span> <span data-ttu-id="c8397-108">名前空間既にをお持ちでない場合は、次を参照してください。[する方法: を作成または Windows Azure CTP サービスの Namespace を変更](http://msdn.microsoft.com/library/windowsazure/hh697699.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="c8397-108">If you don’t have a namespace already, see [How to: Create or Modify a Windows Azure CTP Service Namespace](http://msdn.microsoft.com/library/windowsazure/hh697699.aspx).</span></span>  
  
4.  <span data-ttu-id="c8397-109">クリックするキューを作成する**新しいキュー**から、**エンティティの管理**ページの上部にあるツールバーからのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="c8397-109">To create a Queue click **New Queue** from the **Manage Entities** category from the toolbar at the top of the page.</span></span>  
  
5.  <span data-ttu-id="c8397-110">**新しいキュー**  ダイアログ ボックスで、キューの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c8397-110">In the **New Queue** dialog box, enter a name for the Queue.</span></span> <span data-ttu-id="c8397-111">このチュートリアルと名前を入力してください。 `queueordersedi`、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="c8397-111">For this tutorial, enter the name as `queueordersedi`, and then click **OK**.</span></span> <span data-ttu-id="c8397-112">作成した EDI アグリーメントの一部としてこの名前を指定する[ステップ 2 (Azure 用): EDI アグリーメントを作成する](../core/step-2-for-azure-create-an-edi-agreement.md)です。</span><span class="sxs-lookup"><span data-stu-id="c8397-112">You specified this name as part of the EDI agreement you created in [Step 2 (For Azure): Create an EDI Agreement](../core/step-2-for-azure-create-an-edi-agreement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8397-113">参照</span><span class="sxs-lookup"><span data-stu-id="c8397-113">See Also</span></span>  
 [<span data-ttu-id="c8397-114">チュートリアル 4: BizTalk Server 2013 を使用するハイブリッド アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="c8397-114">Tutorial 4: Creating a Hybrid Application Using BizTalk Server 2013</span></span>](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)