---
title: XML メッセージ エンベロープを入れ子になった |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e880cef1-4e73-4bce-a06e-8c4d23bc5a8c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b341930a30c8653cb2db378a24c6600f48de0891
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65263355"
---
# <a name="nested-xml-message-envelopes"></a><span data-ttu-id="ca4ce-102">入れ子になった XML メッセージ エンベロープ</span><span class="sxs-lookup"><span data-stu-id="ca4ce-102">Nested XML Message Envelopes</span></span>
<span data-ttu-id="ca4ce-103">複雑なドキュメント構造を作成する XML エンベロープを入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="ca4ce-103">XML envelopes can be nested to create complex document structures.</span></span> <span data-ttu-id="ca4ce-104">入れ子になった XML エンベロープに柔軟で canonical と呼ばれる 2 つの形式で発生します。</span><span class="sxs-lookup"><span data-stu-id="ca4ce-104">Nested XML envelopes can occur in two forms, known as flexible and canonical.</span></span> <span data-ttu-id="ca4ce-105">次の例では、エンベロープ ドキュメントをドキュメントおよびエンベロープ (太字で表示する) ことができますが表示される上位のエンベロープ内の同じレベルでの柔軟な形式を示します。</span><span class="sxs-lookup"><span data-stu-id="ca4ce-105">The following example shows the flexible form of enveloped documents, in which documents and envelopes (shown in bold type) can appear at the same level within an enclosing envelope.</span></span>  
  
```  
<envelope1>  
    <document1/>    <envelope2>  
        <document2/>  
        <document3/>  
    </envelope2>    <document4/>  
</envelope1>  
```  
  
 <span data-ttu-id="ca4ce-106">次の例では、最も内側のエンベロープ内の同じレベルに表示されるすべてのドキュメントのエンベロープのドキュメントの正規の形式に準拠している同様のインスタンス メッセージを示します。</span><span class="sxs-lookup"><span data-stu-id="ca4ce-106">The following example shows a similar instance message that conforms to the canonical form of enveloped documents, in which all documents appear at the same level within the innermost envelope.</span></span>  
  
```  
<envelope1>  
    <envelope2>  
        <document1/>  
        <document2/>  
        <document3/>  
        <document4/>  
    </envelope2>  
</envelope1>  
  
```  
  
 <span data-ttu-id="ca4ce-107">フォームの説明のいずれかで、インスタンス メッセージを指定する、XML 逆アセンブラーは document1、document2、document3、および document4 を生成を生成します。</span><span class="sxs-lookup"><span data-stu-id="ca4ce-107">Given an instance message in either of the forms described, the XML disassembler will produce document1, document2, document3, and document4.</span></span> <span data-ttu-id="ca4ce-108">これらのドキュメントのそれぞれのメッセージ コンテキストには、外側のエンベロープの各内で昇格させたプロパティと、対応するドキュメントから昇格されたプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ca4ce-108">The message context of each of these documents includes the properties promoted from the corresponding document as well as the properties promoted within each of the enclosing envelopes.</span></span> <span data-ttu-id="ca4ce-109">次の表に表示される昇格させたプロパティが両方、柔軟で標準的な例については、さまざまなエンベロープの最初の列で指定されたプロパティ昇格に基づきラップされていない各ドキュメントのメッセージ コンテキストに含めるとドキュメント。</span><span class="sxs-lookup"><span data-stu-id="ca4ce-109">The following table shows the promoted properties that will be include in the message context of each unwrapped documents for both the flexible and canonical examples, given the property promotions specified in the first column for the various envelopes and documents.</span></span>  
  
|<span data-ttu-id="ca4ce-110">指定したプロパティの昇格</span><span class="sxs-lookup"><span data-stu-id="ca4ce-110">Specified property promotions</span></span>|<span data-ttu-id="ca4ce-111">柔軟な例については、結果のメッセージ コンテキスト プロパティ</span><span class="sxs-lookup"><span data-stu-id="ca4ce-111">Resulting message context properties for flexible example</span></span>|<span data-ttu-id="ca4ce-112">標準的な例の結果のメッセージ コンテキスト プロパティ</span><span class="sxs-lookup"><span data-stu-id="ca4ce-112">Resulting message context properties for canonical example</span></span>|  
|-----------------------------------|---------------------------------------------------------------|----------------------------------------------------------------|  
|<span data-ttu-id="ca4ce-113">envelope1: p1</span><span class="sxs-lookup"><span data-stu-id="ca4ce-113">envelope1: p1</span></span><br /><br /> <span data-ttu-id="ca4ce-114">envelope2: p3</span><span class="sxs-lookup"><span data-stu-id="ca4ce-114">envelope2: p3</span></span><br /><br /> <span data-ttu-id="ca4ce-115">文書 1: p2</span><span class="sxs-lookup"><span data-stu-id="ca4ce-115">document1: p2</span></span><br /><br /> <span data-ttu-id="ca4ce-116">文書 2: p4 および p5</span><span class="sxs-lookup"><span data-stu-id="ca4ce-116">document2: p4 and p5</span></span><br /><br /> <span data-ttu-id="ca4ce-117">document3: no promotions</span><span class="sxs-lookup"><span data-stu-id="ca4ce-117">document3: no promotions</span></span><br /><br /> <span data-ttu-id="ca4ce-118">document4: no promotions</span><span class="sxs-lookup"><span data-stu-id="ca4ce-118">document4: no promotions</span></span>|<span data-ttu-id="ca4ce-119">文書 1: p1、p2</span><span class="sxs-lookup"><span data-stu-id="ca4ce-119">document1: p1, p2</span></span><br /><br /> <span data-ttu-id="ca4ce-120">文書 2: p1、p3、p4、p5</span><span class="sxs-lookup"><span data-stu-id="ca4ce-120">document2: p1, p3, p4, p5</span></span><br /><br /> <span data-ttu-id="ca4ce-121">document3: p1、p3</span><span class="sxs-lookup"><span data-stu-id="ca4ce-121">document3: p1, p3</span></span><br /><br /> <span data-ttu-id="ca4ce-122">document4 を生成: p1</span><span class="sxs-lookup"><span data-stu-id="ca4ce-122">document4: p1</span></span>|<span data-ttu-id="ca4ce-123">文書 1: p1、p2、p3</span><span class="sxs-lookup"><span data-stu-id="ca4ce-123">document1: p1, p2, p3</span></span><br /><br /> <span data-ttu-id="ca4ce-124">文書 2: p1、p3、p4、p5</span><span class="sxs-lookup"><span data-stu-id="ca4ce-124">document2: p1, p3, p4, p5</span></span><br /><br /> <span data-ttu-id="ca4ce-125">document3: p1、p3</span><span class="sxs-lookup"><span data-stu-id="ca4ce-125">document3: p1, p3</span></span><br /><br /> <span data-ttu-id="ca4ce-126">document4 を生成: p1、p3</span><span class="sxs-lookup"><span data-stu-id="ca4ce-126">document4: p1, p3</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ca4ce-127">参照</span><span class="sxs-lookup"><span data-stu-id="ca4ce-127">See Also</span></span>  
 <span data-ttu-id="ca4ce-128">[XML メッセージ エンベロープ](../core/xml-message-envelopes.md) </span><span class="sxs-lookup"><span data-stu-id="ca4ce-128">[XML Message Envelopes](../core/xml-message-envelopes.md) </span></span>  
 <span data-ttu-id="ca4ce-129">[XML メッセージの構造](../core/structure-of-an-xml-message.md) </span><span class="sxs-lookup"><span data-stu-id="ca4ce-129">[Structure of an XML Message](../core/structure-of-an-xml-message.md) </span></span>  
 [<span data-ttu-id="ca4ce-130">エンベロープ用スキーマの作成方法</span><span class="sxs-lookup"><span data-stu-id="ca4ce-130">How to Create Schemas for Envelopes</span></span>](../core/how-to-create-schemas-for-envelopes.md)