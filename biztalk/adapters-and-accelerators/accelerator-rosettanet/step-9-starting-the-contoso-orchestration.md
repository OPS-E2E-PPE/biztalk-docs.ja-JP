---
title: '手順 9: Contoso オーケストレーションの開始 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, starting orchestrations
ms.assetid: df3ff90b-5a9f-4ae7-819a-11cb36d64ccd
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d58d7f2f9d725fca94eb6cf3d2412b3c376fe015
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209450"
---
# <a name="step-9-starting-the-contoso-orchestration"></a><span data-ttu-id="3b797-102">手順 9: Contoso オーケストレーションの開始</span><span class="sxs-lookup"><span data-stu-id="3b797-102">Step 9: Starting the Contoso Orchestration</span></span>
<span data-ttu-id="3b797-103">ここでは、物理的な送信元と送信先の場所を定義して、ポートの構成プロセスを実行します。</span><span class="sxs-lookup"><span data-stu-id="3b797-103">In this step, you complete the port configuration process by defining the physical source and destination locations.</span></span> <span data-ttu-id="3b797-104">作成した論理ポートを物理ポートをバインドする[手順 7: ポートの作成と構成](../../adapters-and-accelerators/accelerator-rosettanet/step-7-creating-and-configuring-ports.md)です。</span><span class="sxs-lookup"><span data-stu-id="3b797-104">You bind the physical ports to the logical ports you created in [Step 7: Creating and Configuring Ports](../../adapters-and-accelerators/accelerator-rosettanet/step-7-creating-and-configuring-ports.md).</span></span> <span data-ttu-id="3b797-105">オーケストレーションで実行される物理環境と、オーケストレーションで設計したビジネス プロセスを関連付けるには、サービスを参加させます。</span><span class="sxs-lookup"><span data-stu-id="3b797-105">You then enlist the service to associate the business process that you designed in the orchestration with the physical environment that the orchestration will run in.</span></span> <span data-ttu-id="3b797-106">最後に、Fabrikam とのビジネス トランザクションに参加できるように、オーケストレーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="3b797-106">Finally, you start the orchestration so that it can participate in business transactions with Fabrikam.</span></span>  
  
### <a name="to-bind-the-orchestration-ports"></a><span data-ttu-id="3b797-107">オーケストレーション ポートをバインドするには</span><span class="sxs-lookup"><span data-stu-id="3b797-107">To bind the orchestration ports</span></span>  
  
1.  <span data-ttu-id="3b797-108">開いている**BizTalk エクスプ ローラー**です。</span><span class="sxs-lookup"><span data-stu-id="3b797-108">Open **BizTalk Explorer**.</span></span>  
  
2.  <span data-ttu-id="3b797-109">BizTalk エクスプ ローラーで、 **BizTalk 構成データベース**、展開**オーケストレーション**を右クリックして **[contosopriceandavailability.privateresponderprocess]**、クリックして**バインド**です。</span><span class="sxs-lookup"><span data-stu-id="3b797-109">In BizTalk Explorer, expand **BizTalk Configuration Database**, expand **Orchestrations**, right-click **ContosoPriceAndAvailability.PrivateResponderProcess**, and then click **Bind**.</span></span>  
  
3.  <span data-ttu-id="3b797-110">[ポートのバインドのプロパティ] ページで、 **LOB_To_PrivateResponder**で、 **FromLOB**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="3b797-110">On the Port Bindings Properties page, select **LOB_To_PrivateResponder** in the **FromLOB** property.</span></span>  
  
4.  <span data-ttu-id="3b797-111">**ContosoSQLReqResponsePort**ボックスで、 **3 a2sqlreqresponsesendport**です。</span><span class="sxs-lookup"><span data-stu-id="3b797-111">In the **ContosoSQLReqResponsePort** box, select **3A2SQLReqResponseSendPort**.</span></span>  
  
5.  <span data-ttu-id="3b797-112">**ToLOB**プロパティ、展開**送信ポート**選択**PrivateResponder_To_LOB**です。</span><span class="sxs-lookup"><span data-stu-id="3b797-112">In the **ToLOB** property, expand **Send Ports** and select **PrivateResponder_To_LOB**.</span></span>  
  
6.  <span data-ttu-id="3b797-113">左側のウィンドウで [構成] ウィンドウで選択**ホスト**です。</span><span class="sxs-lookup"><span data-stu-id="3b797-113">In the Configuration window in the left pane, select **Host**.</span></span>  
  
7.  <span data-ttu-id="3b797-114">**ホスト**プロパティで、 **BizTalk ホスト**カテゴリで、 **BizTalkServerApplication**クリックしてドロップダウン リストから**OK**.</span><span class="sxs-lookup"><span data-stu-id="3b797-114">In the **Host** property, in the **BizTalk Host** category, select **BizTalkServerApplication** from the drop-down list, and then click **OK**.</span></span>  
  
### <a name="to-start-the-biztalk-runtime-process"></a><span data-ttu-id="3b797-115">BizTalk ランタイム プロセスを開始するには</span><span class="sxs-lookup"><span data-stu-id="3b797-115">To start the BizTalk runtime process</span></span>  
  
1.  <span data-ttu-id="3b797-116">をクリックして**開始**、をポイント**すべてのプログラム**、をポイント**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] をクリックし、 **BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="3b797-116">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="3b797-117">左側のウィンドウで、BizTalk 管理コンソールで、展開[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**、し、展開**ホスト インスタンス**です。</span><span class="sxs-lookup"><span data-stu-id="3b797-117">In the BizTalk Administration Console, in the left pane, expand [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Host Instances**.</span></span>  
  
3.  <span data-ttu-id="3b797-118">いることを確認の状態、 **BizTalkServerApplication**サービスは**を実行している**です。</span><span class="sxs-lookup"><span data-stu-id="3b797-118">Verify that the status of the **BizTalkServerApplication** service is **Running**.</span></span>  
  
### <a name="to-enlist-and-start-the-orchestration"></a><span data-ttu-id="3b797-119">オーケストレーションを登録して開始するには</span><span class="sxs-lookup"><span data-stu-id="3b797-119">To enlist and start the orchestration</span></span>  
  
1.  <span data-ttu-id="3b797-120">BizTalk 管理コンソールの左側のウィンドウで展開**アプリケーション**、展開**BizTalk アプリケーション 1**、クリックして**オーケストレーション**です。</span><span class="sxs-lookup"><span data-stu-id="3b797-120">In the left pane of the BizTalk Administration Console, expand **Applications**, expand **BizTalk Application 1**, and then click **Orchestrations**.</span></span>  
  
2.  <span data-ttu-id="3b797-121">右側のペインで右クリックし、 **[contosopriceandavailability.privateresponderprocess]** オーケストレーション、およびクリック**Enlist**です。</span><span class="sxs-lookup"><span data-stu-id="3b797-121">In the right pane, right-click the **ContosoPriceAndAvailability.PrivateResponderProcess** orchestration, and then click **Enlist**.</span></span>  
  
3.  <span data-ttu-id="3b797-122">右クリックし、 **[contosopriceandavailability.privateresponderprocess]** オーケストレーション、およびクリック**開始**オーケストレーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="3b797-122">Right-click the **ContosoPriceAndAvailability.PrivateResponderProcess** orchestration, and then click **Start** to start the orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b797-123">参照</span><span class="sxs-lookup"><span data-stu-id="3b797-123">See Also</span></span>  
 [<span data-ttu-id="3b797-124">Fabrikam ソリューションの作成</span><span class="sxs-lookup"><span data-stu-id="3b797-124">Creating the Fabrikam Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-the-fabrikam-solution.md)