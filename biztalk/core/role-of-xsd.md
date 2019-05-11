---
title: XSD の役割 |Microsoft Docs
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
ms.openlocfilehash: d6cb9a975f137263265051be0235f33d35bd4a41
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303531"
---
# <a name="role-of-xsd"></a><span data-ttu-id="39bef-102">XSD の役割</span><span class="sxs-lookup"><span data-stu-id="39bef-102">Role of XSD</span></span>
<span data-ttu-id="39bef-103">XML スキーマ定義 (XSD) 言語は、BizTalk で定義されるメッセージ スキーマの基礎となる構文を提供します。</span><span class="sxs-lookup"><span data-stu-id="39bef-103">The XML Schema definition (XSD) language provides the underlying syntax of the message schemas defined within BizTalk.</span></span> <span data-ttu-id="39bef-104">BizTalk エディターおよび BizTalk マッパーのツリー ビューは、独自のプロパティのセットとレコードの BizTalk 固有のグラフィカルな階層と [フィールド] ノード (その他の種類のノード間)、各を使用して、このような階層が作成され、XSD として永続化します。</span><span class="sxs-lookup"><span data-stu-id="39bef-104">Although the tree views in BizTalk Editor and BizTalk Mapper use a BizTalk-specific graphical hierarchy of record and field nodes (among other types of nodes), each with its own set of properties, such hierarchies are constructed and persisted as XSD.</span></span> <span data-ttu-id="39bef-105">BizTalk エディターは、ノード数が、プロパティの値に関連付けられているさまざまなノードを追加またはツリー ビュー内のスキーマのグラフィック表現から削除し、構築される XSD を表示できる読み取り専用の XSD ビューを提供します。変更されました。</span><span class="sxs-lookup"><span data-stu-id="39bef-105">BizTalk Editor provides a read-only XSD view in which you can see the XSD that is constructed as various nodes are added to or removed from the graphic representation of the schema in the tree view, and as the values of the properties associated with those nodes are changed.</span></span> <span data-ttu-id="39bef-106">通常はありませんが、ツリー ビューでスキーマの階層構造を変更すると、XSD の変更内容を調査する場合は、単純なスキーマを BizTalk エディターを正常に構築する XSD の詳細を理解するために必要なは、XSD の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="39bef-106">Although it is usually not necessary to understand the details of XSD to successfully construct simple schemas with BizTalk Editor, if you study the XSD changes as you make changes to the schema hierarchy in the tree view, you will learn to use XSD.</span></span>  
  
 <span data-ttu-id="39bef-107">BizTalk Server で定義されている注釈の広範なセットと、XSD 内でのスキーマ注釈機能は、フラット ファイルなどの XML 以外のメッセージを表すため、必要なセマンティクスをサポートするために拡張する XSD を効果的にできます。</span><span class="sxs-lookup"><span data-stu-id="39bef-107">The schema annotation feature within XSD, with the extensive set of annotations defined by BizTalk Server, effectively allows XSD to be extended to support the necessary semantics for representing non-XML messages such as flat files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39bef-108">参照</span><span class="sxs-lookup"><span data-stu-id="39bef-108">See Also</span></span>  
 <span data-ttu-id="39bef-109">[Web 上の XSD リソース](../core/xsd-resources-on-the-web.md) </span><span class="sxs-lookup"><span data-stu-id="39bef-109">[XSD Resources on the Web](../core/xsd-resources-on-the-web.md) </span></span>  
 [<span data-ttu-id="39bef-110">スキーマについて</span><span class="sxs-lookup"><span data-stu-id="39bef-110">About Schemas</span></span>](../core/about-schemas.md)