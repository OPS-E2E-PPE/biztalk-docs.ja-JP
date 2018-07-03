---
title: SWIFT スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SWIFT, SWIFT messages
- schemas, SWIFT
- SWIFT messages, SWIFT schemas
- SWIFT, schemas
ms.assetid: 53017a56-a718-4577-a08c-9c92d9a54e7a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f749a06c694007008f3d8138b2b087b77b2c4f03
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996115"
---
# <a name="swift-schemas"></a><span data-ttu-id="816ec-102">SWIFT スキーマ</span><span class="sxs-lookup"><span data-stu-id="816ec-102">SWIFT Schemas</span></span>
[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]<span data-ttu-id="816ec-103"> 送信し、SWIFT ネットワーク経由で個々 のフラット ファイルとして SWIFT の財務 (FIN) メッセージを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="816ec-103"> sends and receives SWIFT financial (FIN) messages as individual flat files over the SWIFT network.</span></span> <span data-ttu-id="816ec-104">各メッセージは、一連のヘッダーのブロックの定義済みの一連のラベル付きのフィールドと位置指定または順序付きのサブフィールドとトレーラーのブロック内でトレーラーのセットから成るテキスト ブロックで構成されます。</span><span class="sxs-lookup"><span data-stu-id="816ec-104">Each individual message consists of a set of header blocks, a text block made up of a predefined set of labeled fields and positional or ordered subfields, and a set of trailers inside a trailer block.</span></span> <span data-ttu-id="816ec-105">テキスト ブロックの内容は、メッセージの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="816ec-105">The content of the text block varies by message type.</span></span>  
  
 <span data-ttu-id="816ec-106">SWIFT の財務 (FIN) メッセージのバッチを交換する多くのアプリケーションもあります: 1 つのファイルに含まれるメッセージのセット。</span><span class="sxs-lookup"><span data-stu-id="816ec-106">There are also many applications, which exchange batches of SWIFT financial (FIN) messages—a set of messages contained in a single file.</span></span> <span data-ttu-id="816ec-107">ファイルがローカルに配信される可能性がありますまたは FileAct を介して送信される可能性があります (SWIFT IP ネットワーク経由で — SIPN)、または FTP を使用します。</span><span class="sxs-lookup"><span data-stu-id="816ec-107">The file may be delivered locally or may be transmitted through FileAct (over the SWIFT IP Network—SIPN), or through FTP.</span></span>  
  
 <span data-ttu-id="816ec-108">データの操作を簡略化するに関連付けられているバッチ処理や、個別に送信されるのかどうかに関係なく、これらのメッセージ Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]各メッセージの種類を定義する XSD スキーマを提供します。</span><span class="sxs-lookup"><span data-stu-id="816ec-108">To simplify the manipulation of the data associated with these messages, regardless of whether they are batched or submitted individually, Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] provides an XSD schema defining each message type.</span></span> <span data-ttu-id="816ec-109">このスキーマは、メッセージを適切なスキーマに自動的に関連付けられているし、XML との間は、SWIFT ネットワークで使用される、外部のフラット ファイル表記の間で自動的に変換できるように、メッセージの種類を昇格させます。</span><span class="sxs-lookup"><span data-stu-id="816ec-109">This schema promotes the message type so that messages can be automatically associated with the proper schema, and automatically transformed between the external flat file representation, used by the SWIFT network, to and from XML.</span></span>  
  
 <span data-ttu-id="816ec-110">スキーマには、すべてのヘッダー、テキスト、およびトレーラーを含むブロックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="816ec-110">The schema includes all of the blocks including headers, text, and trailers.</span></span> <span data-ttu-id="816ec-111">このスキーマは、総合的なのに十分な FIN メッセージ レベルのプロトコルを使用して行う SWIFT ネットワーク経由でメッセージを送信して、すべての SWIFT ネットワーク経由で受信したメッセージに関連付けられた情報を格納するために、インターチェンジのスキーマは。</span><span class="sxs-lookup"><span data-stu-id="816ec-111">This schema is an interchange schema, because it is comprehensive enough to transmit messages over the SWIFT network using the FIN message-level protocols, and to contain all of the information associated with a message received through the SWIFT network.</span></span>  
  
 <span data-ttu-id="816ec-112">各メッセージの種類のスキーマは、全体的な形式とそのメッセージの種類のコンテキストを定義します。</span><span class="sxs-lookup"><span data-stu-id="816ec-112">The schema for each message type defines the overall format and context of that message type.</span></span> <span data-ttu-id="816ec-113">A4SWIFT では、各ブロックを定義します。</span><span class="sxs-lookup"><span data-stu-id="816ec-113">A4SWIFT defines each block.</span></span> <span data-ttu-id="816ec-114">各ブロック内では、フィールドとサブフィールド配置されます。必要に応じて、フィールドとサブフィールドが個別のスキーマで定義されている一般的な基本または複合型から構築されます。</span><span class="sxs-lookup"><span data-stu-id="816ec-114">Inside each block, the fields and subfields are laid out. As appropriate, the fields and subfields are built from common base or complex types, defined in separate schemas.</span></span> <span data-ttu-id="816ec-115">スキーマ レベルの検証には、形式、文字セット、設定値、範囲、必須/任意、再現性、位置、および必要に応じて、長さが含まれています。</span><span class="sxs-lookup"><span data-stu-id="816ec-115">Schema-level validation includes format, character set, value set, range, required/optional, repeatability, position, and length, as appropriate.</span></span> <span data-ttu-id="816ec-116">ビジネス ルールでは、クロス フィールド検証やその他の論理チェックを実行します。</span><span class="sxs-lookup"><span data-stu-id="816ec-116">The business rules perform cross-field validations and other logical checks.</span></span>  
  
 <span data-ttu-id="816ec-117">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="816ec-117">This section contains:</span></span>  
  
-   [<span data-ttu-id="816ec-118">サンプル メッセージ プレゼンテーション</span><span class="sxs-lookup"><span data-stu-id="816ec-118">Sample Message Presentation</span></span>](../../adapters-and-accelerators/accelerator-swift/sample-message-presentation.md)  
  
-   [<span data-ttu-id="816ec-119">サンプル スキーマ プレゼンテーション</span><span class="sxs-lookup"><span data-stu-id="816ec-119">Sample Schema Presentation</span></span>](../../adapters-and-accelerators/accelerator-swift/sample-schema-presentation.md)  
  
-   [<span data-ttu-id="816ec-120">SWIFT ヘッダー</span><span class="sxs-lookup"><span data-stu-id="816ec-120">SWIFT Headers</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-headers.md)  
  
-   [<span data-ttu-id="816ec-121">SWIFT テキスト</span><span class="sxs-lookup"><span data-stu-id="816ec-121">SWIFT Text</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-text.md)  
  
-   [<span data-ttu-id="816ec-122">SWIFT トレーラー</span><span class="sxs-lookup"><span data-stu-id="816ec-122">SWIFT Trailers</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-trailers.md)  
  
-   [<span data-ttu-id="816ec-123">SWIFT メッセージ規格の更新</span><span class="sxs-lookup"><span data-stu-id="816ec-123">Updating SWIFT Message Standards</span></span>](../../adapters-and-accelerators/accelerator-swift/updating-swift-messaging-standards.md)