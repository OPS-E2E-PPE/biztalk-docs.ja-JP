---
title: "SWIFT 逆アセンブラおよびアセンブラの操作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- developing, assembler
- developing, disassembler
- assembler, developing
- disassembler, developing
ms.assetid: cc88ed4c-baed-4efa-b54f-9fe079df9ba4
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1ae6acb6239821362ad5f488e9b95b9ffcc43d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="working-with-the-swift-disassembler-and-assembler"></a><span data-ttu-id="9ff78-102">SWIFT 逆アセンブラおよびアセンブラの操作</span><span class="sxs-lookup"><span data-stu-id="9ff78-102">Working with the SWIFT Disassembler and Assembler</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="9ff78-103">[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]カスタム パイプライン コンポーネント、SWIFT の逆アセンブラー、および SWIFT のフラット ファイル メッセージの処理専用に設計された機能が用意されている SWIFT アセンブラーを提供します。</span><span class="sxs-lookup"><span data-stu-id="9ff78-103"> [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] provides custom pipeline components, the SWIFT disassembler, and SWIFT assembler that have features designed specifically for processing SWIFT flat-file messages.</span></span> <span data-ttu-id="9ff78-104">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]送信および受信の段階で定義された特定のタスクを実行するパイプラインを使用して、A4SWIFT パイプライン コンポーネントを受信 (受信) と送信 (送信) 処理します。</span><span class="sxs-lookup"><span data-stu-id="9ff78-104">The [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] send and receive pipelines use the A4SWIFT pipeline components to perform specific tasks during defined stages of inbound (receive) and outbound (send) processing.</span></span> <span data-ttu-id="9ff78-105">メッセージの処理、パイプライン、およびパイプライン コンポーネントに関する詳細については、次を参照してください。[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="9ff78-105">For further details about message processing, pipelines, and pipeline components, see [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Help.</span></span>  
  
 <span data-ttu-id="9ff78-106">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9ff78-106">This section contains:</span></span>  
  
-   [<span data-ttu-id="9ff78-107">SWIFT 逆アセンブラーおよびアセンブラー機能</span><span class="sxs-lookup"><span data-stu-id="9ff78-107">SWIFT Disassembler and Assembler Functionality</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-and-assembler-functionality.md)  
  
-   [<span data-ttu-id="9ff78-108">SWIFT 逆アセンブラーまたはアセンブラーをパイプラインに追加します。</span><span class="sxs-lookup"><span data-stu-id="9ff78-108">Adding the SWIFT Disassembler or Assembler to a Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/adding-the-swift-disassembler-or-assembler-to-a-pipeline.md)  
  
-   [<span data-ttu-id="9ff78-109">SWIFT 逆アセンブラーまたはアセンブラーを構成します。</span><span class="sxs-lookup"><span data-stu-id="9ff78-109">Configuring the SWIFT Disassembler or Assembler</span></span>](../../adapters-and-accelerators/accelerator-swift/configuring-the-swift-disassembler-or-assembler.md)  
  
-   [<span data-ttu-id="9ff78-110">動的なメッセージの種類の探索とスキーマの解決</span><span class="sxs-lookup"><span data-stu-id="9ff78-110">Dynamic Message Type Discovery and Schema Resolution</span></span>](../../adapters-and-accelerators/accelerator-swift/dynamic-message-type-discovery-and-schema-resolution.md)  
  
-   [<span data-ttu-id="9ff78-111">動的なメッセージの種類の探索用のカスタム ヘッダーのスキーマの作成</span><span class="sxs-lookup"><span data-stu-id="9ff78-111">Creating Custom Header Schemas for Dynamic Message Type Discovery</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-custom-header-schemas-for-dynamic-message-type-discovery.md)  
  
-   [<span data-ttu-id="9ff78-112">受信バッチを逆アセンブル</span><span class="sxs-lookup"><span data-stu-id="9ff78-112">Disassembling Inbound Batches</span></span>](../../adapters-and-accelerators/accelerator-swift/disassembling-inbound-batches.md)