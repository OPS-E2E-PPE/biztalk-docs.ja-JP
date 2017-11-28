---
title: "XPath をコピーする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 404599d4-0fb3-4c7c-91e6-1295d9d0965e
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb282c5c32d8da62a9da6d7a9c900c798e44eee7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-copy-xpath"></a><span data-ttu-id="a187b-102">XPath をコピーする方法</span><span class="sxs-lookup"><span data-stu-id="a187b-102">How to Copy XPath</span></span>
<span data-ttu-id="a187b-103">XSD (XML Schema Definition) 言語は、BizTalk Server で定義されるメッセージ スキーマの基礎となる構文を提供します。</span><span class="sxs-lookup"><span data-stu-id="a187b-103">The XML Schema definition (XSD) language provides the underlying syntax of the message schemas defined within BizTalk Server.</span></span> <span data-ttu-id="a187b-104">BizTalk マッパーのツリー ビューでは、それぞれ独自のプロパティのセットを備えた、レコード ノードおよびフィールド ノードの BizTalk 固有のグラフィカルな階層 (他の種類のノード間) を使用します。ただし、このような階層は、XSD として構築および保存されます。</span><span class="sxs-lookup"><span data-stu-id="a187b-104">Although the tree views in BizTalk Mapper use a BizTalk-specific graphical hierarchy of record and field nodes (among other types of nodes), each with its own set of properties, such hierarchies are constructed and persisted as XSD.</span></span>  
  
 <span data-ttu-id="a187b-105">マップが複雑で複数のグリッド ページが含まれる場合は、スキーマ ノードの親を特定するのが難しいことがあります。</span><span class="sxs-lookup"><span data-stu-id="a187b-105">In scenarios where maps are complex and span across grid pages, locating the parent of a schema node can be difficult.</span></span> <span data-ttu-id="a187b-106">このような場合は XSD パスが役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="a187b-106">The XSD path will be of use here.</span></span> <span data-ttu-id="a187b-107">XSD パスを使用すると、スキーマ ノードの深さについての情報を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="a187b-107">You can use the XSD path to get information about the depth of schema nodes.</span></span> <span data-ttu-id="a187b-108">また、このパスを別のグリッド ページで再利用して、リレーションシップを識別できます。</span><span class="sxs-lookup"><span data-stu-id="a187b-108">Also, you can reuse this path in another grid page to identify the relationship.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a187b-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="a187b-109">Prerequisites</span></span>  
 <span data-ttu-id="a187b-110">これらの手順では、BizTalk マッパーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a187b-110">These instructions require that BizTalk Mapper is running.</span></span>  
  
### <a name="to-copy-the-xsd-path-xpath"></a><span data-ttu-id="a187b-111">XSD パス (XPath) をコピーするには</span><span class="sxs-lookup"><span data-stu-id="a187b-111">To copy the XSD path (XPath)</span></span>  
  
1.  <span data-ttu-id="a187b-112">XSD パスが必要し、なる をクリックし、スキーマ ノードを右クリックして**コピー XPath**です。</span><span class="sxs-lookup"><span data-stu-id="a187b-112">Right-click the schema node for which you want the XSD path, and then click **Copy XPath**.</span></span>  
  
2.  <span data-ttu-id="a187b-113">テキスト エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="a187b-113">Open a text editor.</span></span> <span data-ttu-id="a187b-114">**[編集]** メニューの **[貼り付け]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a187b-114">On the **Edit** menu, click **Paste**.</span></span> <span data-ttu-id="a187b-115">XSD パスを確認できるようになります。</span><span class="sxs-lookup"><span data-stu-id="a187b-115">You can now see the XSD path.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a187b-116">または、Ctrl + V キーを押してテキスト エディターにパスを貼り付けることもできます。</span><span class="sxs-lookup"><span data-stu-id="a187b-116">Alternatively, you can press CTRL+V to paste the path in a text editor.</span></span>  
  
     <span data-ttu-id="a187b-117">次に示すコードは、選択されているスキーマ ノードの XSD パスです。</span><span class="sxs-lookup"><span data-stu-id="a187b-117">The code below displays the XSD path for the selected schema node.</span></span>  
  
    ```  
    /*[local-name()='<Schema>']/*[local-name()='Shipment']/*[local-name()='DataCollection']  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a187b-118">参照</span><span class="sxs-lookup"><span data-stu-id="a187b-118">See Also</span></span>  
 <span data-ttu-id="a187b-119">[BizTalk マッパーの強化された機能を使用](../core/using-enhanced-features-in-biztalk-mapper.md) </span><span class="sxs-lookup"><span data-stu-id="a187b-119">[Using Enhanced Features in BizTalk Mapper](../core/using-enhanced-features-in-biztalk-mapper.md) </span></span>  
 <span data-ttu-id="a187b-120">[スキーマを置換する方法](../core/how-to-replace-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="a187b-120">[How to Replace Schemas](../core/how-to-replace-schemas.md) </span></span>  
 <span data-ttu-id="a187b-121">[展開して、スキーマ ツリーを折りたたむ方法](https://msdn.microsoft.com/library/ee253802(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="a187b-121">[How to Expand and Collapse the Schema Trees](https://msdn.microsoft.com/library/ee253802(v=bts.10).aspx)</span></span>