---
title: "ソース スキーマと送信先スキーマ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- destination schemas
- source schemas, maps
- XML schemas, defining
- destination schemas, about destination schemas
- schemas, destination
- destination schemas, maps
- maps, source schemas
- schemas, Root Reference property
- Root Reference property, modifying
- source schemas
- modifying, Root Reference property
- maps, Root Reference property
- source schemas, about source schemas
- schemas, maps
- maps, schema requirements
- schemas, requirements
- schemas, source schemas
- maps, destination schemas
- Root Reference property
ms.assetid: 8c805854-9fa1-4ce3-938d-a2e61ba17fa1
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d82fb8445260b505fbd04b648c251b99fe896dcd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="source-and-destination-schemas"></a><span data-ttu-id="5ff45-102">送信元スキーマと送信先スキーマ</span><span class="sxs-lookup"><span data-stu-id="5ff45-102">Source and Destination Schemas</span></span>
<span data-ttu-id="5ff45-103">各 BizTalk マップは、2 つのスキーマを使用して: 送信元スキーマおよび送信先スキーマです。</span><span class="sxs-lookup"><span data-stu-id="5ff45-103">Each BizTalk map uses two schemas: a source schema and a destination schema.</span></span> <span data-ttu-id="5ff45-104">送信元スキーマは、データの取得元となるインスタンス メッセージの構造を定義します。</span><span class="sxs-lookup"><span data-stu-id="5ff45-104">A source schema defines the structure of the instance messages from which you are taking data.</span></span> <span data-ttu-id="5ff45-105">送信先スキーマは、マップによって生成されるインスタンス メッセージの構造を定義します。</span><span class="sxs-lookup"><span data-stu-id="5ff45-105">The destination schema defines the structure of the instance messages the map produces.</span></span> <span data-ttu-id="5ff45-106">たとえば、注文書から請求書に出荷先情報および請求先情報をマップする場合、送信元スキーマに注文書を定義するスキーマ、送信先スキーマに請求書を定義するスキーマが必要です。</span><span class="sxs-lookup"><span data-stu-id="5ff45-106">For example, if you want to map the shipping and billing information from a purchase order to an invoice, you need a schema to define purchase orders for the source schema and a schema defining invoices for the destination schema.</span></span>  
  
 <span data-ttu-id="5ff45-107">BizTalk マップで使用されるスキーマでは、次の条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ff45-107">Schemas used in BizTalk maps must meet the following conditions:</span></span>  
  
-   <span data-ttu-id="5ff45-108">現在の BizTalk プロジェクトの一部に送信元スキーマおよび送信先スキーマを組み込む必要があります。また、実行中にスキーマへアクセスするために、アセンブリにスキーマへの参照を組み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ff45-108">The source and destination schemas need to be a part of your current BizTalk project, or you must include a reference to the schemas in the assembly so that the schemas can be accessed during run time.</span></span>  
  
-   <span data-ttu-id="5ff45-109">BizTalk マッパーで使用されるスキーマは、XSD (XML Schema Definition) 言語に基づいている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ff45-109">The schemas used in BizTalk Mapper must be based on the XML Schema definition (XSD) language.</span></span> <span data-ttu-id="5ff45-110">BizTalk エディターを使用すると、このようなスキーマを簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="5ff45-110">BizTalk Editor provides an easy way to create such schemas.</span></span> <span data-ttu-id="5ff45-111">BizTalk エディターでスキーマの作成の詳細については、次を参照してください。 [BizTalk エディターを使用してスキーマを作成する](../core/creating-schemas-using-biztalk-editor.md)です。</span><span class="sxs-lookup"><span data-stu-id="5ff45-111">For more information about creating schemas with BizTalk Editor, see [Creating Schemas Using BizTalk Editor](../core/creating-schemas-using-biztalk-editor.md).</span></span> <span data-ttu-id="5ff45-112">参照してください[スキーマの作成](../core/creating-schemas.md)です。</span><span class="sxs-lookup"><span data-stu-id="5ff45-112">Also see [Creating Schemas](../core/creating-schemas.md).</span></span>  
  
 <span data-ttu-id="5ff45-113">BizTalk エディターでは、複数のルート ノードがあるスキーマを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5ff45-113">In BizTalk Editor, you can create schemas with multiple root nodes.</span></span> <span data-ttu-id="5ff45-114">ただし、BizTalk マップで複数のルート ノードがあるスキーマを使用する場合は、マップで使用するルート ノード (および対応するサブ構造体) を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ff45-114">However, if you use a schema with multiple root nodes in a BizTalk map, you must choose which root node (and corresponding substructure) to use in the map.</span></span> <span data-ttu-id="5ff45-115">スキーマが、**ルート参照**ルートを識別するプロパティが主キー。</span><span class="sxs-lookup"><span data-stu-id="5ff45-115">Schemas have a **Root Reference** property identifying which root is primary.</span></span> <span data-ttu-id="5ff45-116">スキーマに複数のルートと**ルート参照**プロパティ スキーマは、最初に開いたとき元または送信先スキーマ、BizTalk マッパーは、指定されたルート。</span><span class="sxs-lookup"><span data-stu-id="5ff45-116">If a schema has multiple roots and the **Root Reference** property is set when the schema is first opened as the source or destination schema, BizTalk Mapper uses the specified root.</span></span> <span data-ttu-id="5ff45-117">スキーマに複数のルートと**ルート参照**プロパティが設定されていない、BizTalk マッパーでは、ルートを選択するように求められます。</span><span class="sxs-lookup"><span data-stu-id="5ff45-117">If a schema has multiple roots and the **Root Reference** property is not set, BizTalk Mapper prompts you to choose a root.</span></span>  
  
 <span data-ttu-id="5ff45-118">変更した場合、**ルート参照**マップでは、BizTalk マッパーは既に使用のスキーマ プロパティの変更を確認できず、最初に指定したルートを使用し続けます。</span><span class="sxs-lookup"><span data-stu-id="5ff45-118">If you change the **Root Reference** property of a schema already used in a map, BizTalk Mapper does not notice the change and continues to use the originally specified root.</span></span> <span data-ttu-id="5ff45-119">設定をお勧め、同じスキーマの異なるルートを使用して別のマップを構築する場合、**ルート参照**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="5ff45-119">If you want to build different maps using different roots of the same schema, it is best not to set the **Root Reference** property.</span></span> <span data-ttu-id="5ff45-120">この場合、新しいマップでスキーマを使用するたびに、明示的にルートを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ff45-120">That way, whenever the schema is used for a new map, you must explicitly choose the root.</span></span>  
  
 <span data-ttu-id="5ff45-121">マップにスキーマを含めた後にスキーマを編集すると、マップ内のリンクが壊れる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5ff45-121">If you edit a schema after it is included in a map, the links within the map may break.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ff45-122">参照</span><span class="sxs-lookup"><span data-stu-id="5ff45-122">See Also</span></span>  
 <span data-ttu-id="5ff45-123">[マップ](../core/maps.md) </span><span class="sxs-lookup"><span data-stu-id="5ff45-123">[Maps](../core/maps.md) </span></span>  
 [<span data-ttu-id="5ff45-124">BizTalk マッパーを使用してマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="5ff45-124">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)