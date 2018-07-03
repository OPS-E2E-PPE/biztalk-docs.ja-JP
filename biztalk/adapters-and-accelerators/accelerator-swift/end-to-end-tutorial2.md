---
title: エンド ツー エンド Tutorial2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tutorial, about the tutorial
- tutorial
- tutorial, workflow
ms.assetid: 1aba93b9-6991-46ef-a3bc-3815a5ff473f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da298e0c69de7a351e64aa33ac48611700de3621
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980675"
---
# <a name="end-to-end-tutorial"></a><span data-ttu-id="46050-102">エンド ツー エンドのチュートリアル</span><span class="sxs-lookup"><span data-stu-id="46050-102">End-to-End Tutorial</span></span>
<span data-ttu-id="46050-103">このチュートリアルには、Microsoft の作成および設定する方法について説明する詳細な手順が含まれています。[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]ソリューション。</span><span class="sxs-lookup"><span data-stu-id="46050-103">This tutorial contains detailed steps that describe how to create and set up a Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] solution.</span></span> <span data-ttu-id="46050-104">Microsoft を使用して、モジュールとレッスン[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]スキーマを作成するオーケストレーション、および A4SWIFT を使用して、パイプライン コンポーネントをマップします。</span><span class="sxs-lookup"><span data-stu-id="46050-104">The modules and lessons use Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] to create the schema, maps orchestrations, and pipeline components using A4SWIFT.</span></span>  
  
 <span data-ttu-id="46050-105">次の図は、エンド ツー エンドの A4SWIFT ソリューションの一般的統合エンジン使用シナリオのワークフローを示しています。</span><span class="sxs-lookup"><span data-stu-id="46050-105">The following figure shows the workflow of a common Integration Engine usage scenario for an end-to-end A4SWIFT solution.</span></span>  
  
 <span data-ttu-id="46050-106">![](../../adapters-and-accelerators/accelerator-swift/media/fsa-tut-wklw.gif "FSA_Tut_wklw")</span><span class="sxs-lookup"><span data-stu-id="46050-106">![](../../adapters-and-accelerators/accelerator-swift/media/fsa-tut-wklw.gif "FSA_Tut_wklw")</span></span>  
  
|<span data-ttu-id="46050-107">A4SWIFT チュートリアル ワークフロー キー</span><span class="sxs-lookup"><span data-stu-id="46050-107">A4SWIFT Tutorial Workflow Key</span></span>|  
|-----------------------------------|  
|<span data-ttu-id="46050-108">**ASM** SWIFT アセンブラーを =</span><span class="sxs-lookup"><span data-stu-id="46050-108">**ASM** = SWIFT Assembler</span></span>|  
|<span data-ttu-id="46050-109">**逆アセンブラー** SWIFT 逆アセンブラーを =</span><span class="sxs-lookup"><span data-stu-id="46050-109">**DASM** = SWIFT Disassembler</span></span>|  
|<span data-ttu-id="46050-110">**MTxxx** A4SWIFT メッセージの種類を =</span><span class="sxs-lookup"><span data-stu-id="46050-110">**MTxxx** = A4SWIFT Message type</span></span>|  
|<span data-ttu-id="46050-111">**SIPN** SWIFT のセキュリティで保護された IP ネットワークを =</span><span class="sxs-lookup"><span data-stu-id="46050-111">**SIPN** = SWIFT Secure IP Network</span></span>|  
  
 <span data-ttu-id="46050-112">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="46050-112">This section contains:</span></span>  
  
-   [<span data-ttu-id="46050-113">モジュール 1: SWIFT ソリューションの作成</span><span class="sxs-lookup"><span data-stu-id="46050-113">Module 1: Creating a SWIFT Solution</span></span>](../../adapters-and-accelerators/accelerator-swift/module-1-creating-a-swift-solution.md)  
  
-   [<span data-ttu-id="46050-114">モジュール 2: 新しいスキーマ プロジェクトの追加</span><span class="sxs-lookup"><span data-stu-id="46050-114">Module 2: Adding a New Schemas Project</span></span>](../../adapters-and-accelerators/accelerator-swift/module-2-adding-a-new-schemas-project.md)  
  
-   [<span data-ttu-id="46050-115">モジュール 3: パイプライン プロジェクトの追加</span><span class="sxs-lookup"><span data-stu-id="46050-115">Module 3: Adding a Pipeline Project</span></span>](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md)  
  
-   [<span data-ttu-id="46050-116">モジュール 4: XML 受信場所とフラット ファイル送信ポートの追加</span><span class="sxs-lookup"><span data-stu-id="46050-116">Module 4: Adding an XML Receive Location and Flat File Send Port</span></span>](../../adapters-and-accelerators/accelerator-swift/module-4-adding-an-xml-receive-location-and-flat-file-send-port.md)  
  
-   [<span data-ttu-id="46050-117">モジュール 5: フラット ファイルの受信場所と XML 送信ポートの追加</span><span class="sxs-lookup"><span data-stu-id="46050-117">Module 5: Adding a Flat File Receive Location and XML Send Port</span></span>](../../adapters-and-accelerators/accelerator-swift/module-5-adding-a-flat-file-receive-location-and-xml-send-port.md)  
  
-   [<span data-ttu-id="46050-118">モジュール 6: ビジネス ルールの展開</span><span class="sxs-lookup"><span data-stu-id="46050-118">Module 6: Deploying the Business Rules</span></span>](../../adapters-and-accelerators/accelerator-swift/module-6-deploying-the-business-rules.md)  
  
-   [<span data-ttu-id="46050-119">モジュール 7: 有効なフラット ファイル インスタンスのテスト</span><span class="sxs-lookup"><span data-stu-id="46050-119">Module 7: Testing a Valid Flat File Instance</span></span>](../../adapters-and-accelerators/accelerator-swift/module-7-testing-a-valid-flat-file-instance.md)