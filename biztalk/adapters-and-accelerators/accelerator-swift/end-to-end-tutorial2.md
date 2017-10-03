---
title: "エンド ツー エンド Tutorial2 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tutorial, about the tutorial
- tutorial
- tutorial, workflow
ms.assetid: 1aba93b9-6991-46ef-a3bc-3815a5ff473f
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c4022595ed05cb779d11e09d66080024ac76654
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="end-to-end-tutorial"></a><span data-ttu-id="4b7b2-102">エンド ツー エンドのチュートリアル</span><span class="sxs-lookup"><span data-stu-id="4b7b2-102">End-to-End Tutorial</span></span>
<span data-ttu-id="4b7b2-103">このチュートリアルには作成および設定する方法を説明する詳しい手順が含まれています、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="4b7b2-103">This tutorial contains detailed steps that describe how to create and set up a [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] solution.</span></span> <span data-ttu-id="4b7b2-104">モジュールとレッスン使用[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]スキーマを作成するオーケストレーション、および A4SWIFT を使用してコンポーネントをパイプラインにマップします。</span><span class="sxs-lookup"><span data-stu-id="4b7b2-104">The modules and lessons use [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] to create the schema, maps orchestrations, and pipeline components using A4SWIFT.</span></span>  
  
 <span data-ttu-id="4b7b2-105">次の図は、エンド ツー エンド A4SWIFT ソリューションの一般的な統合エンジン使用シナリオのワークフローを示しています。</span><span class="sxs-lookup"><span data-stu-id="4b7b2-105">The following figure shows the workflow of a common Integration Engine usage scenario for an end-to-end A4SWIFT solution.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/fsa-tut-wklw.gif "FSA_Tut_wklw")  
  
|<span data-ttu-id="4b7b2-106">A4SWIFT チュートリアル ワークフロー キー</span><span class="sxs-lookup"><span data-stu-id="4b7b2-106">A4SWIFT Tutorial Workflow Key</span></span>|  
|-----------------------------------|  
|<span data-ttu-id="4b7b2-107">**ASM** SWIFT アセンブラーを =</span><span class="sxs-lookup"><span data-stu-id="4b7b2-107">**ASM** = SWIFT Assembler</span></span>|  
|<span data-ttu-id="4b7b2-108">**DASM** SWIFT 逆アセンブラーを =</span><span class="sxs-lookup"><span data-stu-id="4b7b2-108">**DASM** = SWIFT Disassembler</span></span>|  
|<span data-ttu-id="4b7b2-109">**MTxxx** A4SWIFT メッセージの種類を =</span><span class="sxs-lookup"><span data-stu-id="4b7b2-109">**MTxxx** = A4SWIFT Message type</span></span>|  
|<span data-ttu-id="4b7b2-110">**SIPN** SWIFT のセキュリティで保護された IP ネットワークを =</span><span class="sxs-lookup"><span data-stu-id="4b7b2-110">**SIPN** = SWIFT Secure IP Network</span></span>|  
  
 <span data-ttu-id="4b7b2-111">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4b7b2-111">This section contains:</span></span>  
  
-   [<span data-ttu-id="4b7b2-112">第 1 章: SWIFT ソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="4b7b2-112">Module 1: Creating a SWIFT Solution</span></span>](../../adapters-and-accelerators/accelerator-swift/module-1-creating-a-swift-solution.md)  
  
-   [<span data-ttu-id="4b7b2-113">第 2 章: 新しいスキーマ プロジェクトの追加</span><span class="sxs-lookup"><span data-stu-id="4b7b2-113">Module 2: Adding a New Schemas Project</span></span>](../../adapters-and-accelerators/accelerator-swift/module-2-adding-a-new-schemas-project.md)  
  
-   [<span data-ttu-id="4b7b2-114">第 3 章: パイプライン プロジェクトの追加</span><span class="sxs-lookup"><span data-stu-id="4b7b2-114">Module 3: Adding a Pipeline Project</span></span>](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md)  
  
-   [<span data-ttu-id="4b7b2-115">第 4 章: XML の受信場所およびフラット ファイル送信ポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="4b7b2-115">Module 4: Adding an XML Receive Location and Flat File Send Port</span></span>](../../adapters-and-accelerators/accelerator-swift/module-4-adding-an-xml-receive-location-and-flat-file-send-port.md)  
  
-   [<span data-ttu-id="4b7b2-116">第 5 章: フラット ファイルを追加する受信場所と XML 送信ポート</span><span class="sxs-lookup"><span data-stu-id="4b7b2-116">Module 5: Adding a Flat File Receive Location and XML Send Port</span></span>](../../adapters-and-accelerators/accelerator-swift/module-5-adding-a-flat-file-receive-location-and-xml-send-port.md)  
  
-   [<span data-ttu-id="4b7b2-117">第 6 章: ビジネス ルールの展開</span><span class="sxs-lookup"><span data-stu-id="4b7b2-117">Module 6: Deploying the Business Rules</span></span>](../../adapters-and-accelerators/accelerator-swift/module-6-deploying-the-business-rules.md)  
  
-   [<span data-ttu-id="4b7b2-118">第 7 章: テストの有効なフラット ファイル インスタンス</span><span class="sxs-lookup"><span data-stu-id="4b7b2-118">Module 7: Testing a Valid Flat File Instance</span></span>](../../adapters-and-accelerators/accelerator-swift/module-7-testing-a-valid-flat-file-instance.md)