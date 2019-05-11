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
ms.openlocfilehash: 20b5600cfa54e5df6ae72c3a5f3bb03a255d4c08
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354278"
---
# <a name="create-custom-pipelines-to-process-json-messages"></a><span data-ttu-id="f470d-102">JSON メッセージを処理するカスタム パイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="f470d-102">Create custom pipelines to process JSON messages</span></span>
> [!NOTE]
>  <span data-ttu-id="f470d-103">このチュートリアルは、BizTalk Server にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="f470d-103">This tutorial applies to BizTalk Server only.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="f470d-104">内の JSON メッセージの処理に使用できるパイプライン コンポーネントを提供する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="f470d-104">provides pipeline components that can be used to process JSON messages within a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span> <span data-ttu-id="f470d-105">この手順で使用してこれらのパイプライン コンポーネントを構成するときに使用できるカスタムのパイプラインを作成する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="f470d-105">In this step, we use those pipeline components to create custom pipelines that can be used when configuring a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span>  
  
## <a name="create-a-custom-receive-pipeline"></a><span data-ttu-id="f470d-106">カスタム受信パイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="f470d-106">Create a custom receive pipeline</span></span>  
  
1. <span data-ttu-id="f470d-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューション エクスプ ローラーからのアプリケーション プロジェクトを右クリックし をポイント**追加** > **新しい項目の** > **受信パイプライン**.</span><span class="sxs-lookup"><span data-stu-id="f470d-107">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application, from the Solution Explorer, right-click the project, and point to **Add** > **New Item** > **Receive Pipeline**.</span></span> <span data-ttu-id="f470d-108">パイプラインの名前を付けて`JSONToXmlReceivePipeline.btp`、 をクリックし、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="f470d-108">Provide the pipeline name as `JSONToXmlReceivePipeline.btp`, and then click **Add**.</span></span>  
  
2. <span data-ttu-id="f470d-109">内で、**デコード**段階の新しい追加**JSON デコーダー**します。</span><span class="sxs-lookup"><span data-stu-id="f470d-109">Within the **Decode** stage add the new **JSON decoder**.</span></span> <span data-ttu-id="f470d-110">その他のステージとその他のスクリーン ショットで示すように、パイプライン コンポーネントと変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="f470d-110">In the other stages and other pipeline components as shown in the screenshot, and save changes.</span></span>  
  
    <span data-ttu-id="f470d-111">![カスタム受信パイプライン](../core/media/btsjson-receivepipeline.png "BTSJSON_ReceivePipeline")</span><span class="sxs-lookup"><span data-stu-id="f470d-111">![Custom receive pipeline](../core/media/btsjson-receivepipeline.png "BTSJSON_ReceivePipeline")</span></span>  
  
## <a name="create-a-custom-send-pipeline"></a><span data-ttu-id="f470d-112">カスタム送信パイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="f470d-112">Create a custom send pipeline</span></span>  
  
1. <span data-ttu-id="f470d-113">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューション エクスプ ローラーからのアプリケーション プロジェクトを右クリックし をポイント**追加** > **新しい項目の** > **送信パイプライン**.</span><span class="sxs-lookup"><span data-stu-id="f470d-113">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application, from the Solution Explorer, right-click the project, and point to **Add** > **New Item** > **Send Pipeline**.</span></span> <span data-ttu-id="f470d-114">パイプラインの名前を付けて`XmlToJSONSendPipeline.btp`、 をクリックし、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="f470d-114">Provide the pipeline name as `XmlToJSONSendPipeline.btp`, and then click **Add**.</span></span>  
  
2. <span data-ttu-id="f470d-115">内で、**エンコード**段階の新しい追加**JSON エンコーダー**します。</span><span class="sxs-lookup"><span data-stu-id="f470d-115">Within the **Encode** stage add the new **JSON encoder**.</span></span> <span data-ttu-id="f470d-116">その他のステージとその他のスクリーン ショットで示すように、パイプライン コンポーネントと変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="f470d-116">In the other stages and other pipeline components as shown in the screenshot, and save changes.</span></span>  
  
    <span data-ttu-id="f470d-117">![カスタム送信パイプライン](../core/media/btsjson-sendpipeline.png "BTSJSON_SendPipeline")</span><span class="sxs-lookup"><span data-stu-id="f470d-117">![Custom send pipeline](../core/media/btsjson-sendpipeline.png "BTSJSON_SendPipeline")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f470d-118">参照</span><span class="sxs-lookup"><span data-stu-id="f470d-118">See Also</span></span>  
 [<span data-ttu-id="f470d-119">BizTalk Server を使用して JSON メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="f470d-119">Processing JSON messages using BizTalk Server</span></span>](../core/processing-json-messages-using-biztalk-server.md)