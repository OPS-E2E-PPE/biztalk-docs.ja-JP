---
title: カスタム XSLT |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- functoid types, Scripting
- maps, customizing
- functoid types, Looping
- maps, extending
- XSLT, maps
- Scripting functoids
- maps, XSLT
- customizing, maps
- maps, replacing
ms.assetid: e254d16d-4d16-4c23-a3ed-cc98eea9939a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4adf2abe438b3972419184b1297eaff5578c5bde
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238346"
---
# <a name="custom-xslt"></a><span data-ttu-id="de2f3-102">カスタム XSLT</span><span class="sxs-lookup"><span data-stu-id="de2f3-102">Custom XSLT</span></span>
<span data-ttu-id="de2f3-103">XSLT (Extensible Stylesheet Language Transformations) コードに関する知識がある場合、このコードを使用して、BizTalk マップのカスタマイズ、拡張、または置換を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="de2f3-103">If you are familiar with Extensible Stylesheet Language Transformations (XSLT) code, you can use it to customize, extend, or replace BizTalk maps.</span></span> <span data-ttu-id="de2f3-104">XSLT を使用する最も簡単な方法は、**スクリプト**functoid です。</span><span class="sxs-lookup"><span data-stu-id="de2f3-104">The simplest way to use XSLT is with the **Scripting** functoid.</span></span> <span data-ttu-id="de2f3-105">**スクリプト**functoid は多くのスクリプトを受け取ります。NET 対応言語、XSLT を含むです。</span><span class="sxs-lookup"><span data-stu-id="de2f3-105">The **Scripting** functoid accepts scripts in many .NET-enabled languages, including XSLT.</span></span> <span data-ttu-id="de2f3-106">XSLT を使用しての詳細については、**スクリプト**functoid を参照してください[スクリプトを使用してインラインの XSLT および XSLT 呼び出しテンプレート](../core/scripting-using-inline-xslt-and-xslt-call-templates.md)です。</span><span class="sxs-lookup"><span data-stu-id="de2f3-106">For more information about using XSLT with the **Scripting** functoid, see [Scripting Using Inline XSLT and XSLT Call Templates](../core/scripting-using-inline-xslt-and-xslt-call-templates.md).</span></span>  
  
 <span data-ttu-id="de2f3-107">あるインスタンス メッセージを別のインスタンス メッセージに変換するために XSLT コードを使用している場合、BizTalk マップの代わりに、直接このコードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="de2f3-107">If you have XSLT code that you have been using to convert one instance message into another, you can use that code directly in place of a BizTalk map.</span></span> <span data-ttu-id="de2f3-108">XSLT コード マップを BizTalk を置き換えることについてを参照してください[マップなしのマップを作成する方法](../core/how-to-create-a-map-without-maps.md)です。</span><span class="sxs-lookup"><span data-stu-id="de2f3-108">For information about replacing BizTalk maps with your XSLT code, see [How to Create a Map without Maps](../core/how-to-create-a-map-without-maps.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de2f3-109">参照</span><span class="sxs-lookup"><span data-stu-id="de2f3-109">See Also</span></span>  
 <span data-ttu-id="de2f3-110">[マップ](../core/maps.md) </span><span class="sxs-lookup"><span data-stu-id="de2f3-110">[Maps](../core/maps.md) </span></span>  
 [<span data-ttu-id="de2f3-111">BizTalk マッパーを使用してマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="de2f3-111">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)