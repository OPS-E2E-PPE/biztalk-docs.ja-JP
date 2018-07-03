---
title: メッセージと ErrorCollection オブジェクトが失敗しました |Microsoft Docs
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
ms.openlocfilehash: e4f9fd17807d9bc1b92b1eae1ac75662843c8e17
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993163"
---
# <a name="failed-messages-and-errorcollection-objects"></a><span data-ttu-id="9cb0b-102">失敗したメッセージと ErrorCollection オブジェクト</span><span class="sxs-lookup"><span data-stu-id="9cb0b-102">Failed Messages and ErrorCollection Objects</span></span>
<span data-ttu-id="9cb0b-103">Microsoft の昇格させたプロパティを持つ失敗したメッセージを修飾することだけでなく[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]追加のメッセージをメッセージ ボックス データベースに、失敗したメッセージを発行*一部*という**ErrorSegment**.</span><span class="sxs-lookup"><span data-stu-id="9cb0b-103">In addition to decorating a failed message with promoted properties, Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] publishes the failed message to the MessageBox database with an additional message *part*, called **ErrorSegment**.</span></span> <span data-ttu-id="9cb0b-104">このエラーの部分を含む XML を表す、 **ErrorCollection**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="9cb0b-104">This error part contains XML representing an **ErrorCollection** object.</span></span> <span data-ttu-id="9cb0b-105">A4SWIFT の逆アセンブラーが表示されます、 **ErrorCollection**メッセージ処理 (解析、XML の検証とビジネス ルール エンジン (BRE) の検証) の各段階中のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="9cb0b-105">The A4SWIFT disassembler populates the **ErrorCollection** object during each stage of message processing (parsing, XML validation, and Business Rule Engine (BRE) validation).</span></span>  
  
 <span data-ttu-id="9cb0b-106">**ErrorCollection**オブジェクトのコレクションである*エラー オブジェクト*、メッセージ処理中に特定のエラーまたは失敗を表す各します。</span><span class="sxs-lookup"><span data-stu-id="9cb0b-106">The **ErrorCollection** object is a collection of *error objects*, each of which represents a particular error or failure during message processing.</span></span> <span data-ttu-id="9cb0b-107">個々 のエラー オブジェクトには、(メッセージとエラーの説明の場所) などの 1 つのエラーの詳細が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9cb0b-107">The individual error objects contain details about a single failure (such as the location in the message and a description of the failure).</span></span>  
  
 <span data-ttu-id="9cb0b-108">詳細については、 **ErrorCollection**アプリケーション プログラミング インターフェイス (API) と使用方法の詳細は、元のクラスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cb0b-108">For more information about the **ErrorCollection** application programming interface (API) and usage details, see ErrorCollection Class.</span></span> <span data-ttu-id="9cb0b-109">個々 のエラー オブジェクトの詳細については、ErrorBase クラス (エラー オブジェクトの基本クラス)、BreValidationError クラス、ParseError クラス、および XmlValidationError クラスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cb0b-109">For more information about individual error objects, see ErrorBase Class (the base class for error objects), BreValidationError Class, ParseError Class, and XmlValidationError Class.</span></span>  
  
 <span data-ttu-id="9cb0b-110">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9cb0b-110">This section contains:</span></span>  
  
-   [<span data-ttu-id="9cb0b-111">キャプチャおよびメッセージ修復のソリューションの機能拡張</span><span class="sxs-lookup"><span data-stu-id="9cb0b-111">Extending the Solution for Capture and Message Repair</span></span>](../../adapters-and-accelerators/accelerator-swift/extending-the-solution-for-capture-and-message-repair.md)