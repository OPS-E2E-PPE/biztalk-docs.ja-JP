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
ms.openlocfilehash: b6fb92d0b8a20e9ca4e1a71aead55af21b1daeea
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394782"
---
# <a name="x12-edi-character-set"></a><span data-ttu-id="2b761-102">X12 EDI 文字セット</span><span class="sxs-lookup"><span data-stu-id="2b761-102">X12 EDI Character Set</span></span>
<span data-ttu-id="2b761-103">&#Xd1; という文字またはアクサン グラーブ (') を使用する場合は、次のことを指定します。</span><span class="sxs-lookup"><span data-stu-id="2b761-103">When using the Ñ character or a grave accent (\`), specify the following:</span></span>  


|                                                                   |                                  <span data-ttu-id="2b761-104">文字セット</span><span class="sxs-lookup"><span data-stu-id="2b761-104">Character Set</span></span>                                   |
|-------------------------------------------------------------------|----------------------------------------------------------------------------------|
|             <span data-ttu-id="2b761-105">EDI ドキュメント内の &#xd1; という文字のみ</span><span class="sxs-lookup"><span data-stu-id="2b761-105">Only the Ñ character in the EDI document</span></span>              |                            <span data-ttu-id="2b761-106">拡張文字セットを使用します。</span><span class="sxs-lookup"><span data-stu-id="2b761-106">Use Extended Character Set</span></span>                            |
|           <span data-ttu-id="2b761-107">のみの抑音アクセント (\`)、EDI ドキュメントの |                             UTF8 文字セットを使用します。</span><span class="sxs-lookup"><span data-stu-id="2b761-107">Only a grave accent (\`) in the EDI document            |                              Use UTF8 Character Set</span></span>                              |
| <span data-ttu-id="2b761-108">& #Xd1; という文字**と**アクサン グラーブ (\`)、同じドキュメント内 |-UTF8 エンコード受信ドキュメントである必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b761-108">The Ñ character **and** a grave accent (\`) in the same document: | -   The inbound document must have UTF8 encoding</span></span><br /><span data-ttu-id="2b761-109">-UTF8 文字セットを使用します。</span><span class="sxs-lookup"><span data-stu-id="2b761-109">-   Use UTF8 Character Set</span></span> |

 <span data-ttu-id="2b761-110">次のリンク プロバイダー EDI 文字セットの詳細について。</span><span class="sxs-lookup"><span data-stu-id="2b761-110">The following links provider more information on EDI Character Sets:</span></span>  

 [<span data-ttu-id="2b761-111">EDI 文字セット</span><span class="sxs-lookup"><span data-stu-id="2b761-111">EDI Character Sets</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=271249)  

 [<span data-ttu-id="2b761-112">EDI 文字セットのサポート</span><span class="sxs-lookup"><span data-stu-id="2b761-112">EDI Character Set Support</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=271250)