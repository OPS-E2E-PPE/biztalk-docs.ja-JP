---
title: SWIFT 逆アセンブラーとアセンブラーの操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- developing, assembler
- developing, disassembler
- assembler, developing
- disassembler, developing
ms.assetid: cc88ed4c-baed-4efa-b54f-9fe079df9ba4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e61d34b8ab92f20c2c39c9b4c9394b78d13f100
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376860"
---
# <a name="working-with-the-swift-disassembler-and-assembler"></a><span data-ttu-id="d19d9-102">SWIFT 逆アセンブラーとアセンブラーの操作</span><span class="sxs-lookup"><span data-stu-id="d19d9-102">Working with the SWIFT Disassembler and Assembler</span></span>
<span data-ttu-id="d19d9-103">Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]カスタム パイプライン コンポーネントでは、SWIFT 逆アセンブラー、および SWIFT のフラット ファイル メッセージの処理専用に設計された機能を備えている SWIFT アセンブラーを提供します。</span><span class="sxs-lookup"><span data-stu-id="d19d9-103">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] provides custom pipeline components, the SWIFT disassembler, and SWIFT assembler that have features designed specifically for processing SWIFT flat-file messages.</span></span> <span data-ttu-id="d19d9-104">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]送信し、受信の段階で定義されている特定のタスクを実行するパイプラインの使用、A4SWIFT パイプライン コンポーネントの受信 (受信) と送信 (送信) 処理します。</span><span class="sxs-lookup"><span data-stu-id="d19d9-104">The [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] send and receive pipelines use the A4SWIFT pipeline components to perform specific tasks during defined stages of inbound (receive) and outbound (send) processing.</span></span> <span data-ttu-id="d19d9-105">メッセージの処理、パイプライン、およびパイプライン コンポーネントの詳細については、BizTalk Server のヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d19d9-105">For further details about message processing, pipelines, and pipeline components, see BizTalk Server Help.</span></span>  
  
 <span data-ttu-id="d19d9-106">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d19d9-106">This section contains:</span></span>  
  
-   [<span data-ttu-id="d19d9-107">SWIFT 逆アセンブラーおよびアセンブラーの機能</span><span class="sxs-lookup"><span data-stu-id="d19d9-107">SWIFT Disassembler and Assembler Functionality</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-and-assembler-functionality.md)  
  
-   [<span data-ttu-id="d19d9-108">SWIFT 逆アセンブラーまたはアセンブラーをパイプラインに追加する</span><span class="sxs-lookup"><span data-stu-id="d19d9-108">Adding the SWIFT Disassembler or Assembler to a Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/adding-the-swift-disassembler-or-assembler-to-a-pipeline.md)  
  
-   [<span data-ttu-id="d19d9-109">SWIFT 逆アセンブラーまたはアセンブラーの構成</span><span class="sxs-lookup"><span data-stu-id="d19d9-109">Configuring the SWIFT Disassembler or Assembler</span></span>](../../adapters-and-accelerators/accelerator-swift/configuring-the-swift-disassembler-or-assembler.md)  
  
-   [<span data-ttu-id="d19d9-110">動的メッセージ型の探索とスキーマの解決</span><span class="sxs-lookup"><span data-stu-id="d19d9-110">Dynamic Message Type Discovery and Schema Resolution</span></span>](../../adapters-and-accelerators/accelerator-swift/dynamic-message-type-discovery-and-schema-resolution.md)  
  
-   [<span data-ttu-id="d19d9-111">動的メッセージ型の探索用にカスタム ヘッダー スキーマを作成する</span><span class="sxs-lookup"><span data-stu-id="d19d9-111">Creating Custom Header Schemas for Dynamic Message Type Discovery</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-custom-header-schemas-for-dynamic-message-type-discovery.md)  
  
-   [<span data-ttu-id="d19d9-112">受信バッチの逆アセンブル</span><span class="sxs-lookup"><span data-stu-id="d19d9-112">Disassembling Inbound Batches</span></span>](../../adapters-and-accelerators/accelerator-swift/disassembling-inbound-batches.md)