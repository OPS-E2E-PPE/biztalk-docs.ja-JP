---
title: "JSON メッセージを処理するカスタム パイプラインを作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b04faad1-b14b-4146-82c7-88a38d2a46a5
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86c85f1a45dceb812fc805a66701653642d0ccb6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="create-custom-pipelines-to-process-json-messages"></a><span data-ttu-id="c2ec6-102">JSON メッセージ処理用のカスタム パイプラインの作成</span><span class="sxs-lookup"><span data-stu-id="c2ec6-102">Create custom pipelines to process JSON messages</span></span>
> [!NOTE]
>  <span data-ttu-id="c2ec6-103">このチュートリアルは、[!INCLUDE[prague](../includes/prague-md.md)] のみを対象としています。</span><span class="sxs-lookup"><span data-stu-id="c2ec6-103">This tutorial applies to [!INCLUDE[prague](../includes/prague-md.md)] only.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c2ec6-104"> では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリで JSON メッセージを処理する際に使用するパイプライン コンポーネントが提供されます。</span><span class="sxs-lookup"><span data-stu-id="c2ec6-104"> provides pipeline components that can be used to process JSON messages within a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span> <span data-ttu-id="c2ec6-105">この手順では、そのパイプラインを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリの構成時に使用するカスタム パイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="c2ec6-105">In this step, we use those pipeline components to create custom pipelines that can be used when configuring a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span>  
  
## <a name="create-a-custom-receive-pipeline"></a><span data-ttu-id="c2ec6-106">カスタム受信パイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="c2ec6-106">Create a custom receive pipeline</span></span>  
  
1.  <span data-ttu-id="c2ec6-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューション エクスプ ローラーからのアプリケーションは、プロジェクトを右クリックし、順にポイント**追加** > **新しい項目の** > **受信パイプライン**.</span><span class="sxs-lookup"><span data-stu-id="c2ec6-107">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application, from the Solution Explorer, right-click the project, and point to **Add** > **New Item** > **Receive Pipeline**.</span></span> <span data-ttu-id="c2ec6-108">パイプラインの名前を付けて`JSONToXmlReceivePipeline.btp`、クリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="c2ec6-108">Provide the pipeline name as `JSONToXmlReceivePipeline.btp`, and then click **Add**.</span></span>  
  
2.  <span data-ttu-id="c2ec6-109">内で、**デコード**ステージを追加、新しい**JSON デコーダー**です。</span><span class="sxs-lookup"><span data-stu-id="c2ec6-109">Within the **Decode** stage add the new **JSON decoder**.</span></span> <span data-ttu-id="c2ec6-110">スクリーンショットのように、他のステージの他のパイプライン コンポーネントで変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="c2ec6-110">In the other stages and other pipeline components as shown in the screenshot, and save changes.</span></span>  
  
     <span data-ttu-id="c2ec6-111">![カスタム受信パイプライン](../core/media/btsjson-receivepipeline.png "BTSJSON_ReceivePipeline")</span><span class="sxs-lookup"><span data-stu-id="c2ec6-111">![Custom receive pipeline](../core/media/btsjson-receivepipeline.png "BTSJSON_ReceivePipeline")</span></span>  
  
## <a name="create-a-custom-send-pipeline"></a><span data-ttu-id="c2ec6-112">カスタム送信パイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="c2ec6-112">Create a custom send pipeline</span></span>  
  
1.  <span data-ttu-id="c2ec6-113">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューション エクスプ ローラーからのアプリケーションは、プロジェクトを右クリックし、順にポイント**追加** > **新しい項目の** > **送信パイプライン**.</span><span class="sxs-lookup"><span data-stu-id="c2ec6-113">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application, from the Solution Explorer, right-click the project, and point to **Add** > **New Item** > **Send Pipeline**.</span></span> <span data-ttu-id="c2ec6-114">パイプラインの名前を付けて`XmlToJSONSendPipeline.btp`、クリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="c2ec6-114">Provide the pipeline name as `XmlToJSONSendPipeline.btp`, and then click **Add**.</span></span>  
  
2.  <span data-ttu-id="c2ec6-115">内で、**エンコード**ステージを追加、新しい**JSON エンコーダー**です。</span><span class="sxs-lookup"><span data-stu-id="c2ec6-115">Within the **Encode** stage add the new **JSON encoder**.</span></span> <span data-ttu-id="c2ec6-116">スクリーンショットのように、他のステージの他のパイプライン コンポーネントで変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="c2ec6-116">In the other stages and other pipeline components as shown in the screenshot, and save changes.</span></span>  
  
     <span data-ttu-id="c2ec6-117">![カスタム送信パイプライン](../core/media/btsjson-sendpipeline.png "BTSJSON_SendPipeline")</span><span class="sxs-lookup"><span data-stu-id="c2ec6-117">![Custom send pipeline](../core/media/btsjson-sendpipeline.png "BTSJSON_SendPipeline")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2ec6-118">参照</span><span class="sxs-lookup"><span data-stu-id="c2ec6-118">See Also</span></span>  
 [<span data-ttu-id="c2ec6-119">BizTalk Server を使用して JSON メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="c2ec6-119">Processing JSON messages using BizTalk Server</span></span>](../core/processing-json-messages-using-biztalk-server.md)