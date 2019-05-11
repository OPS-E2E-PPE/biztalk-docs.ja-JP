---
title: XPath をコピーする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 404599d4-0fb3-4c7c-91e6-1295d9d0965e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5bf9a8da90f264abb0953592abf16dc0e157fcb5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385600"
---
# <a name="how-to-copy-xpath"></a><span data-ttu-id="bc705-102">XPath をコピーする方法</span><span class="sxs-lookup"><span data-stu-id="bc705-102">How to Copy XPath</span></span>
<span data-ttu-id="bc705-103">XML スキーマ定義 (XSD) 言語は、BizTalk Server 内で定義されるメッセージ スキーマの基礎となる構文を提供します。</span><span class="sxs-lookup"><span data-stu-id="bc705-103">The XML Schema definition (XSD) language provides the underlying syntax of the message schemas defined within BizTalk Server.</span></span> <span data-ttu-id="bc705-104">BizTalk マッパーのツリー ビューは、独自のプロパティのセットとレコードの BizTalk 固有のグラフィカルな階層と [フィールド] ノード (その他の種類のノード間)、各を使用して、このような階層が作成され、XSD として永続化します。</span><span class="sxs-lookup"><span data-stu-id="bc705-104">Although the tree views in BizTalk Mapper use a BizTalk-specific graphical hierarchy of record and field nodes (among other types of nodes), each with its own set of properties, such hierarchies are constructed and persisted as XSD.</span></span>  
  
 <span data-ttu-id="bc705-105">マップが複雑になり、span をグリッド ページ間ではここでは、スキーマのノードの親を検索するは難しいです。</span><span class="sxs-lookup"><span data-stu-id="bc705-105">In scenarios where maps are complex and span across grid pages, locating the parent of a schema node can be difficult.</span></span> <span data-ttu-id="bc705-106">XSD パスは、ここで使用されます。</span><span class="sxs-lookup"><span data-stu-id="bc705-106">The XSD path will be of use here.</span></span> <span data-ttu-id="bc705-107">XSD パスを使用すると、スキーマ ノードの深さについての情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="bc705-107">You can use the XSD path to get information about the depth of schema nodes.</span></span> <span data-ttu-id="bc705-108">また、リレーションシップを識別するために別のグリッド ページ内にこのパスを再利用できます。</span><span class="sxs-lookup"><span data-stu-id="bc705-108">Also, you can reuse this path in another grid page to identify the relationship.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bc705-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="bc705-109">Prerequisites</span></span>  
 <span data-ttu-id="bc705-110">これらの手順では、BizTalk マッパーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc705-110">These instructions require that BizTalk Mapper is running.</span></span>  
  
### <a name="to-copy-the-xsd-path-xpath"></a><span data-ttu-id="bc705-111">XSD パス (XPath) をコピーするには</span><span class="sxs-lookup"><span data-stu-id="bc705-111">To copy the XSD path (XPath)</span></span>  
  
1.  <span data-ttu-id="bc705-112">スキーマのノードを XSD パスが必要し、し、をクリックを右クリックして**XPath のコピー**します。</span><span class="sxs-lookup"><span data-stu-id="bc705-112">Right-click the schema node for which you want the XSD path, and then click **Copy XPath**.</span></span>  
  
2.  <span data-ttu-id="bc705-113">テキスト エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="bc705-113">Open a text editor.</span></span> <span data-ttu-id="bc705-114">**[編集]** メニューの **[貼り付け]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc705-114">On the **Edit** menu, click **Paste**.</span></span> <span data-ttu-id="bc705-115">XSD パスが確認できます。</span><span class="sxs-lookup"><span data-stu-id="bc705-115">You can now see the XSD path.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bc705-116">またをテキスト エディターで、パスを貼り付けるには、CTRL + V を押すことができます。</span><span class="sxs-lookup"><span data-stu-id="bc705-116">Alternatively, you can press CTRL+V to paste the path in a text editor.</span></span>  
  
     <span data-ttu-id="bc705-117">次のコードでは、選択したスキーマ ノードの XSD パスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bc705-117">The code below displays the XSD path for the selected schema node.</span></span>  
  
    ```  
    /*[local-name()='<Schema>']/*[local-name()='Shipment']/*[local-name()='DataCollection']  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="bc705-118">参照</span><span class="sxs-lookup"><span data-stu-id="bc705-118">See Also</span></span>  
 <span data-ttu-id="bc705-119">[BizTalk マッパーの強化された機能を使用](../core/using-enhanced-features-in-biztalk-mapper.md) </span><span class="sxs-lookup"><span data-stu-id="bc705-119">[Using Enhanced Features in BizTalk Mapper](../core/using-enhanced-features-in-biztalk-mapper.md) </span></span>  
 <span data-ttu-id="bc705-120">[スキーマを置換する方法](../core/how-to-replace-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="bc705-120">[How to Replace Schemas](../core/how-to-replace-schemas.md) </span></span>  
 <span data-ttu-id="bc705-121">[展開し、スキーマ ツリーを折りたたむ方法](https://msdn.microsoft.com/library/ee253802(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="bc705-121">[How to Expand and Collapse the Schema Trees](https://msdn.microsoft.com/library/ee253802(v=bts.10).aspx)</span></span>