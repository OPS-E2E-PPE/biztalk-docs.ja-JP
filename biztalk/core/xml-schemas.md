---
title: XML スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1ec364e7-866d-4164-be91-be75a40ce878
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b46f5b43a34049dfc3ad366fd87fa82d6dac2cb7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997491"
---
# <a name="xml-schemas"></a><span data-ttu-id="9dbfa-102">XML スキーマ</span><span class="sxs-lookup"><span data-stu-id="9dbfa-102">XML Schemas</span></span>
<span data-ttu-id="9dbfa-103">XML スキーマは、XML で表されるビジネス ドキュメントの詳細情報を記述します。</span><span class="sxs-lookup"><span data-stu-id="9dbfa-103">An XML schema describes a business document that is represented in XML.</span></span> <span data-ttu-id="9dbfa-104">Microsoft BizTalk Server では、ビジネス ドキュメントの正規表現として XML を使用するため受信および送信ドキュメントには、翻訳は不要です。</span><span class="sxs-lookup"><span data-stu-id="9dbfa-104">Because Microsoft BizTalk Server uses XML as its canonical representation for business documents, inbound and outbound documents do not require any translation.</span></span> <span data-ttu-id="9dbfa-105">また、すべてのスキーマで使用できる基本的なプロパティだけを使用して、XML スキーマを BizTalk エディターで作成できるので、スキーマ エディター拡張機能を有効にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9dbfa-105">XML schemas can be created in BizTalk Editor using only the basic set of properties that are available within all schemas, and do not require any schema editor extensions to be enabled.</span></span>  
  
 <span data-ttu-id="9dbfa-106">BizTalk Server で XML スキーマを作成することがいくつかの方法はあります。</span><span class="sxs-lookup"><span data-stu-id="9dbfa-106">There are several ways in which you can create XML schemas in BizTalk Server.</span></span> <span data-ttu-id="9dbfa-107">たとえば、次のオブジェクトにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="9dbfa-107">These include:</span></span>  
  
- <span data-ttu-id="9dbfa-108">**新しいスキーマを作成する**します。</span><span class="sxs-lookup"><span data-stu-id="9dbfa-108">**Creating a new schema**.</span></span> <span data-ttu-id="9dbfa-109">このスキーマ作成の方法には、新しいスキーマを BizTalk プロジェクトに追加することも含まれます。</span><span class="sxs-lookup"><span data-stu-id="9dbfa-109">This method of schema creation involves adding a new schema to a BizTalk project.</span></span> <span data-ttu-id="9dbfa-110">**ソリューション エクスプ ローラー**、BizTalk プロジェクトを右クリックし、をクリックして**追加**、 をクリックして**新しい項目の**、 をクリックし、**スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="9dbfa-110">In **Solution Explorer**, right-click the BizTalk project, click **Add**, click **New Item**, and then click **Schema**.</span></span> <span data-ttu-id="9dbfa-111">スキーマ ツリー ビューでさまざまなノードを追加してスキーマの構造を構築します。</span><span class="sxs-lookup"><span data-stu-id="9dbfa-111">Build up the structure of the schema by adding various nodes in the schema tree view.</span></span>  
  
- <span data-ttu-id="9dbfa-112">**他のスキーマと組み合わせて、新しいスキーマを作成する**します。</span><span class="sxs-lookup"><span data-stu-id="9dbfa-112">**Creating a new schema, in conjunction with other schemas**.</span></span> <span data-ttu-id="9dbfa-113">: 複雑なスキーマを実際に使用するとき、一般的には、既存の他のスキーマで提供されている型を使用して、メッセージのスキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="9dbfa-113">For complex schemas in the real world, you are more likely to build the schemas for your messages by using types provided in other existing schemas.</span></span> <span data-ttu-id="9dbfa-114">XSD (XML Schema Definition) 言語の概念 (スキーマのインポート、包含、および再定義) を使用することにより、他のスキーマで既に定義されている型を利用できます。</span><span class="sxs-lookup"><span data-stu-id="9dbfa-114">By using the XML Schema definition (XSD) language concepts of importing, including, and redefining schemas, you can take advantage of types already defined in other schemas.</span></span> <span data-ttu-id="9dbfa-115">複数のスキーマを組み合わせて使用の詳細については、[使用その他のスキーマを](../core/schemas-that-use-other-schemas.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dbfa-115">For more information about using multiple schemas together, see [Schemas That Use Other Schemas](../core/schemas-that-use-other-schemas.md).</span></span>  
  
- <span data-ttu-id="9dbfa-116">**インスタンス メッセージからスキーマを生成する**します。</span><span class="sxs-lookup"><span data-stu-id="9dbfa-116">**Generating a schema from an instance message**.</span></span> <span data-ttu-id="9dbfa-117">: インスタンス メッセージが整形式 XML で構成されていれば、特定のインスタンス メッセージに対応する XML スキーマを生成できます。</span><span class="sxs-lookup"><span data-stu-id="9dbfa-117">You can generate an XML schema that corresponds to a particular instance message as long as that instance message consists of well-formed XML.</span></span> <span data-ttu-id="9dbfa-118">使用して、**生成した項目の追加 -  *\<BizTalk プロジェクト名\>***   ダイアログ ボックスをクリックして**生成した項目の追加**で**プロジェクト** メニューの この種類のスキーマ生成操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="9dbfa-118">Use the **Add Generated Items - *\<BizTalk Project Name\>*** dialog box, accessed by clicking **Add Generated Items** on the **Project** menu, to perform this type of schema generation operation.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="9dbfa-119">この生成操作は、XML スキーマを生成する場合のみ使用できます。プロパティ スキーマやフラット ファイル スキーマには使用できません。</span><span class="sxs-lookup"><span data-stu-id="9dbfa-119">This type of generation operation can only be used to generate XML schemas, not property schemas or flat file schemas.</span></span>  
  
- <span data-ttu-id="9dbfa-120">**以前のスキーマ仕様言語から XSD にスキーマを移行する**します。</span><span class="sxs-lookup"><span data-stu-id="9dbfa-120">**Migrating a schema from an older schema specification language to XSD**.</span></span> <span data-ttu-id="9dbfa-121">Xml-data Reduced (XDR) 形式でスキーマを格納する BizTalk Server の以前のバージョンを使用して開発されたスキーマから、BizTalk Server の XML スキーマを生成できます。</span><span class="sxs-lookup"><span data-stu-id="9dbfa-121">You can generate an XML schema for BizTalk Server from a schema that was developed by using a previous version of BizTalk Server, which stored schemas in XML-Data Reduced (XDR) format.</span></span> <span data-ttu-id="9dbfa-122">古い XDR スキーマを BizTalk Server で使用される XSD 形式に移行する方法の詳細については、[スキーマの移行前のバージョンの BizTalk Server から](../core/schema-migration-from-previous-versions-of-biztalk-server.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dbfa-122">For more information about how to migrate older XDR schemas to the XSD format used by BizTalk Server, see [Schema Migration from Previous Versions of BizTalk Server](../core/schema-migration-from-previous-versions-of-biztalk-server.md).</span></span>  
  
   <span data-ttu-id="9dbfa-123">また、DTD (Document Type Definition) 構文で表記されるドキュメント スキーマから、XSD に基づいた XML スキーマを生成できます。</span><span class="sxs-lookup"><span data-stu-id="9dbfa-123">You can also generate an XML schema based on XSD from a document schema expressed by using the Document Type Definition (DTD) syntax.</span></span>  
  
   <span data-ttu-id="9dbfa-124">使用して、**生成した項目の追加 -  *\<BizTalk プロジェクト名\>***   ダイアログ ボックスをクリックして**生成した項目の追加**で**プロジェクト** メニューの この種類のスキーマ生成操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="9dbfa-124">Use the **Add Generated Items - *\<BizTalk Project Name\>*** dialog box, accessed by clicking **Add Generated Items** on the **Project** menu, to perform this type of schema generation operation.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="9dbfa-125">これらの生成操作は、XML スキーマを生成する場合のみ使用できます。プロパティ スキーマやフラット ファイル スキーマには使用できません。</span><span class="sxs-lookup"><span data-stu-id="9dbfa-125">These types of generation operations can only be used to generate XML schemas, not property schemas or flat file schemas.</span></span>  
  
  <span data-ttu-id="9dbfa-126">スキーマの作成にどの方法を使用していても、スキーマを変更して、対応するインスタンス メッセージを完全に説明できます。</span><span class="sxs-lookup"><span data-stu-id="9dbfa-126">Whichever schema creation technique you use, you will continue by modifying the schema so that it provides a sufficiently complete description of its corresponding instance messages.</span></span> <span data-ttu-id="9dbfa-127">これらのタスクを開始するを参照してください。[スキーマ内のノードを管理する](../core/managing-the-nodes-within-a-schema.md)、[ノードのプロパティの設定](../core/how-to-set-node-properties.md)、および[既存のノードの操作](../core/working-with-existing-nodes.md)します。</span><span class="sxs-lookup"><span data-stu-id="9dbfa-127">To get started on these tasks, see [Managing the Nodes Within a Schema](../core/managing-the-nodes-within-a-schema.md), [Setting Node Properties](../core/how-to-set-node-properties.md), and [Working with Existing Nodes](../core/working-with-existing-nodes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dbfa-128">参照</span><span class="sxs-lookup"><span data-stu-id="9dbfa-128">See Also</span></span>  
 [<span data-ttu-id="9dbfa-129">さまざまな種類の BizTalk スキーマ</span><span class="sxs-lookup"><span data-stu-id="9dbfa-129">Different Types of BizTalk Schemas</span></span>](../core/different-types-of-biztalk-schemas.md)