---
title: "XML メッセージ エンベロープを入れ子になった |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e880cef1-4e73-4bce-a06e-8c4d23bc5a8c
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46b0f505dd9ba7da71df1cb460f9c9a6610763d3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="nested-xml-message-envelopes"></a><span data-ttu-id="24a21-102">入れ子になった XML メッセージ エンベロープ</span><span class="sxs-lookup"><span data-stu-id="24a21-102">Nested XML Message Envelopes</span></span>
<span data-ttu-id="24a21-103">XML エンベロープを入れ子にすることによって、複雑なドキュメント構造を作成できます。</span><span class="sxs-lookup"><span data-stu-id="24a21-103">XML envelopes can be nested to create complex document structures.</span></span> <span data-ttu-id="24a21-104">入れ子になった XML エンベロープには、柔軟型と正規型の 2 つの形態があります。</span><span class="sxs-lookup"><span data-stu-id="24a21-104">Nested XML envelopes can occur in two forms, known as flexible and canonical.</span></span> <span data-ttu-id="24a21-105">次の例は、柔軟型のエンベロープ ドキュメントを示しています。ドキュメントおよびエンベロープ (太字部分) が上位のエンベロープ内の同じレベルに出現しています。</span><span class="sxs-lookup"><span data-stu-id="24a21-105">The following example shows the flexible form of enveloped documents, in which documents and envelopes (shown in bold type) can appear at the same level within an enclosing envelope.</span></span>  
  
```  
<envelope1>  
    <document1/>    <envelope2>  
        <document2/>  
        <document3/>  
    </envelope2>    <document4/>  
</envelope1>  
```  
  
 <span data-ttu-id="24a21-106">次の例は、正規型のエンベロープ ドキュメントに準拠した、同様のインスタンス メッセージを示しています。すべてのドキュメントが最下位のエンベロープ内の同じレベルに出現しています。</span><span class="sxs-lookup"><span data-stu-id="24a21-106">The following example shows a similar instance message that conforms to the canonical form of enveloped documents, in which all documents appear at the same level within the innermost envelope.</span></span>  
  
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
  
 <span data-ttu-id="24a21-107">XML 逆アセンブラーは、前述の 2 つの形態のインスタンス メッセージを受け取ると、いずれも document1、document2、document3、および document4 を生成します。</span><span class="sxs-lookup"><span data-stu-id="24a21-107">Given an instance message in either of the forms described, the XML disassembler will produce document1, document2, document3, and document4.</span></span> <span data-ttu-id="24a21-108">各ドキュメントのメッセージ コンテキストには、対応するドキュメントから昇格されたプロパティのほかに、上位の各エンベロープ内で昇格されたプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="24a21-108">The message context of each of these documents includes the properties promoted from the corresponding document as well as the properties promoted within each of the enclosing envelopes.</span></span> <span data-ttu-id="24a21-109">次の表は、昇格されるプロパティを示しています。これらのプロパティは、柔軟型および正規型の例で、各エンベロープおよびドキュメントの最初の列で指定されたプロパティ昇格に基づき、ラップ解除された各ドキュメントのメッセージ コンテキストに追加されます。</span><span class="sxs-lookup"><span data-stu-id="24a21-109">The following table shows the promoted properties that will be include in the message context of each unwrapped documents for both the flexible and canonical examples, given the property promotions specified in the first column for the various envelopes and documents.</span></span>  
  
|<span data-ttu-id="24a21-110">指定されたプロパティ昇格</span><span class="sxs-lookup"><span data-stu-id="24a21-110">Specified property promotions</span></span>|<span data-ttu-id="24a21-111">結果のメッセージ コンテキスト プロパティ (柔軟型の例)</span><span class="sxs-lookup"><span data-stu-id="24a21-111">Resulting message context properties for flexible example</span></span>|<span data-ttu-id="24a21-112">結果のメッセージ コンテキスト プロパティ (正規型の例)</span><span class="sxs-lookup"><span data-stu-id="24a21-112">Resulting message context properties for canonical example</span></span>|  
|-----------------------------------|---------------------------------------------------------------|----------------------------------------------------------------|  
|<span data-ttu-id="24a21-113">envelope1: p1</span><span class="sxs-lookup"><span data-stu-id="24a21-113">envelope1: p1</span></span><br /><br /> <span data-ttu-id="24a21-114">envelope2: p3</span><span class="sxs-lookup"><span data-stu-id="24a21-114">envelope2: p3</span></span><br /><br /> <span data-ttu-id="24a21-115">document1: p2</span><span class="sxs-lookup"><span data-stu-id="24a21-115">document1: p2</span></span><br /><br /> <span data-ttu-id="24a21-116">document2: p4 および p5</span><span class="sxs-lookup"><span data-stu-id="24a21-116">document2: p4 and p5</span></span><br /><br /> <span data-ttu-id="24a21-117">document3: プロモーションがありません</span><span class="sxs-lookup"><span data-stu-id="24a21-117">document3: no promotions</span></span><br /><br /> <span data-ttu-id="24a21-118">document4 を生成: プロモーションがありません</span><span class="sxs-lookup"><span data-stu-id="24a21-118">document4: no promotions</span></span>|<span data-ttu-id="24a21-119">document1: p1、p2</span><span class="sxs-lookup"><span data-stu-id="24a21-119">document1: p1, p2</span></span><br /><br /> <span data-ttu-id="24a21-120">document2: p1、p3、p4、p5</span><span class="sxs-lookup"><span data-stu-id="24a21-120">document2: p1, p3, p4, p5</span></span><br /><br /> <span data-ttu-id="24a21-121">document3: p1、p3</span><span class="sxs-lookup"><span data-stu-id="24a21-121">document3: p1, p3</span></span><br /><br /> <span data-ttu-id="24a21-122">document4 を生成: p1</span><span class="sxs-lookup"><span data-stu-id="24a21-122">document4: p1</span></span>|<span data-ttu-id="24a21-123">document1: p1、p2、p3</span><span class="sxs-lookup"><span data-stu-id="24a21-123">document1: p1, p2, p3</span></span><br /><br /> <span data-ttu-id="24a21-124">document2: p1、p3、p4、p5</span><span class="sxs-lookup"><span data-stu-id="24a21-124">document2: p1, p3, p4, p5</span></span><br /><br /> <span data-ttu-id="24a21-125">document3: p1、p3</span><span class="sxs-lookup"><span data-stu-id="24a21-125">document3: p1, p3</span></span><br /><br /> <span data-ttu-id="24a21-126">document4 を生成: p1、p3</span><span class="sxs-lookup"><span data-stu-id="24a21-126">document4: p1, p3</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="24a21-127">参照</span><span class="sxs-lookup"><span data-stu-id="24a21-127">See Also</span></span>  
 <span data-ttu-id="24a21-128">[XML メッセージ エンベロープ](../core/xml-message-envelopes.md) </span><span class="sxs-lookup"><span data-stu-id="24a21-128">[XML Message Envelopes](../core/xml-message-envelopes.md) </span></span>  
 <span data-ttu-id="24a21-129">[XML メッセージの構造](../core/structure-of-an-xml-message.md) </span><span class="sxs-lookup"><span data-stu-id="24a21-129">[Structure of an XML Message](../core/structure-of-an-xml-message.md) </span></span>  
 [<span data-ttu-id="24a21-130">エンベロープ用スキーマを作成する方法</span><span class="sxs-lookup"><span data-stu-id="24a21-130">How to Create Schemas for Envelopes</span></span>](../core/how-to-create-schemas-for-envelopes.md)