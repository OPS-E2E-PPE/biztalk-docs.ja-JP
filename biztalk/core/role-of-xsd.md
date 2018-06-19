---
title: XSD の役割 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1fe08f6b-563f-4bae-a5be-551e487b2a6d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ad2f99b60de5ebb2a3cd7e102a2f3f7b787d1ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268578"
---
# <a name="role-of-xsd"></a><span data-ttu-id="2690d-102">XSD の役割</span><span class="sxs-lookup"><span data-stu-id="2690d-102">Role of XSD</span></span>
<span data-ttu-id="2690d-103">XSD (XML Schema Definition) 言語は、BizTalk で定義されるメッセージ スキーマの基礎となる構文を提供します。</span><span class="sxs-lookup"><span data-stu-id="2690d-103">The XML Schema definition (XSD) language provides the underlying syntax of the message schemas defined within BizTalk.</span></span> <span data-ttu-id="2690d-104">BizTalk エディターと BizTalk マッパーのツリー ビューでは、それぞれ独自のプロパティのセットを備えた、レコード ノードおよびフィールド ノードの BizTalk 固有のグラフィカルな階層 (他の種類のノード間) を使用します。ただし、このような階層は、XSD として構築および保存されます。</span><span class="sxs-lookup"><span data-stu-id="2690d-104">Although the tree views in BizTalk Editor and BizTalk Mapper use a BizTalk-specific graphical hierarchy of record and field nodes (among other types of nodes), each with its own set of properties, such hierarchies are constructed and persisted as XSD.</span></span> <span data-ttu-id="2690d-105">BizTalk エディターでは、読み取り専用の XSD ビューを使用できます。このビューでは、グラフィカルに表示されているツリー ビューのスキーマにさまざまなノードを追加する場合、スキーマからさまざまなノードを削除する場合、およびこれらのノードに関連付けられているプロパティの値が変更される場合に構築される XSD を表示できます。</span><span class="sxs-lookup"><span data-stu-id="2690d-105">BizTalk Editor provides a read-only XSD view in which you can see the XSD that is constructed as various nodes are added to or removed from the graphic representation of the schema in the tree view, and as the values of the properties associated with those nodes are changed.</span></span> <span data-ttu-id="2690d-106">通常、BizTalk エディターで単純なスキーマを構築する場合に XSD の詳細を把握する必要はありません。ただし、ツリー ビューのスキーマ階層に対して変更を行う場合に XSD の変更内容を調査すると、XSD の使用方法を学習できます。</span><span class="sxs-lookup"><span data-stu-id="2690d-106">Although it is usually not necessary to understand the details of XSD to successfully construct simple schemas with BizTalk Editor, if you study the XSD changes as you make changes to the schema hierarchy in the tree view, you will learn to use XSD.</span></span>  
  
 <span data-ttu-id="2690d-107">XSD のスキーマ注釈機能と、BizTalk Server によって定義される幅広い注釈のセットを使用すると、XSD を効果的に拡張して、フラット ファイルなどの XML 以外のメッセージを表すためのセマンティクスをサポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="2690d-107">The schema annotation feature within XSD, with the extensive set of annotations defined by BizTalk Server, effectively allows XSD to be extended to support the necessary semantics for representing non-XML messages such as flat files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2690d-108">参照</span><span class="sxs-lookup"><span data-stu-id="2690d-108">See Also</span></span>  
 <span data-ttu-id="2690d-109">[Web 上の XSD リソース](../core/xsd-resources-on-the-web.md) </span><span class="sxs-lookup"><span data-stu-id="2690d-109">[XSD Resources on the Web](../core/xsd-resources-on-the-web.md) </span></span>  
 [<span data-ttu-id="2690d-110">スキーマについて</span><span class="sxs-lookup"><span data-stu-id="2690d-110">About Schemas</span></span>](../core/about-schemas.md)