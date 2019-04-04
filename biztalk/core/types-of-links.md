---
title: リンクの種類 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- compiler directives, links
- elastic links [maps]
- maps, links
- BizTalk Mapper, links
- partial links [maps]
- fixed links [maps]
ms.assetid: 348fae77-2e25-4b79-93bb-d42f3d18a3f7
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f2eb8d5546698cc611072ccff1e9f0bf4abf9a2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009611"
---
# <a name="types-of-links"></a><span data-ttu-id="1be0a-102">リンクの種類</span><span class="sxs-lookup"><span data-stu-id="1be0a-102">Types of Links</span></span>
<span data-ttu-id="1be0a-103">次の一覧は、BizTalk マッパーで使用できるさまざまな種類のリンクを示しています。</span><span class="sxs-lookup"><span data-stu-id="1be0a-103">The following list summarizes the various types of links available in BizTalk Mapper:</span></span>  
  
- <span data-ttu-id="1be0a-104">**柔軟なリンク。**</span><span class="sxs-lookup"><span data-stu-id="1be0a-104">**Elastic links.**</span></span> <span data-ttu-id="1be0a-105">"柔軟な" という用語は、リンクの両端が接続される前の、作成中のリンクに適用されます。</span><span class="sxs-lookup"><span data-stu-id="1be0a-105">The term elastic applies to a link as it is being created, before both ends of the link are connected.</span></span> <span data-ttu-id="1be0a-106">たとえば、送信元スキーマのフィールドからのリンクをドラッグして、送信先スキーマに対応するフィールドにまだ接続がない場合は、リンクがエラスティック。</span><span class="sxs-lookup"><span data-stu-id="1be0a-106">For example, if you are dragging a link from a field in the source schema, but you have not yet connected it to its corresponding field in the destination schema, the link is elastic.</span></span> <span data-ttu-id="1be0a-107">接続を完了すると、柔軟なリンクが固定リンクになります。</span><span class="sxs-lookup"><span data-stu-id="1be0a-107">As you complete the connection, the elastic link becomes a fixed link.</span></span>  
  
   <span data-ttu-id="1be0a-108">リンクの 1 つのエンドポイントを、別のノードまたは Functoid にドラッグできます。</span><span class="sxs-lookup"><span data-stu-id="1be0a-108">You can drag one endpoint of a link to another node or a functoid.</span></span> <span data-ttu-id="1be0a-109">リンクの配置の詳細については、[リンクを作成する方法](../core/how-to-create-links.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1be0a-109">For more information about link replacement, see [How to Create Links](../core/how-to-create-links.md).</span></span>  
  
- <span data-ttu-id="1be0a-110">**固定リンク。**</span><span class="sxs-lookup"><span data-stu-id="1be0a-110">**Fixed Links.**</span></span> <span data-ttu-id="1be0a-111">"固定" という用語は、送信元インスタンス メッセージから送信先インスタンス メッセージへの値の移動 (または、移動の一部) を表すために明示的に構築されたリンクに適用されます。</span><span class="sxs-lookup"><span data-stu-id="1be0a-111">The term fixed applies to a link that you have explicitly constructed to represent the movement of a value from a source instance message to a destination instance message, or at least a part of that movement.</span></span> <span data-ttu-id="1be0a-112">直接接続する固定リンク、**レコード**または**フィールド**ソース スキーマのノードに、**レコード**または**フィールド**マップ先のノードスキーマでは、実行時にデータの直線コピーを表します。</span><span class="sxs-lookup"><span data-stu-id="1be0a-112">Fixed links that directly connect a **Record** or **Field** node in the source schema to a **Record** or **Field** node in the destination schema represent a straight copying of data at run time.</span></span> <span data-ttu-id="1be0a-113">一方の端を Functoid に接続している固定リンクは、実行時の入力インスタンス メッセージから出力インスタンス メッセージへのデータの移動の一部を表します。</span><span class="sxs-lookup"><span data-stu-id="1be0a-113">Fixed links connecting to a functoid at one end or the other represent part of the movement of data from an input instance message to an output instance message at run time.</span></span> <span data-ttu-id="1be0a-114">これらを組み合わせて送信元スキーマと送信先スキーマのリンクを確立すると、データのアイテム全体の移動が示されます。</span><span class="sxs-lookup"><span data-stu-id="1be0a-114">Several of these together, completing the link between the source and destination schemas, represent the entire movement of an item of data.</span></span>  
  
- <span data-ttu-id="1be0a-115">**部分的なリンク。**</span><span class="sxs-lookup"><span data-stu-id="1be0a-115">**Partial links.**</span></span> <span data-ttu-id="1be0a-116">部分的な語句が対象の現在表示できない、正確なリンクに適用されます**レコード**または**フィールド**ノードの送信元または送信先スキーマで接続されています。</span><span class="sxs-lookup"><span data-stu-id="1be0a-116">The term partial applies to links for which you cannot currently see the exact **Record** or **Field** node to which they are connected in the source or destination schemas.</span></span> <span data-ttu-id="1be0a-117">これが発生したときに、**レコード**または**フィールド**スキーマのツリー表記でいずれかの先祖ノードが折りたたまれているために、アタッチ先のノードは表示されません。</span><span class="sxs-lookup"><span data-stu-id="1be0a-117">This occurs when the **Record** or **Field** node to which they are attached is not shown because one of its ancestor nodes is collapsed in the tree representation of the schema.</span></span> <span data-ttu-id="1be0a-118">部分的なリンクの詳細については、[リンクの表示を最適化する方法](../core/how-to-optimize-the-display-of-links.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1be0a-118">For more information about partial links, see [How to Optimize the Display of Links](../core/how-to-optimize-the-display-of-links.md).</span></span>  
  
- <span data-ttu-id="1be0a-119">**コンパイラ リンクを示します。**</span><span class="sxs-lookup"><span data-stu-id="1be0a-119">**Compiler links.**</span></span> <span data-ttu-id="1be0a-120">"コンパイラ" という用語は、BizTalk プロジェクトを作成する際に BizTalk マッパーが自動的に作成するリンクに適用されます。</span><span class="sxs-lookup"><span data-stu-id="1be0a-120">The term compiler applies to links that BizTalk Mapper creates automatically when you build a BizTalk project.</span></span> <span data-ttu-id="1be0a-121">たとえば、テーブルドリブン ループを構成すると、コンパイラ リンクは、送信元スキーマのレコードおよびフィールドと送信先スキーマのレコードおよびフィールドとの関係およびリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="1be0a-121">For example, if you configure table-driven looping, the compiler links show the relationship and the links between the records and fields in the source schema and the records and fields in the destination schema.</span></span> <span data-ttu-id="1be0a-122">このようなリンクは、コンパイラ ディレクティブで自動的に生成させることができます。また、ユーザーがリンクを生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="1be0a-122">This type of link can be generated automatically by compiler directives, or it can be user-directed.</span></span>  
  
  <span data-ttu-id="1be0a-123">既定で、BizTalk マッパーは、マップの詳細を区別するためにさまざまな色付きの線を使用して、これらの各種のリンクを表示します。</span><span class="sxs-lookup"><span data-stu-id="1be0a-123">BizTalk Mapper, by default, displays these various types of links using different colored lines to help you distinguish the detail of your maps.</span></span> <span data-ttu-id="1be0a-124">これらのさまざまな種類のリンクを使用する色を変更することができます、**オプション**コマンドを**ツール**メニュー。</span><span class="sxs-lookup"><span data-stu-id="1be0a-124">You can change the colors used for these different kinds of links with the **Options** command on the **Tools** menu.</span></span> <span data-ttu-id="1be0a-125">色の変化が異なるカテゴリのリンクを表示する方法の詳細については、[方法、色のカスタマイズ、BizTalk マッパーでフォント](../core/how-to-customize-colors-and-font-in-biztalk-mapper.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1be0a-125">For more information about how change in color renders different categories of links, see [How to Customize Colors and Font in BizTalk Mapper](../core/how-to-customize-colors-and-font-in-biztalk-mapper.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1be0a-126">参照</span><span class="sxs-lookup"><span data-stu-id="1be0a-126">See Also</span></span>  
 [<span data-ttu-id="1be0a-127">リンクを使用してレコードとフィールド マッピングを指定する</span><span class="sxs-lookup"><span data-stu-id="1be0a-127">Using Links to Specify Record and Field Mappings</span></span>](../core/using-links-to-specify-record-and-field-mappings.md)