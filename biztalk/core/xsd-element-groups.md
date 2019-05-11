---
title: XSD 要素グループ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XSLT, XSLT variations
- BizTalk Mapper, XSLT variations
- maps, groups
- Choice Group node
- XSD element groups
- XSLT, warnings
ms.assetid: a6ea22cb-6066-480e-8a2a-75fade3e5970
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2090d300259949b8d5e26f2fa48cc416beba3ca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401543"
---
# <a name="xsd-element-groups"></a><span data-ttu-id="65c37-102">XSD 要素グループ</span><span class="sxs-lookup"><span data-stu-id="65c37-102">XSD Element Groups</span></span>
<span data-ttu-id="65c37-103">スキーマ内の特定の構造の使用で、XSLT Extensible Stylesheet Language Transformations () BizTalk マッパーによって生成されるバリエーションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="65c37-103">The use of certain structures in a schema may create variations in the Extensible Stylesheet Language Transformations (XSLT) that BizTalk Mapper generates.</span></span>  
  
 <span data-ttu-id="65c37-104">これは、シーケンス、choice、またはすべての要素グループを定義する、マップにスキーマを含める場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="65c37-104">This can occur when you include a schema in your map that defines sequence, choice, or all element groups.</span></span> <span data-ttu-id="65c37-105">含むスキーマを使用する場合など、**グループの選択**ノードの子の 2 つ以上が必要なマップを作成することは、**グループの選択**ノードに表示される出力インスタンスメッセージ。</span><span class="sxs-lookup"><span data-stu-id="65c37-105">For example, if you use a schema that includes a **Choice Group** node, it is possible for you to create a map that requires two or more of the children of the **Choice Group** node to appear in an output instance message.</span></span> <span data-ttu-id="65c37-106">この場合、BizTalk マッパーでは、マップをコンパイルするときに警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="65c37-106">In this case, BizTalk Mapper displays a warning when you compile the map.</span></span> <span data-ttu-id="65c37-107">この警告は、マップして、必要なフィールドの 1 つだけが実行時に同じ親ループのイテレーションで設定することを指示します。</span><span class="sxs-lookup"><span data-stu-id="65c37-107">The warning tells you that only one of the required fields you have mapped may be populated in the same iteration of the parent loop at run time.</span></span> <span data-ttu-id="65c37-108">BizTalk マッパーは提供されませんが、マッピングのロジックが正しいことを示すエラー メッセージ。</span><span class="sxs-lookup"><span data-stu-id="65c37-108">BizTalk Mapper does not give you an error message stating that your mapping logic is incorrect.</span></span>  
  
 <span data-ttu-id="65c37-109">別の状況では、XSLT にバリエーションを生成する可能性がありますは、次の条件が満たされたときに。</span><span class="sxs-lookup"><span data-stu-id="65c37-109">Another situation in which you might generate variations in the XSLT is when the following conditions are met:</span></span>  
  
- <span data-ttu-id="65c37-110">**レコード A**が子**フィールド要素 B**します。</span><span class="sxs-lookup"><span data-stu-id="65c37-110">**Record A** has a child **Field Element B**.</span></span>  
  
- <span data-ttu-id="65c37-111">**レコード A**と子**フィールド要素 B** 1 回出現します。</span><span class="sxs-lookup"><span data-stu-id="65c37-111">**Record A** and child **Field Element B** occur once.</span></span>  
  
- <span data-ttu-id="65c37-112">**レコード A**の一部である、**グループの選択**繰り返されています。</span><span class="sxs-lookup"><span data-stu-id="65c37-112">**Record A** is part of a **Choice Group** that repeats.</span></span>  
  
  <span data-ttu-id="65c37-113">このような状況では、BizTalk マッパーは、基になるレコードの多くのバリエーションの可能性を処理するために反復処理ロジックを含む XSLT を生成します。</span><span class="sxs-lookup"><span data-stu-id="65c37-113">In this situation, BizTalk Mapper generates XSLT that contains iteration logic to handle the possibility of the many variations of the source records.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="65c37-114">グループを含んだマッピング明示的に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65c37-114">You must be explicit with respect to mappings involving groups.</span></span> <span data-ttu-id="65c37-115">たとえば、送信先スキーマが含まれている場合、**グループの選択**A と B の子ノードを持つノード、ことはできませんと、親グループの同一の繰り返し処理で同時に B。</span><span class="sxs-lookup"><span data-stu-id="65c37-115">For example, if a destination schema contains a **Choice Group** node with child nodes A and B, it is not valid to have A and B simultaneously on the same iteration of their parent group.</span></span> <span data-ttu-id="65c37-116">BizTalk マッパーができない無効なマッピングを作成します。</span><span class="sxs-lookup"><span data-stu-id="65c37-116">BizTalk Mapper does not prevent you from creating mappings that are not valid.</span></span> <span data-ttu-id="65c37-117">そのため、論理演算 functoid を使用して、マッピングを A と B 決して発生する可能性が同時に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65c37-117">Therefore, you must use logical functoids to set up mappings in which A and B can never occur at the same time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65c37-118">参照</span><span class="sxs-lookup"><span data-stu-id="65c37-118">See Also</span></span>  
 <span data-ttu-id="65c37-119">[マップ](../core/maps.md) </span><span class="sxs-lookup"><span data-stu-id="65c37-119">[Maps](../core/maps.md) </span></span>  
 [<span data-ttu-id="65c37-120">BizTalk マッパーを使用してマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="65c37-120">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)