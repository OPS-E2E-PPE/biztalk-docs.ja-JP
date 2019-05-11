---
title: カスタム XSLT |Microsoft Docs
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
ms.openlocfilehash: e7ee93d5cd6deb2b7f5a9b291e6670741f301bd6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390038"
---
# <a name="custom-xslt"></a><span data-ttu-id="ba7b0-102">カスタム xslt は上書き</span><span class="sxs-lookup"><span data-stu-id="ba7b0-102">Custom XSLT</span></span>
<span data-ttu-id="ba7b0-103">拡張可能なスタイル シート言語変換 (XSLT) コードに慣れている場合は、カスタマイズ、拡張、または BizTalk マップを置換に使用できます。</span><span class="sxs-lookup"><span data-stu-id="ba7b0-103">If you are familiar with Extensible Stylesheet Language Transformations (XSLT) code, you can use it to customize, extend, or replace BizTalk maps.</span></span> <span data-ttu-id="ba7b0-104">XSLT を使用する最も簡単な方法は、 **Scripting** functoid。</span><span class="sxs-lookup"><span data-stu-id="ba7b0-104">The simplest way to use XSLT is with the **Scripting** functoid.</span></span> <span data-ttu-id="ba7b0-105">**Scripting** functoid は多くのスクリプトを受け取ります。NET が有効な言語、XSLT を含むです。</span><span class="sxs-lookup"><span data-stu-id="ba7b0-105">The **Scripting** functoid accepts scripts in many .NET-enabled languages, including XSLT.</span></span> <span data-ttu-id="ba7b0-106">XSLT を使用しての詳細については、 **Scripting** functoid を参照してください[スクリプトを使用してインラインの XSLT および XSLT 呼び出しテンプレート](../core/scripting-using-inline-xslt-and-xslt-call-templates.md)します。</span><span class="sxs-lookup"><span data-stu-id="ba7b0-106">For more information about using XSLT with the **Scripting** functoid, see [Scripting Using Inline XSLT and XSLT Call Templates](../core/scripting-using-inline-xslt-and-xslt-call-templates.md).</span></span>  
  
 <span data-ttu-id="ba7b0-107">使用して別に 1 つのインスタンス メッセージを変換する XSLT コードがある場合は、BizTalk マップの代わりに直接コードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ba7b0-107">If you have XSLT code that you have been using to convert one instance message into another, you can use that code directly in place of a BizTalk map.</span></span> <span data-ttu-id="ba7b0-108">XSLT コード マップを BizTalk を置き換えることについては、参照してください[マップを使用しないでマップを作成する方法](../core/how-to-create-a-map-without-maps.md)します。</span><span class="sxs-lookup"><span data-stu-id="ba7b0-108">For information about replacing BizTalk maps with your XSLT code, see [How to Create a Map without Maps](../core/how-to-create-a-map-without-maps.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba7b0-109">参照</span><span class="sxs-lookup"><span data-stu-id="ba7b0-109">See Also</span></span>  
 <span data-ttu-id="ba7b0-110">[マップ](../core/maps.md) </span><span class="sxs-lookup"><span data-stu-id="ba7b0-110">[Maps](../core/maps.md) </span></span>  
 [<span data-ttu-id="ba7b0-111">BizTalk マッパーを使用してマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="ba7b0-111">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)