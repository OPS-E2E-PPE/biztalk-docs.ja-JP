---
title: 'レッスン 6: 作成、カスタム送信パイプライン |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- custom pipelines
- send pipelines, custom pipelines
ms.assetid: 73a3a546-1e43-4b93-87d3-9bfb32685a57
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12afba9368554dc85cf57658f674a088db7580d2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973723"
---
# <a name="lesson-6-creating-a-custom-send-pipeline"></a><span data-ttu-id="d02f8-102">レッスン 6: カスタム送信パイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="d02f8-102">Lesson 6: Creating a Custom Send Pipeline</span></span>
<span data-ttu-id="d02f8-103">このレッスンでは、BizTalk パイプライン デザイナを使用して、カスタム送信パイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="d02f8-103">In this lesson, you create a custom send pipeline using BizTalk Pipeline Designer.</span></span> <span data-ttu-id="d02f8-104">送信パイプラインは、前に、メッセージで実行するパイプライン[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]が宛先にメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="d02f8-104">A send pipeline is a pipeline you run on messages before [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] sends the messages to their destination.</span></span>  
  
 <span data-ttu-id="d02f8-105">SWIFT アセンブラー (ASM) コンポーネントを使用するカスタム パイプラインを構成します。</span><span class="sxs-lookup"><span data-stu-id="d02f8-105">You configure the custom pipeline to use the SWIFT assembler (ASM) component.</span></span> <span data-ttu-id="d02f8-106">ASM は、XML 形式のメッセージを取得に変換したり、SWIFT のフラット ファイルにコンテンツをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="d02f8-106">The ASM takes an XML-formatted message and converts or serializes the content into a SWIFT flat file.</span></span> <span data-ttu-id="d02f8-107">この変換はで作成した MT103 スキーマに基づいて[レッスン 3: カスタム受信パイプラインを追加する](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-a-custom-receive-pipeline.md)します。</span><span class="sxs-lookup"><span data-stu-id="d02f8-107">This conversion is based upon the MT103 schema you created in [Lesson 3: Adding a Custom Receive Pipeline](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-a-custom-receive-pipeline.md).</span></span>  
  
### <a name="to-create-a-custom-send-pipeline"></a><span data-ttu-id="d02f8-108">カスタム送信パイプラインを作成するには</span><span class="sxs-lookup"><span data-stu-id="d02f8-108">To create a custom send pipeline</span></span>  
  
1. <span data-ttu-id="d02f8-109">ソリューション エクスプ ローラーで右クリックし、 **SWIFTPipelines**プロジェクトをポイントして、**追加**、 をクリックし、**新しい項目の**。</span><span class="sxs-lookup"><span data-stu-id="d02f8-109">In Solution Explorer, right-click the **SWIFTPipelines** project, point to **Add**, and then click **New Item**.</span></span>  
  
2. <span data-ttu-id="d02f8-110">追加する新しい項目の SWIFTPipelines ダイアログ ボックスであることを確認**パイプライン ファイル**がカテゴリ ウィンドウで選択され、**送信パイプライン**テンプレート ペインから。</span><span class="sxs-lookup"><span data-stu-id="d02f8-110">In the Add New Item-SWIFTPipelines dialog box, verify that **Pipeline Files** is selected in the Categories pane, and then select **Send Pipeline** from the Templates pane.</span></span>  
  
3. <span data-ttu-id="d02f8-111">**名前**ボックスに「 **MT103SendPipeline.btp**します。</span><span class="sxs-lookup"><span data-stu-id="d02f8-111">In the **Name** box, type **MT103SendPipeline.btp**.</span></span>  
  
4. <span data-ttu-id="d02f8-112">クリックして**追加**に BizTalk パイプライン デザイナで、空のパイプラインを開きます。</span><span class="sxs-lookup"><span data-stu-id="d02f8-112">Click **Add** to open the blank pipeline in BizTalk Pipeline Designer.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d02f8-113">BizTalk パイプライン デザイナーで空のパイプラインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d02f8-113">An empty pipeline appears in the BizTalk Pipeline Designer.</span></span> [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="d02f8-114"> ソリューション エクスプ ローラーに SWIFTPipelines プロジェクトの下の新しいパイプラインを追加します。</span><span class="sxs-lookup"><span data-stu-id="d02f8-114"> adds the new pipeline to Solution Explorer under the SWIFTPipelines project.</span></span>  
  
   <span data-ttu-id="d02f8-115">続行する[レッスン 7: SWIFT アセンブラーをカスタムに追加する送信パイプライン](../../adapters-and-accelerators/accelerator-swift/lesson-7-adding-the-swift-assembler-to-a-custom-send-pipeline.md)します。</span><span class="sxs-lookup"><span data-stu-id="d02f8-115">Proceed to [Lesson 7: Adding the SWIFT Assembler to a Custom Send Pipeline](../../adapters-and-accelerators/accelerator-swift/lesson-7-adding-the-swift-assembler-to-a-custom-send-pipeline.md).</span></span>