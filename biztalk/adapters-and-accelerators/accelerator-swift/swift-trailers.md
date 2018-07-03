---
title: SWIFT トレーラー |Microsoft Docs
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
ms.openlocfilehash: 1457c05b37c3f5b1dfcc5887c1a3f6ce27fcb0d4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004843"
---
# <a name="swift-trailers"></a><span data-ttu-id="a0c27-102">SWIFT トレーラー</span><span class="sxs-lookup"><span data-stu-id="a0c27-102">SWIFT Trailers</span></span>
<span data-ttu-id="a0c27-103">各 SWIFT のメッセージには、メッセージ交換とセキュリティ要件に必要な 1 つまたは複数のトレーラーがいます。</span><span class="sxs-lookup"><span data-stu-id="a0c27-103">Each SWIFT message has one or more trailers as required by the message exchange and security requirements.</span></span> <span data-ttu-id="a0c27-104">システム トレーラー、該当する場合、ユーザーのトレーラーに従います。</span><span class="sxs-lookup"><span data-stu-id="a0c27-104">System trailers, if applicable, follow user trailers.</span></span> <span data-ttu-id="a0c27-105">内で中かっこのペアをさらに区切られた subblock トレーラー ブロック内で各トレーラが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0c27-105">Each trailer within the Trailer Block appears within a subblock delimited by further pairs of curly brackets.</span></span> <span data-ttu-id="a0c27-106">各 subblock 後にコロン、トレーラーの型を表す 3 文字から始まります。</span><span class="sxs-lookup"><span data-stu-id="a0c27-106">Each subblock begins with three letters denoting the trailer type, followed by a colon.</span></span>  
  
 <span data-ttu-id="a0c27-107">SWIFT トレーラー スキーマ (SWIFT Trailer.xsd) には、次の形式が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a0c27-107">The SWIFT Trailer schema (SWIFT Trailer.xsd) contains the format for the following:</span></span>  
  
- <span data-ttu-id="a0c27-108">テキスト ブロックの終了区切り記号</span><span class="sxs-lookup"><span data-stu-id="a0c27-108">The ending delimiter of the text block</span></span>  
  
- <span data-ttu-id="a0c27-109">ユーザー トレーラー (ユーザーおよびシステム情報)</span><span class="sxs-lookup"><span data-stu-id="a0c27-109">User trailers (user and system information)</span></span>  
  
- <span data-ttu-id="a0c27-110">システム トレーラー</span><span class="sxs-lookup"><span data-stu-id="a0c27-110">System trailers</span></span>  
  
  <span data-ttu-id="a0c27-111">テキスト ブロックの終了区切り記号は、「-}」です。</span><span class="sxs-lookup"><span data-stu-id="a0c27-111">The ending delimiter of the Text Block is "-}".</span></span> <span data-ttu-id="a0c27-112">トレーラーのブロックが始まる"{5:"です。</span><span class="sxs-lookup"><span data-stu-id="a0c27-112">The trailer block begins with "{5:".</span></span> <span data-ttu-id="a0c27-113">トレーラーのブロックの内容には、ユーザー情報 (チェックサム、メッセージの認証、独自の認証およびなど) とシステム情報 (遅延メッセージ、メッセージの参照、使用可能な重複するメッセージ、およびなど) の両方が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a0c27-113">The contents of the trailer block include both user information (checksum, message authentication, proprietary authentication, and so on), and system information (delayed message, message reference, possible duplicate message, and so on).</span></span> <span data-ttu-id="a0c27-114">SWIFT によって追加されたトレーラーで区切られた、3 番目のブロックを提供も"{s:"です。</span><span class="sxs-lookup"><span data-stu-id="a0c27-114">Trailers added by SWIFT also provide a third block, delimited by "{S:".</span></span> <span data-ttu-id="a0c27-115">*SWIFT ユーザー向けハンドブック*、「FIN サービスの説明」のトピックで詳しく 5 ブロックの内容について説明します。</span><span class="sxs-lookup"><span data-stu-id="a0c27-115">The *SWIFT User Handbook*, "FIN Service Description" topic, describes in detail the contents of block 5.</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="a0c27-116"> %s のブロックの内容を検証できません。</span><span class="sxs-lookup"><span data-stu-id="a0c27-116"> does not validate the contents of block S.</span></span>  
  
  <span data-ttu-id="a0c27-117">実際、FIN インターフェイスまたは SWIFT ネットワークは、トレーラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="a0c27-117">The actual FIN interface or the SWIFT network appends the trailers.</span></span> <span data-ttu-id="a0c27-118">メッセージにトレーラーが含まれている場合と[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]メッセージを受信[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]メッセージ トレーラーを実行します。</span><span class="sxs-lookup"><span data-stu-id="a0c27-118">If a message contains a trailer when [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] receives the message, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] carries the trailer with the message.</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="a0c27-119"> メッセージにトレーラーが含まれていない場合、エラーは発生しないとき[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="a0c27-119"> does not raise an error if a message does not contain a trailer when [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] receives the message.</span></span> <span data-ttu-id="a0c27-120">として、ヘッダー付きのブロックをはじめ、トレーラーのエントリはすべてオプションで[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a0c27-120">As with headers, all of the trailer entries, including the blocks themselves, are optional in [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span>  
  
  <span data-ttu-id="a0c27-121">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a0c27-121">This section contains:</span></span>  
  
- [<span data-ttu-id="a0c27-122">ユーザー トレーラー</span><span class="sxs-lookup"><span data-stu-id="a0c27-122">User Trailers</span></span>](../../adapters-and-accelerators/accelerator-swift/user-trailers.md)  
  
- [<span data-ttu-id="a0c27-123">システム トレーラー</span><span class="sxs-lookup"><span data-stu-id="a0c27-123">System Trailers</span></span>](../../adapters-and-accelerators/accelerator-swift/system-trailers.md)  
  
## <a name="see-also"></a><span data-ttu-id="a0c27-124">参照</span><span class="sxs-lookup"><span data-stu-id="a0c27-124">See Also</span></span>  
 [<span data-ttu-id="a0c27-125">スキーマの操作</span><span class="sxs-lookup"><span data-stu-id="a0c27-125">Working with Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)