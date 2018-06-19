---
title: 'レッスン 3: カスタム受信パイプラインを追加する |Microsoft ドキュメント'
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
ms.openlocfilehash: 76abee50cce743dde6c62ea078f5ef9dada0c998
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210010"
---
# <a name="lesson-3-adding-a-custom-receive-pipeline"></a><span data-ttu-id="360cc-102">レッスン 3: カスタム受信パイプラインを追加します。</span><span class="sxs-lookup"><span data-stu-id="360cc-102">Lesson 3: Adding a Custom Receive Pipeline</span></span>
<span data-ttu-id="360cc-103">このレッスンでは、BizTalk パイプライン デザイナを使用してカスタム受信パイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="360cc-103">In this lesson you create a custom receive pipeline using BizTalk Pipeline Designer.</span></span> <span data-ttu-id="360cc-104">カスタム受信パイプラインは、アダプターがその前に、メッセージを受信した後のメッセージが実行されるパイプライン[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]メッセージ ボックス データベースに公開します。</span><span class="sxs-lookup"><span data-stu-id="360cc-104">A custom receive pipeline is a pipeline that is run on messages after the adapter receives the messages, but before [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] publishes them to the MessageBox database.</span></span>  
  
 <span data-ttu-id="360cc-105">SWIFT 逆アセンブラー (DASM) コンポーネントを使用してカスタム パイプラインを構成します。</span><span class="sxs-lookup"><span data-stu-id="360cc-105">You configure the custom pipeline to use the SWIFT disassembler (DASM) component.</span></span> <span data-ttu-id="360cc-106">SWIFT の逆アセンブラーでは SWIFT 形式のフラット ファイル、変換、または解析、XML ベースの表現に SWIFT メッセージの内容を[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を使用できます。</span><span class="sxs-lookup"><span data-stu-id="360cc-106">The SWIFT disassembler takes a SWIFT-formatted flat file and converts, or parses, the content of the SWIFT message into an XML-based representation, which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] can consume.</span></span>  
  
 <span data-ttu-id="360cc-107">前の手順で追加した MT103 ランタイム スキーマ ([レッスン 2: プロジェクト参照を追加する](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-project-references.md)) 変換に使用される形式です。</span><span class="sxs-lookup"><span data-stu-id="360cc-107">The MT103 runtime schema that you added in the previous step ([Lesson 2: Adding Project References](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-project-references.md)) is the format that you use for the conversion.</span></span>  
  
### <a name="to-create-a-new-custom-receive-pipeline"></a><span data-ttu-id="360cc-108">新しいカスタム受信パイプラインを作成するには</span><span class="sxs-lookup"><span data-stu-id="360cc-108">To create a new custom receive pipeline</span></span>  
  
1.  <span data-ttu-id="360cc-109">ソリューション エクスプ ローラーで右クリックし、 **SWIFTPipelines**プロジェクトをポイントし、**追加**、順にクリック**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="360cc-109">In Solution Explorer, right-click the **SWIFTPipelines** project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="360cc-110">追加新しい項目の SWIFTPipelines ダイアログ ボックスで、**パイプライン ファイル**カテゴリ ウィンドウで、選択**受信パイプライン**テンプレート ペインからです。</span><span class="sxs-lookup"><span data-stu-id="360cc-110">In the Add New Item-SWIFTPipelines dialog box, click **Pipeline Files** in the Categories pane, and then select **Receive Pipeline** from the Templates pane.</span></span>  
  
3.  <span data-ttu-id="360cc-111">**名前**ボックスに、入力**MT103ReceivePipeline.btp**です。</span><span class="sxs-lookup"><span data-stu-id="360cc-111">In the **Name** box, type **MT103ReceivePipeline.btp**.</span></span>  
  
4.  <span data-ttu-id="360cc-112">をクリックして**追加**BizTalk パイプライン デザイナーで空白のパイプラインを開きます。</span><span class="sxs-lookup"><span data-stu-id="360cc-112">Click **Add** to open the blank pipeline in BizTalk Pipeline Designer.</span></span>  
  
 <span data-ttu-id="360cc-113">BizTalk パイプライン デザイナーで空のパイプラインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="360cc-113">An empty pipeline appears in the BizTalk Pipeline Designer.</span></span> <span data-ttu-id="360cc-114">Visual Studio はまた、SWIFTPipelines プロジェクトの下で、ソリューション エクスプ ローラーに新しいパイプラインを追加します。</span><span class="sxs-lookup"><span data-stu-id="360cc-114">Visual Studio also adds the new pipeline to Solution Explorer under the SWIFTPipelines project.</span></span>  
  
 <span data-ttu-id="360cc-115">進みます[レッスン 4: SWIFT アセンブラーおよび逆アセンブラーをツールボックスに追加する](../../adapters-and-accelerators/accelerator-swift/lesson-4-adding-the-swift-assembler-and-disassembler-to-the-toolbox.md)です。</span><span class="sxs-lookup"><span data-stu-id="360cc-115">Proceed to [Lesson 4: Adding the SWIFT Assembler and Disassembler to the Toolbox](../../adapters-and-accelerators/accelerator-swift/lesson-4-adding-the-swift-assembler-and-disassembler-to-the-toolbox.md).</span></span>