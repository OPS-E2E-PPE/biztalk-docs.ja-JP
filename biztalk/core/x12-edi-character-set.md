---
title: X12 EDI 文字セット |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76e7b327-b0bd-4f16-8bfe-6c0184059f2b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9bd501c81b92f4fa7824009a949fd6c7e58eaf3b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023104"
---
# <a name="x12-edi-character-set"></a><span data-ttu-id="13d99-102">X12 EDI 文字セット</span><span class="sxs-lookup"><span data-stu-id="13d99-102">X12 EDI Character Set</span></span>
<span data-ttu-id="13d99-103">& #Xd1; という文字またはアクサン グラーブ (') を使用する場合は、次のことを指定します。</span><span class="sxs-lookup"><span data-stu-id="13d99-103">When using the Ñ character or a grave accent (\`), specify the following:</span></span>  


|                                                                   |                                  <span data-ttu-id="13d99-104">文字セット</span><span class="sxs-lookup"><span data-stu-id="13d99-104">Character Set</span></span>                                   |
|-------------------------------------------------------------------|----------------------------------------------------------------------------------|
|             <span data-ttu-id="13d99-105">EDI ドキュメント内の & #xd1; という文字のみ</span><span class="sxs-lookup"><span data-stu-id="13d99-105">Only the Ñ character in the EDI document</span></span>              |                            <span data-ttu-id="13d99-106">拡張文字セットを使用します</span><span class="sxs-lookup"><span data-stu-id="13d99-106">Use Extended Character Set</span></span>                            |
|           <span data-ttu-id="13d99-107">のみの抑音アクセント (\`) で、EDI ドキュメント</span><span class="sxs-lookup"><span data-stu-id="13d99-107">Only a grave accent (\`) in the EDI document</span></span>            |                              <span data-ttu-id="13d99-108">UTF8 文字セットの使用</span><span class="sxs-lookup"><span data-stu-id="13d99-108">Use UTF8 Character Set</span></span>                              |
| <span data-ttu-id="13d99-109">& #Xd1; という文字**と**アクサン グラーブ (\`)、同じドキュメント内。</span><span class="sxs-lookup"><span data-stu-id="13d99-109">The Ñ character **and** a grave accent (\`) in the same document:</span></span> | <span data-ttu-id="13d99-110">-UTF8 エンコード受信ドキュメントである必要があります。</span><span class="sxs-lookup"><span data-stu-id="13d99-110">-   The inbound document must have UTF8 encoding</span></span><br /><span data-ttu-id="13d99-111">-UTF8 文字セットを使用します。</span><span class="sxs-lookup"><span data-stu-id="13d99-111">-   Use UTF8 Character Set</span></span> |

 <span data-ttu-id="13d99-112">EDI 文字セットの詳細については、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="13d99-112">The following links provider more information on EDI Character Sets:</span></span>  

 [<span data-ttu-id="13d99-113">EDI 文字セット</span><span class="sxs-lookup"><span data-stu-id="13d99-113">EDI Character Sets</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=271249)  

 [<span data-ttu-id="13d99-114">EDI 文字セットのサポート</span><span class="sxs-lookup"><span data-stu-id="13d99-114">EDI Character Set Support</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=271250)