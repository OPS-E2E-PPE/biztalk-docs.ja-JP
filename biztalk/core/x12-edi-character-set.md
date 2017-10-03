---
title: "X12 EDI 文字セット |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 76e7b327-b0bd-4f16-8bfe-6c0184059f2b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46bcf25317d38846c6376b1fa25572b926c92992
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="x12-edi-character-set"></a><span data-ttu-id="c04da-102">X12 EDI 文字セット</span><span class="sxs-lookup"><span data-stu-id="c04da-102">X12 EDI Character Set</span></span>
<span data-ttu-id="c04da-103">Ñ 文字または抑音アクセント (') を使用する場合は、次のことを指定します。</span><span class="sxs-lookup"><span data-stu-id="c04da-103">When using the Ñ character or a grave accent (\`), specify the following:</span></span>  
  
||<span data-ttu-id="c04da-104">文字セット</span><span class="sxs-lookup"><span data-stu-id="c04da-104">Character Set</span></span>|  
|-|-------------------|  
|<span data-ttu-id="c04da-105">EDI ドキュメント内の Ñ 文字のみ</span><span class="sxs-lookup"><span data-stu-id="c04da-105">Only the Ñ character in the EDI document</span></span>|<span data-ttu-id="c04da-106">拡張文字セットを使用します</span><span class="sxs-lookup"><span data-stu-id="c04da-106">Use Extended Character Set</span></span>|  
|<span data-ttu-id="c04da-107">EDI ドキュメント内の抑音アクセント (\`) のみ</span><span class="sxs-lookup"><span data-stu-id="c04da-107">Only a grave accent (\`) in the EDI document</span></span>|<span data-ttu-id="c04da-108">UTF8 文字セットの使用</span><span class="sxs-lookup"><span data-stu-id="c04da-108">Use UTF8 Character Set</span></span>|  
|<span data-ttu-id="c04da-109">Ñ 文字**と**同じドキュメント内の抑音アクセント (')。</span><span class="sxs-lookup"><span data-stu-id="c04da-109">The Ñ character **and** a grave accent (\`) in the same document:</span></span>|<span data-ttu-id="c04da-110">UTF8 エンコード-受信ドキュメントである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c04da-110">-   The inbound document must have UTF8 encoding</span></span><br /><span data-ttu-id="c04da-111">-UTF8 文字セットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c04da-111">-   Use UTF8 Character Set</span></span>|  
  
 <span data-ttu-id="c04da-112">EDI 文字セットの詳細については、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c04da-112">The following links provider more information on EDI Character Sets:</span></span>  
  
 [<span data-ttu-id="c04da-113">EDI 文字セット</span><span class="sxs-lookup"><span data-stu-id="c04da-113">EDI Character Sets</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=271249)  
  
 [<span data-ttu-id="c04da-114">EDI 文字セットのサポート</span><span class="sxs-lookup"><span data-stu-id="c04da-114">EDI Character Set Support</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=271250)