---
title: 'レッスン 3: カスタム受信パイプラインを追加する |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, creating custom pipelines
- custom pipelines
ms.assetid: 1917b8e2-4f1c-4c20-abe4-ea18a406eeeb
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5238dac95df214a25c130369b134bc155212516
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993747"
---
# <a name="lesson-3-adding-a-custom-receive-pipeline"></a><span data-ttu-id="a6c15-102">レッスン 3: カスタム受信パイプラインを追加します。</span><span class="sxs-lookup"><span data-stu-id="a6c15-102">Lesson 3: Adding a Custom Receive Pipeline</span></span>
<span data-ttu-id="a6c15-103">このレッスンでは、BizTalk パイプライン デザイナを使用してカスタム受信パイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="a6c15-103">In this lesson you create a custom receive pipeline using BizTalk Pipeline Designer.</span></span> <span data-ttu-id="a6c15-104">カスタム受信パイプラインは、アダプターが前に、メッセージを受信した後に、メッセージで実行されるパイプライン[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]メッセージ ボックス データベースに公開します。</span><span class="sxs-lookup"><span data-stu-id="a6c15-104">A custom receive pipeline is a pipeline that is run on messages after the adapter receives the messages, but before [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] publishes them to the MessageBox database.</span></span>  
  
 <span data-ttu-id="a6c15-105">SWIFT 逆アセンブラー (逆アセンブラー) コンポーネントを使用するカスタム パイプラインを構成します。</span><span class="sxs-lookup"><span data-stu-id="a6c15-105">You configure the custom pipeline to use the SWIFT disassembler (DASM) component.</span></span> <span data-ttu-id="a6c15-106">SWIFT 逆アセンブラーでは、SWIFT 形式のフラット ファイルと変換、または解析、SWIFT、XML ベースの表現では、メッセージの内容を[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]消費することができます。</span><span class="sxs-lookup"><span data-stu-id="a6c15-106">The SWIFT disassembler takes a SWIFT-formatted flat file and converts, or parses, the content of the SWIFT message into an XML-based representation, which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] can consume.</span></span>  
  
 <span data-ttu-id="a6c15-107">前の手順で追加した MT103 ランタイム スキーマ ([レッスン 2: プロジェクト参照を追加する](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-project-references.md)) は、変換に使用する形式です。</span><span class="sxs-lookup"><span data-stu-id="a6c15-107">The MT103 runtime schema that you added in the previous step ([Lesson 2: Adding Project References](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-project-references.md)) is the format that you use for the conversion.</span></span>  
  
### <a name="to-create-a-new-custom-receive-pipeline"></a><span data-ttu-id="a6c15-108">新しいカスタム受信パイプラインを作成するには</span><span class="sxs-lookup"><span data-stu-id="a6c15-108">To create a new custom receive pipeline</span></span>  
  
1. <span data-ttu-id="a6c15-109">ソリューション エクスプ ローラーで右クリックし、 **SWIFTPipelines**プロジェクトをポイントして、**追加**、 をクリックし、**新しい項目の**。</span><span class="sxs-lookup"><span data-stu-id="a6c15-109">In Solution Explorer, right-click the **SWIFTPipelines** project, point to **Add**, and then click **New Item**.</span></span>  
  
2. <span data-ttu-id="a6c15-110">追加する新しい項目の SWIFTPipelines ダイアログ ボックスで、**パイプライン ファイル**カテゴリ ウィンドウで選択し**受信パイプライン**テンプレート ペインから。</span><span class="sxs-lookup"><span data-stu-id="a6c15-110">In the Add New Item-SWIFTPipelines dialog box, click **Pipeline Files** in the Categories pane, and then select **Receive Pipeline** from the Templates pane.</span></span>  
  
3. <span data-ttu-id="a6c15-111">**名前**ボックスに「 **MT103ReceivePipeline.btp**します。</span><span class="sxs-lookup"><span data-stu-id="a6c15-111">In the **Name** box, type **MT103ReceivePipeline.btp**.</span></span>  
  
4. <span data-ttu-id="a6c15-112">クリックして**追加**に BizTalk パイプライン デザイナで、空のパイプラインを開きます。</span><span class="sxs-lookup"><span data-stu-id="a6c15-112">Click **Add** to open the blank pipeline in BizTalk Pipeline Designer.</span></span>  
  
   <span data-ttu-id="a6c15-113">BizTalk パイプライン デザイナーで空のパイプラインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6c15-113">An empty pipeline appears in the BizTalk Pipeline Designer.</span></span> <span data-ttu-id="a6c15-114">Visual Studio ではソリューション エクスプ ローラーに新しいパイプラインも SWIFTPipelines プロジェクトの下に追加します。</span><span class="sxs-lookup"><span data-stu-id="a6c15-114">Visual Studio also adds the new pipeline to Solution Explorer under the SWIFTPipelines project.</span></span>  
  
   <span data-ttu-id="a6c15-115">続行する[レッスン 4: SWIFT アセンブラーと逆アセンブラーをツールボックスに追加する](../../adapters-and-accelerators/accelerator-swift/lesson-4-adding-the-swift-assembler-and-disassembler-to-the-toolbox.md)します。</span><span class="sxs-lookup"><span data-stu-id="a6c15-115">Proceed to [Lesson 4: Adding the SWIFT Assembler and Disassembler to the Toolbox](../../adapters-and-accelerators/accelerator-swift/lesson-4-adding-the-swift-assembler-and-disassembler-to-the-toolbox.md).</span></span>