---
title: "サンプル メッセージ プレゼンテーション |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, SWIFT message block
- SWIFT messages, message block example
ms.assetid: 3136a7da-658d-4100-bbe5-2186ee8bafd1
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8a3d03e35f6184e6aed6ba4af71e01a9b65e342
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="sample-message-presentation"></a><span data-ttu-id="de38c-102">サンプル メッセージ プレゼンテーション</span><span class="sxs-lookup"><span data-stu-id="de38c-102">Sample Message Presentation</span></span>
<span data-ttu-id="de38c-103">次の表は、SWIFT メッセージのブロック レイアウトの例を示します。</span><span class="sxs-lookup"><span data-stu-id="de38c-103">The following table shows an example of the block layout of a SWIFT message.</span></span>  
  
|<span data-ttu-id="de38c-104">[ブロック]</span><span class="sxs-lookup"><span data-stu-id="de38c-104">Block</span></span>|<span data-ttu-id="de38c-105">例</span><span class="sxs-lookup"><span data-stu-id="de38c-105">Example</span></span>|  
|-----------|-------------|  
|<span data-ttu-id="de38c-106">**ブロック 1**基本的なヘッダー</span><span class="sxs-lookup"><span data-stu-id="de38c-106">**Block 1** Basic Header</span></span>|<span data-ttu-id="de38c-107">{1:F01BCITITMMAXXX0012000123}</span><span class="sxs-lookup"><span data-stu-id="de38c-107">{1:F01BCITITMMAXXX0012000123}</span></span>|  
|<span data-ttu-id="de38c-108">**ブロック 2** (I) (SWIFT) にアプリケーション ヘッダー入力</span><span class="sxs-lookup"><span data-stu-id="de38c-108">**Block 2** (I) Application Header Input (to SWIFT)</span></span><br /><br /> <span data-ttu-id="de38c-109">または</span><span class="sxs-lookup"><span data-stu-id="de38c-109">Or</span></span><br /><br /> <span data-ttu-id="de38c-110">**ブロック 2** (SWIFT) から (O) アプリケーション ヘッダーを出力</span><span class="sxs-lookup"><span data-stu-id="de38c-110">**Block 2** (O) Application Header Output (from SWIFT)</span></span>|<span data-ttu-id="de38c-111">{2:I103VBOEATWWXXXXN}または {2:O1030840010605BNPAFRPPAXXX00120078960106051051U3</span><span class="sxs-lookup"><span data-stu-id="de38c-111">{2:I103VBOEATWWXXXXN} Or {2:O1030840010605BNPAFRPPAXXX00120078960106051051U3</span></span>|  
|<span data-ttu-id="de38c-112">**ブロック 3**ユーザー ヘッダー</span><span class="sxs-lookup"><span data-stu-id="de38c-112">**Block 3** User Header</span></span>|<span data-ttu-id="de38c-113">{3: {108:BCITITMMA950906}}</span><span class="sxs-lookup"><span data-stu-id="de38c-113">{3:{108:BCITITMMA950906}}</span></span>|  
|<span data-ttu-id="de38c-114">**ブロック 4**テキスト</span><span class="sxs-lookup"><span data-stu-id="de38c-114">**Block 4** Text</span></span>|<span data-ttu-id="de38c-115">{4:\<CRLF\> : 20:1234567890\<CRLF\> : 23B:CRED\<CRLF\> : 32A:010605GBP45000、\<CRLF\> : 33B:GBP45000、\<CRLF\> : 50K:MASTERS インポート\<CRLF\> RUE DES ARBRES 119\<CRLF\> CAMBRAI\<CRLF\> : 52A:BNPAFRPPCAM\<CRLF\> : 53A:POCIITMM680\<CRLF\> : 57A:BCITITMM680\<CRLF\> : 59:/P03452032022819 30\<CRLF\>総計インポート\<CRLF\> PESCARA\<CRLF\> : 70: ドキュメントを RFB/INV 5591\<CRLF\> : 71A:SHA\<CRLF\> -}</span><span class="sxs-lookup"><span data-stu-id="de38c-115">{4:\<CRLF\> :20:1234567890\<CRLF\> :23B:CRED\<CRLF\> :32A:010605GBP45000,\<CRLF\> :33B:GBP45000,\<CRLF\> :50K:MASTERS IMPORT\<CRLF\> RUE DES ARBRES 119\<CRLF\> CAMBRAI\<CRLF\> :52A:BNPAFRPPCAM\<CRLF\> :53A:POCIITMM680\<CRLF\> :57A:BCITITMM680\<CRLF\> :59:/P03452032022819 30\<CRLF\> GRAND IMPORT\<CRLF\> PESCARA\<CRLF\> :70:/RFB/INV 5591\<CRLF\> :71A:SHA\<CRLF\> -}</span></span>|  
|<span data-ttu-id="de38c-116">**5 をブロック**トレーラー</span><span class="sxs-lookup"><span data-stu-id="de38c-116">**Block 5** Trailers</span></span>|<span data-ttu-id="de38c-117">{5: {MAC: 12345678} {CHK:123456789ABC}}</span><span class="sxs-lookup"><span data-stu-id="de38c-117">{5:{MAC:12345678}{CHK:123456789ABC}}</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="de38c-118">参照</span><span class="sxs-lookup"><span data-stu-id="de38c-118">See Also</span></span>  
 [<span data-ttu-id="de38c-119">SWIFT スキーマ</span><span class="sxs-lookup"><span data-stu-id="de38c-119">SWIFT Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-schemas.md)