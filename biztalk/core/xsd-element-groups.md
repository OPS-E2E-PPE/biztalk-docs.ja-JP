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
ms.openlocfilehash: 80b6fdd65067599ed14c37ff00507279ce9b2f47
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006691"
---
# <a name="xsd-element-groups"></a><span data-ttu-id="3bbed-102">XSD 要素グループ</span><span class="sxs-lookup"><span data-stu-id="3bbed-102">XSD Element Groups</span></span>
<span data-ttu-id="3bbed-103">スキーマに特定の構造を使用すると、BizTalk マッパーで生成される XSLT (Extensible Stylesheet Language Transformations) にバリエーションが生じる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3bbed-103">The use of certain structures in a schema may create variations in the Extensible Stylesheet Language Transformations (XSLT) that BizTalk Mapper generates.</span></span>  
  
 <span data-ttu-id="3bbed-104">その一例として、シーケンス、選択肢、または全要素グループを定義するスキーマをマップに含めるような場合が考えられます。</span><span class="sxs-lookup"><span data-stu-id="3bbed-104">This can occur when you include a schema in your map that defines sequence, choice, or all element groups.</span></span> <span data-ttu-id="3bbed-105">含むスキーマを使用する場合など、**グループの選択**ノードの子の 2 つ以上が必要なマップを作成することは、**グループの選択**ノードに表示される出力インスタンスメッセージ。</span><span class="sxs-lookup"><span data-stu-id="3bbed-105">For example, if you use a schema that includes a **Choice Group** node, it is possible for you to create a map that requires two or more of the children of the **Choice Group** node to appear in an output instance message.</span></span> <span data-ttu-id="3bbed-106">この場合、マップをコンパイルするときに、BizTalk マッパーから警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3bbed-106">In this case, BizTalk Mapper displays a warning when you compile the map.</span></span> <span data-ttu-id="3bbed-107">この警告は、実行時の親ループにおける同一の繰り返し処理では、マッピングされた必須フィールドのいずれか 1 つしか、値が挿入されない可能性があることを伝えるものです。</span><span class="sxs-lookup"><span data-stu-id="3bbed-107">The warning tells you that only one of the required fields you have mapped may be populated in the same iteration of the parent loop at run time.</span></span> <span data-ttu-id="3bbed-108">BizTalk マッパーでは、マッピングのロジックに誤りがあることを示すエラー メッセージは生成されません。</span><span class="sxs-lookup"><span data-stu-id="3bbed-108">BizTalk Mapper does not give you an error message stating that your mapping logic is incorrect.</span></span>  
  
 <span data-ttu-id="3bbed-109">他にも、次の条件が満たされた場合、XSLT にバリエーションが生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3bbed-109">Another situation in which you might generate variations in the XSLT is when the following conditions are met:</span></span>  
  
- <span data-ttu-id="3bbed-110">**レコード A**が子**フィールド要素 B**します。</span><span class="sxs-lookup"><span data-stu-id="3bbed-110">**Record A** has a child **Field Element B**.</span></span>  
  
- <span data-ttu-id="3bbed-111">**レコード A**と子**フィールド要素 B** 1 回出現します。</span><span class="sxs-lookup"><span data-stu-id="3bbed-111">**Record A** and child **Field Element B** occur once.</span></span>  
  
- <span data-ttu-id="3bbed-112">**レコード A**の一部である、**グループの選択**繰り返されています。</span><span class="sxs-lookup"><span data-stu-id="3bbed-112">**Record A** is part of a **Choice Group** that repeats.</span></span>  
  
  <span data-ttu-id="3bbed-113">このような場合、BizTalk マッパーは、送信元レコードの複数のバリエーションを処理するための繰り返しロジックを含んだ XSLT を生成します。</span><span class="sxs-lookup"><span data-stu-id="3bbed-113">In this situation, BizTalk Mapper generates XSLT that contains iteration logic to handle the possibility of the many variations of the source records.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3bbed-114">グループを含んだマッピングは、明示的に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3bbed-114">You must be explicit with respect to mappings involving groups.</span></span> <span data-ttu-id="3bbed-115">たとえば、送信先スキーマが含まれている場合、**グループの選択**A と B の子ノードを持つノード、ことはできませんと、親グループの同一の繰り返し処理で同時に B。</span><span class="sxs-lookup"><span data-stu-id="3bbed-115">For example, if a destination schema contains a **Choice Group** node with child nodes A and B, it is not valid to have A and B simultaneously on the same iteration of their parent group.</span></span> <span data-ttu-id="3bbed-116">BizTalk マッパーには、無効なマッピングの作成を回避するような機能はありません。</span><span class="sxs-lookup"><span data-stu-id="3bbed-116">BizTalk Mapper does not prevent you from creating mappings that are not valid.</span></span> <span data-ttu-id="3bbed-117">そのため、A と B が同時に現れることのできないような論理 Functoid を使用して、マッピングを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3bbed-117">Therefore, you must use logical functoids to set up mappings in which A and B can never occur at the same time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bbed-118">参照</span><span class="sxs-lookup"><span data-stu-id="3bbed-118">See Also</span></span>  
 <span data-ttu-id="3bbed-119">[マップ](../core/maps.md) </span><span class="sxs-lookup"><span data-stu-id="3bbed-119">[Maps](../core/maps.md) </span></span>  
 [<span data-ttu-id="3bbed-120">BizTalk マッパーを使用してマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="3bbed-120">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)