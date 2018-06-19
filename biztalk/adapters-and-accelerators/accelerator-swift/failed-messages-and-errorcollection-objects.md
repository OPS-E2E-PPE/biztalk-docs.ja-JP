---
title: 失敗したメッセージおよび元のオブジェクト |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- failed messages, ErrorCollection objects
- ErrorCollection objects
ms.assetid: 8a2ff3b5-d7a0-4595-8b74-3133e9e3a821
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65598ef44bfe3e34bd1695aa81bee368c5175793
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209234"
---
# <a name="failed-messages-and-errorcollection-objects"></a><span data-ttu-id="94101-102">失敗したメッセージと元のオブジェクト</span><span class="sxs-lookup"><span data-stu-id="94101-102">Failed Messages and ErrorCollection Objects</span></span>
<span data-ttu-id="94101-103">昇格させたプロパティは、失敗したメッセージを修飾することだけでなく[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] 、失敗したメッセージをメッセージと共に、メッセージ ボックス データベースに公開*一部*という**ErrorSegment**.</span><span class="sxs-lookup"><span data-stu-id="94101-103">In addition to decorating a failed message with promoted properties, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] publishes the failed message to the MessageBox database with an additional message *part*, called **ErrorSegment**.</span></span> <span data-ttu-id="94101-104">このエラーの部分を含む XML を表す、**元**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="94101-104">This error part contains XML representing an **ErrorCollection** object.</span></span> <span data-ttu-id="94101-105">A4SWIFT 逆アセンブラーは追加、**元**メッセージ (解析、XML の検証、およびビジネス ルール エンジン (BRE)) を処理の各段階のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="94101-105">The A4SWIFT disassembler populates the **ErrorCollection** object during each stage of message processing (parsing, XML validation, and Business Rule Engine (BRE) validation).</span></span>  
  
 <span data-ttu-id="94101-106">**元**オブジェクトは、コレクションの*エラー オブジェクト*を表す特定のエラーまたはエラー メッセージの処理中にします。</span><span class="sxs-lookup"><span data-stu-id="94101-106">The **ErrorCollection** object is a collection of *error objects*, each of which represents a particular error or failure during message processing.</span></span> <span data-ttu-id="94101-107">個々 のエラー オブジェクトには、(メッセージとエラーの説明内の場所) などの 1 つのエラーの詳細が含まれます。</span><span class="sxs-lookup"><span data-stu-id="94101-107">The individual error objects contain details about a single failure (such as the location in the message and a description of the failure).</span></span>  
  
 <span data-ttu-id="94101-108">詳細については、**元**アプリケーション プログラミング インターフェイス (API) と使用方法の詳細は、元のクラスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="94101-108">For more information about the **ErrorCollection** application programming interface (API) and usage details, see ErrorCollection Class.</span></span> <span data-ttu-id="94101-109">個々 のエラー オブジェクトに関する詳細については、ErrorBase クラス (エラー オブジェクトの基本クラス)、BreValidationError クラス、ParseError クラス、および XmlValidationError クラスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="94101-109">For more information about individual error objects, see ErrorBase Class (the base class for error objects), BreValidationError Class, ParseError Class, and XmlValidationError Class.</span></span>  
  
 <span data-ttu-id="94101-110">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="94101-110">This section contains:</span></span>  
  
-   [<span data-ttu-id="94101-111">キャプチャおよび Message Repair ソリューションを拡張します。</span><span class="sxs-lookup"><span data-stu-id="94101-111">Extending the Solution for Capture and Message Repair</span></span>](../../adapters-and-accelerators/accelerator-swift/extending-the-solution-for-capture-and-message-repair.md)