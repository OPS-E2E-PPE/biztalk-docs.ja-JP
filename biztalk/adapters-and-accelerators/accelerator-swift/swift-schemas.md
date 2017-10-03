---
title: "SWIFT スキーマ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SWIFT, SWIFT messages
- schemas, SWIFT
- SWIFT messages, SWIFT schemas
- SWIFT, schemas
ms.assetid: 53017a56-a718-4577-a08c-9c92d9a54e7a
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b4bac26d99fb3282650c20381bbc18237f8908a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="swift-schemas"></a><span data-ttu-id="711f4-102">SWIFT スキーマ</span><span class="sxs-lookup"><span data-stu-id="711f4-102">SWIFT Schemas</span></span>
[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]<span data-ttu-id="711f4-103">送信し、非常に高速ネットワーク経由で個々 のフラット ファイルとして SWIFT の財務 (FIN) メッセージを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="711f4-103"> sends and receives SWIFT financial (FIN) messages as individual flat files over the SWIFT network.</span></span> <span data-ttu-id="711f4-104">各メッセージは、定義済みの一連のラベルの付いたフィールドと位置指定引数または順序付けられたサブフィールド、およびトレーラーをトレーラ ブロック内の一連の構成のテキスト ブロック ヘッダー ブロックのセットで構成されます。</span><span class="sxs-lookup"><span data-stu-id="711f4-104">Each individual message consists of a set of header blocks, a text block made up of a predefined set of labeled fields and positional or ordered subfields, and a set of trailers inside a trailer block.</span></span> <span data-ttu-id="711f4-105">テキスト ブロックの内容は、メッセージの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="711f4-105">The content of the text block varies by message type.</span></span>  
  
 <span data-ttu-id="711f4-106">SWIFT の財務 (FIN) メッセージのバッチを交換する多くのアプリケーションもあります: 1 つのファイルに含まれるメッセージのセット。</span><span class="sxs-lookup"><span data-stu-id="711f4-106">There are also many applications, which exchange batches of SWIFT financial (FIN) messages—a set of messages contained in a single file.</span></span> <span data-ttu-id="711f4-107">ファイルがローカルで配信される可能性がありますか、FileAct を介して送信される可能性があります (SWIFT IP ネットワーク経由で — SIPN)、または FTP を使用します。</span><span class="sxs-lookup"><span data-stu-id="711f4-107">The file may be delivered locally or may be transmitted through FileAct (over the SWIFT IP Network—SIPN), or through FTP.</span></span>  
  
 <span data-ttu-id="711f4-108">バッチ処理や、個別に送信されるのかどうかに関係なく、これらのメッセージに関連付けられているデータの操作を簡単に[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]各メッセージの種類を定義する XSD スキーマを提供します。</span><span class="sxs-lookup"><span data-stu-id="711f4-108">To simplify the manipulation of the data associated with these messages, regardless of whether they are batched or submitted individually, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] provides an XSD schema defining each message type.</span></span> <span data-ttu-id="711f4-109">このスキーマは、メッセージを適切なスキーマに自動的に関連付けられているし、SWIFT ネットワークは、XML との間で使用される、外部のフラット ファイル表記の間で自動的に変換できるように、メッセージの種類を昇格させます。</span><span class="sxs-lookup"><span data-stu-id="711f4-109">This schema promotes the message type so that messages can be automatically associated with the proper schema, and automatically transformed between the external flat file representation, used by the SWIFT network, to and from XML.</span></span>  
  
 <span data-ttu-id="711f4-110">スキーマには、すべてのヘッダー、テキスト、およびトレーラーを含むブロックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="711f4-110">The schema includes all of the blocks including headers, text, and trailers.</span></span> <span data-ttu-id="711f4-111">このスキーマは、十分に総合的 FIN メッセージ レベルのプロトコルを使用して、SWIFT ネットワーク経由でメッセージを送信して、すべての SWIFT ネットワーク経由で受信したメッセージに関連付けられている情報を格納するために、インターチェンジのスキーマはします。</span><span class="sxs-lookup"><span data-stu-id="711f4-111">This schema is an interchange schema, because it is comprehensive enough to transmit messages over the SWIFT network using the FIN message-level protocols, and to contain all of the information associated with a message received through the SWIFT network.</span></span>  
  
 <span data-ttu-id="711f4-112">各メッセージの種類のスキーマは、全体的な形式とそのメッセージの種類のコンテキストを定義します。</span><span class="sxs-lookup"><span data-stu-id="711f4-112">The schema for each message type defines the overall format and context of that message type.</span></span> <span data-ttu-id="711f4-113">A4SWIFT では、各ブロックを定義します。</span><span class="sxs-lookup"><span data-stu-id="711f4-113">A4SWIFT defines each block.</span></span> <span data-ttu-id="711f4-114">各ブロック内のフィールドおよびサブフィールド レイアウトされます。必要に応じて、フィールドおよびサブフィールドが別のスキーマで定義されている一般的な基本または複合型から構築されます。</span><span class="sxs-lookup"><span data-stu-id="711f4-114">Inside each block, the fields and subfields are laid out. As appropriate, the fields and subfields are built from common base or complex types, defined in separate schemas.</span></span> <span data-ttu-id="711f4-115">スキーマ レベルの検証には、形式、文字セット、設定値、範囲、必須/オプション、再現性、位置、および必要に応じて、長さが含まれています。</span><span class="sxs-lookup"><span data-stu-id="711f4-115">Schema-level validation includes format, character set, value set, range, required/optional, repeatability, position, and length, as appropriate.</span></span> <span data-ttu-id="711f4-116">ビジネス ルールは、クロス フィールド検証およびその他の論理チェックを実行します。</span><span class="sxs-lookup"><span data-stu-id="711f4-116">The business rules perform cross-field validations and other logical checks.</span></span>  
  
 <span data-ttu-id="711f4-117">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="711f4-117">This section contains:</span></span>  
  
-   [<span data-ttu-id="711f4-118">サンプル メッセージ プレゼンテーション</span><span class="sxs-lookup"><span data-stu-id="711f4-118">Sample Message Presentation</span></span>](../../adapters-and-accelerators/accelerator-swift/sample-message-presentation.md)  
  
-   [<span data-ttu-id="711f4-119">サンプル スキーマ プレゼンテーション</span><span class="sxs-lookup"><span data-stu-id="711f4-119">Sample Schema Presentation</span></span>](../../adapters-and-accelerators/accelerator-swift/sample-schema-presentation.md)  
  
-   [<span data-ttu-id="711f4-120">SWIFT ヘッダー</span><span class="sxs-lookup"><span data-stu-id="711f4-120">SWIFT Headers</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-headers.md)  
  
-   [<span data-ttu-id="711f4-121">SWIFT テキスト</span><span class="sxs-lookup"><span data-stu-id="711f4-121">SWIFT Text</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-text.md)  
  
-   [<span data-ttu-id="711f4-122">SWIFT は、トレーラー</span><span class="sxs-lookup"><span data-stu-id="711f4-122">SWIFT Trailers</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-trailers.md)  
  
-   [<span data-ttu-id="711f4-123">SWIFT メッセージ標準を更新</span><span class="sxs-lookup"><span data-stu-id="711f4-123">Updating SWIFT Message Standards</span></span>](../../adapters-and-accelerators/accelerator-swift/updating-swift-messaging-standards.md)