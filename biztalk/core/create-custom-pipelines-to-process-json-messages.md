---
title: JSON メッセージを処理するカスタム パイプラインの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b04faad1-b14b-4146-82c7-88a38d2a46a5
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e28f825b1f26f3c080a02fd9a2e2bf8960a816fd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005995"
---
# <a name="create-custom-pipelines-to-process-json-messages"></a><span data-ttu-id="57948-102">JSON メッセージ処理用のカスタム パイプラインの作成</span><span class="sxs-lookup"><span data-stu-id="57948-102">Create custom pipelines to process JSON messages</span></span>
> [!NOTE]
>  <span data-ttu-id="57948-103">このチュートリアルは、BizTalk Server にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="57948-103">This tutorial applies to BizTalk Server only.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="57948-104"> では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリで JSON メッセージを処理する際に使用するパイプライン コンポーネントが提供されます。</span><span class="sxs-lookup"><span data-stu-id="57948-104"> provides pipeline components that can be used to process JSON messages within a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span> <span data-ttu-id="57948-105">この手順では、そのパイプラインを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリの構成時に使用するカスタム パイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="57948-105">In this step, we use those pipeline components to create custom pipelines that can be used when configuring a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span>  
  
## <a name="create-a-custom-receive-pipeline"></a><span data-ttu-id="57948-106">カスタム受信パイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="57948-106">Create a custom receive pipeline</span></span>  
  
1. <span data-ttu-id="57948-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューション エクスプ ローラーからのアプリケーション プロジェクトを右クリックし をポイント**追加** > **新しい項目の** > **受信パイプライン**.</span><span class="sxs-lookup"><span data-stu-id="57948-107">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application, from the Solution Explorer, right-click the project, and point to **Add** > **New Item** > **Receive Pipeline**.</span></span> <span data-ttu-id="57948-108">パイプラインの名前を付けて`JSONToXmlReceivePipeline.btp`、 をクリックし、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="57948-108">Provide the pipeline name as `JSONToXmlReceivePipeline.btp`, and then click **Add**.</span></span>  
  
2. <span data-ttu-id="57948-109">内で、**デコード**段階の新しい追加**JSON デコーダー**します。</span><span class="sxs-lookup"><span data-stu-id="57948-109">Within the **Decode** stage add the new **JSON decoder**.</span></span> <span data-ttu-id="57948-110">スクリーンショットのように、他のステージの他のパイプライン コンポーネントで変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="57948-110">In the other stages and other pipeline components as shown in the screenshot, and save changes.</span></span>  
  
    <span data-ttu-id="57948-111">![カスタム受信パイプライン](../core/media/btsjson-receivepipeline.png "BTSJSON_ReceivePipeline")</span><span class="sxs-lookup"><span data-stu-id="57948-111">![Custom receive pipeline](../core/media/btsjson-receivepipeline.png "BTSJSON_ReceivePipeline")</span></span>  
  
## <a name="create-a-custom-send-pipeline"></a><span data-ttu-id="57948-112">カスタム送信パイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="57948-112">Create a custom send pipeline</span></span>  
  
1. <span data-ttu-id="57948-113">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューション エクスプ ローラーからのアプリケーション プロジェクトを右クリックし をポイント**追加** > **新しい項目の** > **送信パイプライン**.</span><span class="sxs-lookup"><span data-stu-id="57948-113">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application, from the Solution Explorer, right-click the project, and point to **Add** > **New Item** > **Send Pipeline**.</span></span> <span data-ttu-id="57948-114">パイプラインの名前を付けて`XmlToJSONSendPipeline.btp`、 をクリックし、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="57948-114">Provide the pipeline name as `XmlToJSONSendPipeline.btp`, and then click **Add**.</span></span>  
  
2. <span data-ttu-id="57948-115">内で、**エンコード**段階の新しい追加**JSON エンコーダー**します。</span><span class="sxs-lookup"><span data-stu-id="57948-115">Within the **Encode** stage add the new **JSON encoder**.</span></span> <span data-ttu-id="57948-116">スクリーンショットのように、他のステージの他のパイプライン コンポーネントで変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="57948-116">In the other stages and other pipeline components as shown in the screenshot, and save changes.</span></span>  
  
    <span data-ttu-id="57948-117">![カスタム送信パイプライン](../core/media/btsjson-sendpipeline.png "BTSJSON_SendPipeline")</span><span class="sxs-lookup"><span data-stu-id="57948-117">![Custom send pipeline](../core/media/btsjson-sendpipeline.png "BTSJSON_SendPipeline")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57948-118">参照</span><span class="sxs-lookup"><span data-stu-id="57948-118">See Also</span></span>  
 [<span data-ttu-id="57948-119">BizTalk Server を使用して JSON メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="57948-119">Processing JSON messages using BizTalk Server</span></span>](../core/processing-json-messages-using-biztalk-server.md)