---
title: 'モジュール 3: パイプライン プロジェクトの追加 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tutorial, creating pipelines
- projects, pipelines
- pipelines, adding to projects
ms.assetid: 38bf1629-df29-4bea-840b-60b354b06430
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85305614cec2757a91aa006238b3eb1ca4fbdbba
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970659"
---
# <a name="module-3-adding-a-pipeline-project"></a><span data-ttu-id="0c1d1-102">モジュール 3: パイプライン プロジェクトの追加</span><span class="sxs-lookup"><span data-stu-id="0c1d1-102">Module 3: Adding a Pipeline Project</span></span>
<span data-ttu-id="0c1d1-103">このモジュールでは、新しいプロジェクトをカスタムの送信を含むソリューションに追加し、受信パイプラインします。</span><span class="sxs-lookup"><span data-stu-id="0c1d1-103">In this module, you add a new project to your solution that contains your custom send and receive pipelines.</span></span> <span data-ttu-id="0c1d1-104">SWIFT メッセージは、本質的にフラット ファイルには、使用しているため、Microsoft に含まれている既定のパイプラインを使用することはできません[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="0c1d1-104">Because you are working with SWIFT messages, which are flat file in nature, you cannot use the default pipelines that are included with Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)].</span></span>  
  
 <span data-ttu-id="0c1d1-105">SWIFT メッセージに追加レベルの検証が必要なマイクロソフト[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]カスタム逆アセンブラー (逆アセンブラー) と SWIFT のメッセージで使用するためのアセンブラー (ASM) のコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0c1d1-105">SWIFT messages require additional levels of validation so Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] includes custom disassembler (DASM) and assembler (ASM) components for use with SWIFT messages.</span></span>  
  
 <span data-ttu-id="0c1d1-106">このモジュールで追加することも、新しいパイプライン プロジェクトに追加受信し、送信パイプライン、SWIFT 逆アセンブラーおよび ASM を使用します。</span><span class="sxs-lookup"><span data-stu-id="0c1d1-106">In this module, you also add a new pipeline project, add receive and send pipelines, and use the SWIFT DASM and ASM.</span></span>  
  
 <span data-ttu-id="0c1d1-107">BizTalk プロジェクト テンプレートを選択すると、Microsoft 内での BizTalk マッパーなど、BizTalk ツールを公開します[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]開発環境。</span><span class="sxs-lookup"><span data-stu-id="0c1d1-107">Selecting the BizTalk project template exposes the BizTalk tools, such as BizTalk Mapper, within the Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] development environment.</span></span>  
  
 <span data-ttu-id="0c1d1-108">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0c1d1-108">This section contains:</span></span>  
  
-   [<span data-ttu-id="0c1d1-109">レッスン 1: パイプライン プロジェクトをソリューションに追加する</span><span class="sxs-lookup"><span data-stu-id="0c1d1-109">Lesson 1: Adding a Pipelines Project to the Solution</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-1-adding-a-pipelines-project-to-the-solution.md)  
  
-   [<span data-ttu-id="0c1d1-110">レッスン 2: プロジェクト参照を追加する</span><span class="sxs-lookup"><span data-stu-id="0c1d1-110">Lesson 2: Adding Project References</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-project-references.md)  
  
-   [<span data-ttu-id="0c1d1-111">レッスン 3: カスタム受信パイプラインを追加する</span><span class="sxs-lookup"><span data-stu-id="0c1d1-111">Lesson 3: Adding a Custom Receive Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-a-custom-receive-pipeline.md)  
  
-   [<span data-ttu-id="0c1d1-112">レッスン 4: SWIFT アセンブラーと逆アセンブラーをツールボックスに追加する</span><span class="sxs-lookup"><span data-stu-id="0c1d1-112">Lesson 4: Adding the SWIFT Assembler and Disassembler to the Toolbox</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-4-adding-the-swift-assembler-and-disassembler-to-the-toolbox.md)  
  
-   [<span data-ttu-id="0c1d1-113">レッスン 5: SWIFT 逆アセンブラーをカスタム受信パイプラインに追加する</span><span class="sxs-lookup"><span data-stu-id="0c1d1-113">Lesson 5: Adding the SWIFT Disassembler to a Custom Receive Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-5-adding-the-swift-disassembler-to-a-custom-receive-pipeline.md)  
  
-   [<span data-ttu-id="0c1d1-114">レッスン 6: カスタム送信パイプラインを作成する</span><span class="sxs-lookup"><span data-stu-id="0c1d1-114">Lesson 6: Creating a Custom Send Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-6-creating-a-custom-send-pipeline.md)  
  
-   [<span data-ttu-id="0c1d1-115">レッスン 7: カスタム送信パイプラインに SWIFT アセンブラーを追加する</span><span class="sxs-lookup"><span data-stu-id="0c1d1-115">Lesson 7: Adding the SWIFT Assembler to a Custom Send Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-7-adding-the-swift-assembler-to-a-custom-send-pipeline.md)  
  
-   [<span data-ttu-id="0c1d1-116">レッスン 8: アセンブリをビルドして展開する</span><span class="sxs-lookup"><span data-stu-id="0c1d1-116">Lesson 8: Building and Deploying the Assembly</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-8-building-and-deploying-the-assembly.md)