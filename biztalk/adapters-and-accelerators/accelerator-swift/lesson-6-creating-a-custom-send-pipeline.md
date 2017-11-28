---
title: "レッスン 6: カスタムを作成する送信パイプライン |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom pipelines
- send pipelines, custom pipelines
ms.assetid: 73a3a546-1e43-4b93-87d3-9bfb32685a57
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a82801b0084f2d1b82a2c25cfc0fa2a9f8f1376c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="lesson-6-creating-a-custom-send-pipeline"></a><span data-ttu-id="44692-102">レッスン 6: カスタムの送信パイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="44692-102">Lesson 6: Creating a Custom Send Pipeline</span></span>
<span data-ttu-id="44692-103">このレッスンでは、BizTalk パイプライン デザイナを使用して、カスタム送信パイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="44692-103">In this lesson, you create a custom send pipeline using BizTalk Pipeline Designer.</span></span> <span data-ttu-id="44692-104">送信パイプラインは前に、のメッセージで実行するパイプライン[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]が宛先にメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="44692-104">A send pipeline is a pipeline you run on messages before [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] sends the messages to their destination.</span></span>  
  
 <span data-ttu-id="44692-105">SWIFT アセンブラー (ASM) コンポーネントを使用するカスタム パイプラインを構成します。</span><span class="sxs-lookup"><span data-stu-id="44692-105">You configure the custom pipeline to use the SWIFT assembler (ASM) component.</span></span> <span data-ttu-id="44692-106">ASM は XML 形式のメッセージを受け取る変換や、SWIFT のフラット ファイルにコンテンツをシリアル化してください。</span><span class="sxs-lookup"><span data-stu-id="44692-106">The ASM takes an XML-formatted message and converts or serializes the content into a SWIFT flat file.</span></span> <span data-ttu-id="44692-107">この変換はで作成した MT103 スキーマに基づいて[レッスン 3: カスタム受信パイプラインを追加する](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-a-custom-receive-pipeline.md)です。</span><span class="sxs-lookup"><span data-stu-id="44692-107">This conversion is based upon the MT103 schema you created in [Lesson 3: Adding a Custom Receive Pipeline](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-a-custom-receive-pipeline.md).</span></span>  
  
### <a name="to-create-a-custom-send-pipeline"></a><span data-ttu-id="44692-108">カスタム送信パイプラインを作成するには</span><span class="sxs-lookup"><span data-stu-id="44692-108">To create a custom send pipeline</span></span>  
  
1.  <span data-ttu-id="44692-109">ソリューション エクスプ ローラーで右クリックし、 **SWIFTPipelines**プロジェクトをポイントし、**追加**、順にクリック**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="44692-109">In Solution Explorer, right-click the **SWIFTPipelines** project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="44692-110">追加新しい項目の SWIFTPipelines ダイアログ ボックスであることを確認**パイプライン ファイル**が選択されてカテゴリ ウィンドウで、**送信パイプライン**テンプレート ペインからです。</span><span class="sxs-lookup"><span data-stu-id="44692-110">In the Add New Item-SWIFTPipelines dialog box, verify that **Pipeline Files** is selected in the Categories pane, and then select **Send Pipeline** from the Templates pane.</span></span>  
  
3.  <span data-ttu-id="44692-111">**名前**ボックスに、入力**MT103SendPipeline.btp**です。</span><span class="sxs-lookup"><span data-stu-id="44692-111">In the **Name** box, type **MT103SendPipeline.btp**.</span></span>  
  
4.  <span data-ttu-id="44692-112">をクリックして**追加**BizTalk パイプライン デザイナーで空白のパイプラインを開きます。</span><span class="sxs-lookup"><span data-stu-id="44692-112">Click **Add** to open the blank pipeline in BizTalk Pipeline Designer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="44692-113">BizTalk パイプライン デザイナーで空のパイプラインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="44692-113">An empty pipeline appears in the BizTalk Pipeline Designer.</span></span> [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="44692-114">ソリューション エクスプ ローラーに SWIFTPipelines プロジェクトの下で、新しいパイプラインを追加します。</span><span class="sxs-lookup"><span data-stu-id="44692-114"> adds the new pipeline to Solution Explorer under the SWIFTPipelines project.</span></span>  
  
 <span data-ttu-id="44692-115">進みます[レッスン 7: カスタムに SWIFT アセンブラーを追加する送信パイプライン](../../adapters-and-accelerators/accelerator-swift/lesson-7-adding-the-swift-assembler-to-a-custom-send-pipeline.md)です。</span><span class="sxs-lookup"><span data-stu-id="44692-115">Proceed to [Lesson 7: Adding the SWIFT Assembler to a Custom Send Pipeline](../../adapters-and-accelerators/accelerator-swift/lesson-7-adding-the-swift-assembler-to-a-custom-send-pipeline.md).</span></span>