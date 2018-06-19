---
title: '第 3 章: パイプライン プロジェクトを追加 |Microsoft ドキュメント'
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
ms.openlocfilehash: 2d14e0f334514fd35a7f8de963f7fb457e3fbbd5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22208162"
---
# <a name="module-3-adding-a-pipeline-project"></a><span data-ttu-id="85aec-102">第 3 章: パイプライン プロジェクトの追加</span><span class="sxs-lookup"><span data-stu-id="85aec-102">Module 3: Adding a Pipeline Project</span></span>
<span data-ttu-id="85aec-103">このモジュールでは、新しいプロジェクトをカスタムの送信を含むソリューションを追加し、受信パイプラインします。</span><span class="sxs-lookup"><span data-stu-id="85aec-103">In this module, you add a new project to your solution that contains your custom send and receive pipelines.</span></span> <span data-ttu-id="85aec-104">含まれている既定のパイプラインを使用することはできません、本質的にフラット ファイルであり、SWIFT のメッセージに作業しているため[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="85aec-104">Because you are working with SWIFT messages, which are flat file in nature, you cannot use the default pipelines that are included with [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)].</span></span>  
  
 <span data-ttu-id="85aec-105">SWIFT メッセージ レベルが必要に追加の検証のため[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]カスタム逆アセンブラー (DASM) および SWIFT メッセージで使用するためのアセンブラー (ASM) コンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="85aec-105">SWIFT messages require additional levels of validation so [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] includes custom disassembler (DASM) and assembler (ASM) components for use with SWIFT messages.</span></span>  
  
 <span data-ttu-id="85aec-106">このモジュールに追加することも、新しいパイプライン プロジェクトに追加受信し送信パイプライン、および SWIFT DASM と ASM を使用します。</span><span class="sxs-lookup"><span data-stu-id="85aec-106">In this module, you also add a new pipeline project, add receive and send pipelines, and use the SWIFT DASM and ASM.</span></span>  
  
 <span data-ttu-id="85aec-107">BizTalk マッパー, など、BizTalk ツール内で公開する BizTalk プロジェクト テンプレートを選択する、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]開発環境です。</span><span class="sxs-lookup"><span data-stu-id="85aec-107">Selecting the BizTalk project template exposes the BizTalk tools, such as BizTalk Mapper, within the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] development environment.</span></span>  
  
 <span data-ttu-id="85aec-108">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="85aec-108">This section contains:</span></span>  
  
-   [<span data-ttu-id="85aec-109">レッスン 1: パイプライン プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="85aec-109">Lesson 1: Adding a Pipelines Project to the Solution</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-1-adding-a-pipelines-project-to-the-solution.md)  
  
-   [<span data-ttu-id="85aec-110">レッスン 2: プロジェクト参照の追加</span><span class="sxs-lookup"><span data-stu-id="85aec-110">Lesson 2: Adding Project References</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-project-references.md)  
  
-   [<span data-ttu-id="85aec-111">レッスン 3: カスタム受信パイプラインを追加します。</span><span class="sxs-lookup"><span data-stu-id="85aec-111">Lesson 3: Adding a Custom Receive Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-a-custom-receive-pipeline.md)  
  
-   [<span data-ttu-id="85aec-112">レッスン 4: SWIFT アセンブラーおよび逆アセンブラーをツールボックスに追加します。</span><span class="sxs-lookup"><span data-stu-id="85aec-112">Lesson 4: Adding the SWIFT Assembler and Disassembler to the Toolbox</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-4-adding-the-swift-assembler-and-disassembler-to-the-toolbox.md)  
  
-   [<span data-ttu-id="85aec-113">レッスン 5: カスタム受信パイプラインに SWIFT の逆アセンブラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="85aec-113">Lesson 5: Adding the SWIFT Disassembler to a Custom Receive Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-5-adding-the-swift-disassembler-to-a-custom-receive-pipeline.md)  
  
-   [<span data-ttu-id="85aec-114">レッスン 6: カスタムの送信パイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="85aec-114">Lesson 6: Creating a Custom Send Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-6-creating-a-custom-send-pipeline.md)  
  
-   [<span data-ttu-id="85aec-115">レッスン 7: カスタム送信パイプラインに SWIFT アセンブラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="85aec-115">Lesson 7: Adding the SWIFT Assembler to a Custom Send Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-7-adding-the-swift-assembler-to-a-custom-send-pipeline.md)  
  
-   [<span data-ttu-id="85aec-116">レッスン 8: のビルドと、アセンブリの展開</span><span class="sxs-lookup"><span data-stu-id="85aec-116">Lesson 8: Building and Deploying the Assembly</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-8-building-and-deploying-the-assembly.md)