---
title: SWIFT トレーラー |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SWIFT Trailer schema
- schemas, SWIFT
- trailers [SWIFT]
- SWIFT, trailers
ms.assetid: b6d64584-0514-4c87-98c0-33755efc4695
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc3155ac21f55e7c61483b9287429f9b722f6a84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214498"
---
# <a name="swift-trailers"></a><span data-ttu-id="9283f-102">SWIFT は、トレーラー</span><span class="sxs-lookup"><span data-stu-id="9283f-102">SWIFT Trailers</span></span>
<span data-ttu-id="9283f-103">各 SWIFT メッセージは、メッセージ交換とセキュリティ要件に必要な 1 つまたは複数のトレーラーがします。</span><span class="sxs-lookup"><span data-stu-id="9283f-103">Each SWIFT message has one or more trailers as required by the message exchange and security requirements.</span></span> <span data-ttu-id="9283f-104">システム トレーラー、該当する場合、ユーザーのトレーラーに従います。</span><span class="sxs-lookup"><span data-stu-id="9283f-104">System trailers, if applicable, follow user trailers.</span></span> <span data-ttu-id="9283f-105">各トレーラーをトレーラ ブロック内では、中かっこのペアをこれ以上で区切られたサブブロック内が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9283f-105">Each trailer within the Trailer Block appears within a subblock delimited by further pairs of curly brackets.</span></span> <span data-ttu-id="9283f-106">各サブブロック後にコロンをトレーラ型を表す 3 文字から始まります。</span><span class="sxs-lookup"><span data-stu-id="9283f-106">Each subblock begins with three letters denoting the trailer type, followed by a colon.</span></span>  
  
 <span data-ttu-id="9283f-107">SWIFT トレーラー スキーマ (SWIFT Trailer.xsd) には、次の形式が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9283f-107">The SWIFT Trailer schema (SWIFT Trailer.xsd) contains the format for the following:</span></span>  
  
-   <span data-ttu-id="9283f-108">テキスト ブロックの終了区切り記号</span><span class="sxs-lookup"><span data-stu-id="9283f-108">The ending delimiter of the text block</span></span>  
  
-   <span data-ttu-id="9283f-109">ユーザーのトレーラー (ユーザーおよびシステム情報)</span><span class="sxs-lookup"><span data-stu-id="9283f-109">User trailers (user and system information)</span></span>  
  
-   <span data-ttu-id="9283f-110">システムのトレーラー</span><span class="sxs-lookup"><span data-stu-id="9283f-110">System trailers</span></span>  
  
 <span data-ttu-id="9283f-111">テキスト ブロックの終了区切り記号は、「-」} です。</span><span class="sxs-lookup"><span data-stu-id="9283f-111">The ending delimiter of the Text Block is "-}".</span></span> <span data-ttu-id="9283f-112">トレーラー ブロックが始まる"{5:"です。</span><span class="sxs-lookup"><span data-stu-id="9283f-112">The trailer block begins with "{5:".</span></span> <span data-ttu-id="9283f-113">トレーラーのブロックの内容には、ユーザー情報 (チェックサム、メッセージの認証、独自の認証およびなど) とシステム情報 (遅延メッセージ、メッセージの参照を使用可能な重複するメッセージ、およびなど) の両方が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9283f-113">The contents of the trailer block include both user information (checksum, message authentication, proprietary authentication, and so on), and system information (delayed message, message reference, possible duplicate message, and so on).</span></span> <span data-ttu-id="9283f-114">SWIFT によって追加されたトレーラーで区切られた 3 番目のブロックを提供も"{s:"です。</span><span class="sxs-lookup"><span data-stu-id="9283f-114">Trailers added by SWIFT also provide a third block, delimited by "{S:".</span></span> <span data-ttu-id="9283f-115">*SWIFT ユーザー マニュアル*、「FIN サービスの説明」のトピックで詳しく 5 ブロックの内容について説明します。</span><span class="sxs-lookup"><span data-stu-id="9283f-115">The *SWIFT User Handbook*, "FIN Service Description" topic, describes in detail the contents of block 5.</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="9283f-116">%s のブロックの内容を検証できません。</span><span class="sxs-lookup"><span data-stu-id="9283f-116"> does not validate the contents of block S.</span></span>  
  
 <span data-ttu-id="9283f-117">実際、FIN インターフェイスまたは SWIFT ネットワークは、トレーラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="9283f-117">The actual FIN interface or the SWIFT network appends the trailers.</span></span> <span data-ttu-id="9283f-118">メッセージにトレーラーが含まれている場合と[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]はメッセージを受信[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]メッセージにトレーラーを実行します。</span><span class="sxs-lookup"><span data-stu-id="9283f-118">If a message contains a trailer when [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] receives the message, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] carries the trailer with the message.</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="9283f-119">メッセージにトレーラーが含まれていない場合、エラーを生成しない場合に[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="9283f-119"> does not raise an error if a message does not contain a trailer when [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] receives the message.</span></span> <span data-ttu-id="9283f-120">として、ヘッダー付き自体のブロックを含む、トレーラーのエントリはすべてオプションで[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="9283f-120">As with headers, all of the trailer entries, including the blocks themselves, are optional in [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span>  
  
 <span data-ttu-id="9283f-121">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9283f-121">This section contains:</span></span>  
  
-   [<span data-ttu-id="9283f-122">ユーザーのトレーラー</span><span class="sxs-lookup"><span data-stu-id="9283f-122">User Trailers</span></span>](../../adapters-and-accelerators/accelerator-swift/user-trailers.md)  
  
-   [<span data-ttu-id="9283f-123">システムのトレーラー</span><span class="sxs-lookup"><span data-stu-id="9283f-123">System Trailers</span></span>](../../adapters-and-accelerators/accelerator-swift/system-trailers.md)  
  
## <a name="see-also"></a><span data-ttu-id="9283f-124">参照</span><span class="sxs-lookup"><span data-stu-id="9283f-124">See Also</span></span>  
 [<span data-ttu-id="9283f-125">スキーマの操作</span><span class="sxs-lookup"><span data-stu-id="9283f-125">Working with Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)