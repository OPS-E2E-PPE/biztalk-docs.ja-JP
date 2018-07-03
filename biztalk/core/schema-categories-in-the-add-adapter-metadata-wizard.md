---
title: スキーマ カテゴリ、アダプター メタデータのウィザードの追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3927c676-f60a-449e-be43-6f75e28aefe1
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46fd9ffab7aa4f8617e08a18824cc251ad9f4173
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008011"
---
# <a name="schema-categories-in-the-add-adapter-metadata-wizard"></a><span data-ttu-id="85d02-102">アダプター メタデータの追加ウィザードのスキーマ カテゴリ</span><span class="sxs-lookup"><span data-stu-id="85d02-102">Schema Categories in the Add Adapter Metadata Wizard</span></span>

## <a name="overview"></a><span data-ttu-id="85d02-103">概要</span><span class="sxs-lookup"><span data-stu-id="85d02-103">Overview</span></span>
> [!NOTE]
>  <span data-ttu-id="85d02-104">このトピックは、実装する静的アダプターに対してのみ、 **IStaticAdapterConfig**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="85d02-104">This topic is only for static adapters that implement the **IStaticAdapterConfig** interface.</span></span>  
  
 <span data-ttu-id="85d02-105">アダプターは、データを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に渡す前に、数千あるスキーマのうちのいずれかを使用してデータを変換します。</span><span class="sxs-lookup"><span data-stu-id="85d02-105">An adapter may use any one of thousands of schemas to transform data before passing it to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="85d02-106">メタデータを BizTalk プロジェクトに追加する場合は、アダプター メタデータの追加ウィザードを使用して、アダプターと連携するすべてのスキーマの一覧からスキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="85d02-106">When adding metadata to a BizTalk project, use the Add Adapter Metadata Wizard to select a schema from a list of all the schemas with which the adapter interacts.</span></span>  
  
 <span data-ttu-id="85d02-107">サンプル ファイル アダプターの CategorySchema.xml ファイルは、サービス スキーマのツリー ビュー構成を生成するために、アダプター フレームワークの BiztalkAdapterFramework.xsd ファイルと共に使用されるスキーマ インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="85d02-107">In the sample file adapter, the CategorySchema.xml file is a schema instance that is used in conjunction with the Adapter Framework's BiztalkAdapterFramework.xsd file to populate a tree-view organization of service schemas.</span></span>  <span data-ttu-id="85d02-108">BizTalkAdapterFramework.xsd ファイルは、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Developer Tools フォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="85d02-108">The BizTalkAdapterFramework.xsd file is located in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Developer Tools folder.</span></span>  
  
 <span data-ttu-id="85d02-109">このファイルを作成し、ソリューションに即した方法でスキーマを構成できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="85d02-109">You should create this file so that it organizes the schemas in a manner that is intuitive to your solution.</span></span> <span data-ttu-id="85d02-110">CategorySchema.xml の既存のカテゴリは、独自のツリーで実行できることの一例にすぎません。</span><span class="sxs-lookup"><span data-stu-id="85d02-110">The existing categories in CategorySchema.xml are just an example of what you can do in your own tree.</span></span> <span data-ttu-id="85d02-111">これらのカテゴリとサンプル アダプターによって渡されるデータは特に関連性がありません。</span><span class="sxs-lookup"><span data-stu-id="85d02-111">The categories do not have any particular relevance to the data that is passed by the sample adapter.</span></span> <span data-ttu-id="85d02-112">スキーマの構成は、数千もの異なるスキーマを利用できるアプリケーション固有のアダプターで特に重要になります。</span><span class="sxs-lookup"><span data-stu-id="85d02-112">The organization of the schemas is particularly important with application-specific adapters, where thousands of different schemas may be available.</span></span> <span data-ttu-id="85d02-113">トランスポート固有のアダプターの場合、ツリー ビュー構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="85d02-113">For transport-specific adapters, this tree-view organization is unnecessary.</span></span>  
  
 <span data-ttu-id="85d02-114">次に示します、 **インポートするサービス**アダプター メタデータの追加ウィザードのページ。</span><span class="sxs-lookup"><span data-stu-id="85d02-114">The following figure shows the **Select Services to Import** page in the Add Adapter Metadata Wizard.</span></span>  
  
 <span data-ttu-id="85d02-115">![](../core/media/ebiz-prog-custad-tree.gif "ebiz_prog_custad_tree")</span><span class="sxs-lookup"><span data-stu-id="85d02-115">![](../core/media/ebiz-prog-custad-tree.gif "ebiz_prog_custad_tree")</span></span>  
<span data-ttu-id="85d02-116">アダプター メタデータの追加ウィザードのスキーマ カテゴリのツリー ビュー</span><span class="sxs-lookup"><span data-stu-id="85d02-116">Tree view of the schema categories in the Add Adapter Metadata Wizard</span></span>  


## <a name="sample-xml"></a><span data-ttu-id="85d02-117">サンプル XML</span><span class="sxs-lookup"><span data-stu-id="85d02-117">Sample XML</span></span>
  
 <span data-ttu-id="85d02-118">CategorySchema.xml ファイルのコードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="85d02-118">The following code shows the CategorySchema.xml file:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<CategoryTree>  
     <DisplayName>Services Organization</DisplayName>  
     <DisplayDescription>An organization of application services</DisplayDescription>  
     <CategoryTreeNode>  
          <DisplayName>Health Care</DisplayName>  
          <Description>Services under Health Care</Description>  
          <CategoryTreeNode>  
               <DisplayName>Administrative</DisplayName>  
               <Description>Administrative Health Care Services</Description>  
               <ServiceTreeNode>  
                    <DisplayName>Eligibility</DisplayName>  
                    <Description>Eligibility Verification Transactions</Description>  
                    <WSDLReference>ANSI X 12 270</WSDLReference>  
               </ServiceTreeNode>  
          </CategoryTreeNode>  
     </CategoryTreeNode>  
     <CategoryTreeNode>  
          <DisplayName>Manufacturing</DisplayName>  
          <Description>Manufacturing Services</Description>  
          <CategoryTreeNode>  
               <DisplayName>Inventory</DisplayName>  
               <Description>Inventory Services</Description>  
               <ServiceTreeNode>  
                    <DisplayName>Requisition</DisplayName>  
                    <Description>Requisition</Description>  
                    <WSDLReference>RequisitionService</WSDLReference>  
               </ServiceTreeNode>  
          </CategoryTreeNode>  
     </CategoryTreeNode>  
</CategoryTree>  
```  
  
 <span data-ttu-id="85d02-119">このスキーマ インスタンスには、次のノード タイプが表示されます。</span><span class="sxs-lookup"><span data-stu-id="85d02-119">The following node types appear in this schema instance:</span></span>  
  
- <span data-ttu-id="85d02-120">**CategoryTree します。**</span><span class="sxs-lookup"><span data-stu-id="85d02-120">**CategoryTree.**</span></span> <span data-ttu-id="85d02-121">システム情報モデルの最上位レベルの構造。</span><span class="sxs-lookup"><span data-stu-id="85d02-121">Top-level structure of a model of system information.</span></span> <span data-ttu-id="85d02-122">0 個以上の CategoryTreeNode ノード、ExpandableCategoryTreeNode ノード、および ServiceTreeNode ノードが格納されます。</span><span class="sxs-lookup"><span data-stu-id="85d02-122">Contains zero or more of the CategoryTreeNode, ExpandableCategoryTreeNode, and ServiceTreeNode nodes.</span></span>  
  
- <span data-ttu-id="85d02-123">**CategoryTreeNode します。**</span><span class="sxs-lookup"><span data-stu-id="85d02-123">**CategoryTreeNode.**</span></span> <span data-ttu-id="85d02-124">0 個以上の CategoryTreeNode ノード、および ServiceTreeNode ノードが格納されます。</span><span class="sxs-lookup"><span data-stu-id="85d02-124">Contains zero or more CategoryTreeNode and ServiceTreeNode nodes.</span></span> <span data-ttu-id="85d02-125">ユーザー インターフェイスでフォルダーとして表示される CategoryTreeNode を使用して、関連する一連のサービスをグループ化します。</span><span class="sxs-lookup"><span data-stu-id="85d02-125">Use the CategoryTreeNode that appears as a folder in the user interface (UI) to group a set of related services.</span></span> <span data-ttu-id="85d02-126">通常、このノードには、表示されるサービスの表示名と説明が格納されます。</span><span class="sxs-lookup"><span data-stu-id="85d02-126">Typically this contains a display name and description of the services to be displayed.</span></span> <span data-ttu-id="85d02-127">子ノードの数が少数である場合、アダプターは CategoryTreeNode を使用する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="85d02-127">An adapter might use a CategoryTreeNode if the number of child nodes is small.</span></span>  
  
- <span data-ttu-id="85d02-128">**ExpandableCategoryTreeNode します。**</span><span class="sxs-lookup"><span data-stu-id="85d02-128">**ExpandableCategoryTreeNode.**</span></span> <span data-ttu-id="85d02-129">展開時に動的に生成されるリーフ ノード。</span><span class="sxs-lookup"><span data-stu-id="85d02-129">A leaf node that is dynamically populated when expanded.</span></span> <span data-ttu-id="85d02-130">ExpandableCategoryTreeNode はプレースホルダーとして使用され、UI でフォルダーとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="85d02-130">The ExpandableCategoryTreeNode is used as a placeholder and appears as a folder in the UI.</span></span> <span data-ttu-id="85d02-131">このノードを使用すると、ユーザーがノードをクリックして展開するまで、サブ要素を含むカテゴリ ノードの生成を延期することができます。</span><span class="sxs-lookup"><span data-stu-id="85d02-131">This can be used to defer populating a category node with subelements until the user clicks to expand the node.</span></span> <span data-ttu-id="85d02-132">多数の子ノードがカテゴリに含まれる場合、アダプターは ExpandableCategoryTreeNode を使用する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="85d02-132">An adapter might use an ExpandableCategoryTreeNode if a category contains a large number of child nodes.</span></span>  
  
- <span data-ttu-id="85d02-133">**ServiceTreeNode します。**</span><span class="sxs-lookup"><span data-stu-id="85d02-133">**ServiceTreeNode.**</span></span> <span data-ttu-id="85d02-134">ServiceTreeNode は、UI でドキュメントまたはリーフ ノードとして表示され、Web Services Description Language (WSDL) ファイルを表します。</span><span class="sxs-lookup"><span data-stu-id="85d02-134">A ServiceTreeNode appears as a document, or leaf node, in the UI and represents a Web Services Description Language (WSDL) file.</span></span>  
  
  <span data-ttu-id="85d02-135">ユーザーは、ノードを展開するフォルダーをクリックすると、アダプター フレームワークが呼び出す、 **IStaticAdapterConfig.GetServiceOrganization**メソッドの値として、ノードの名前を渡して、アダプターを**NodeIdentifier**属性。</span><span class="sxs-lookup"><span data-stu-id="85d02-135">When a user clicks the folder to expand a node, the Adapter Framework calls the **IStaticAdapterConfig.GetServiceOrganization** method on the adapter passing the name of the node as the value of the **NodeIdentifier** attribute.</span></span> <span data-ttu-id="85d02-136">アダプターは、ExpandableCategoryTreeNode の下に追加するサブノードを含む CategoryTree を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="85d02-136">The adapter should return a CategoryTree containing the subnodes to add under the ExpandableCategoryTreeNode.</span></span> <span data-ttu-id="85d02-137">アダプター フレームワークは、ExpandableCategoryTreeNode を CategoryTreeNode に置き換えて、返された CategoryTree の子を CategoryTreeNode に追加します。</span><span class="sxs-lookup"><span data-stu-id="85d02-137">The Adapter Framework replaces the ExpandableCategoryTreeNode with a CategoryTreeNode and adds to it the children of the returned CategoryTree.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="85d02-138">最初の呼び出しで**IStaticAdapterConfig.GetServiceOrganization**アダプター フレームワークは、ノード識別子を null に渡します。</span><span class="sxs-lookup"><span data-stu-id="85d02-138">In the initial call to **IStaticAdapterConfig.GetServiceOrganization** the Adapter Framework passes null for the node identifier.</span></span> <span data-ttu-id="85d02-139">これは、ルート レベルの CategoryTree を返すようにアダプターに通知します。</span><span class="sxs-lookup"><span data-stu-id="85d02-139">This tells the adapter to return the root-level CategoryTree.</span></span>  
  
 <span data-ttu-id="85d02-140">BiztalkAdapterFramework.xsd ファイルから抽出したカテゴリ ツリー スキーマを次に示します。</span><span class="sxs-lookup"><span data-stu-id="85d02-140">Below is the category tree schema extracted from the BiztalkAdapterFramework.xsd file.</span></span> <span data-ttu-id="85d02-141">アダプター メタデータの追加ウィザードは、このカテゴリ ツリー スキーマをスケルトン ツリーとして使用し、特定のアプリケーション依存エンティティを XML ファイルから生成します。</span><span class="sxs-lookup"><span data-stu-id="85d02-141">This is used by the Add Adapter Metadata Wizard as the skeleton tree with which to populate with specific application-dependent entities from an XML file.</span></span> <span data-ttu-id="85d02-142">この例では、CategorySchema.xml ファイルがその XML ファイルに該当します。</span><span class="sxs-lookup"><span data-stu-id="85d02-142">In our example that file is the CategorySchema.xml file.</span></span>  
  
```  
<!-- Service Organization Tree schema used by Add Adapter Wizard -->  
    <xs:element name="CategoryTree" type="CategoryTree" />  
    <xs:complexType name="CategoryTree">  
        <xs:sequence>  
            <xs:element name="DisplayName" type="xs:string" />  
            <xs:element name="DisplayDescription" type="xs:string" />  
            <xs:choice minOccurs="0" maxOccurs="unbounded">  
                <xs:element name="ExpandableCategoryTreeNode" type="ExpandableCategoryTreeNode" minOccurs="0" maxOccurs="unbounded" />  
                <xs:element name="CategoryTreeNode" type="CategoryTreeNode" minOccurs="0" maxOccurs="unbounded" />  
                <xs:element name="ServiceTreeNode" type="ServiceTreeNode" minOccurs="0" maxOccurs="unbounded" />  
            </xs:choice>  
        </xs:sequence>  
    </xs:complexType>  
    <xs:complexType name="ExpandableCategoryTreeNode">  
        <xs:sequence>  
            <xs:element name="DisplayName" type="xs:string" />  
            <xs:element name="Description" type="xs:string" />  
        </xs:sequence>  
        <xs:attribute name="NodeIdentifier" type="xs:string" use="required"></xs:attribute>  
    </xs:complexType>  
    <xs:complexType name="CategoryTreeNode">  
        <xs:sequence>  
            <xs:element name="DisplayName" type="xs:string" />  
            <xs:element name="Description" type="xs:string" />  
            <xs:choice minOccurs="0" maxOccurs="unbounded">  
                <xs:element name="ExpandableCategoryTreeNode" type="ExpandableCategoryTreeNode" minOccurs="0" maxOccurs="unbounded" />  
                <xs:element name="CategoryTreeNode" type="CategoryTreeNode" minOccurs="0" maxOccurs="unbounded" />  
                <xs:element name="ServiceTreeNode" type="ServiceTreeNode" minOccurs="0" maxOccurs="unbounded" />  
            </xs:choice>  
        </xs:sequence>  
    </xs:complexType>  
    <xs:complexType name="ServiceTreeNode">  
        <xs:sequence>  
            <xs:element name="DisplayName" type="xs:string" />  
            <xs:element name="Description" type="xs:string" />  
            <xs:element name="WSDLReference" type="xs:string" />  
        </xs:sequence>  
    </xs:complexType>  
</xs:schema>  
```  
  
 <span data-ttu-id="85d02-143">CategorySchema.xml ファイルを修正したら、AdapterManagement プロジェクトをリビルドし、アダプター メタデータの追加ウィザードを実行して、CategorySchema.xml のツリーが正しく表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="85d02-143">After modifying your CategorySchema.xml file, rebuild the AdapterManagement project, and then run the Add Adapter Metadata Wizard to ensure that the tree represented in CategorySchema.xml appears correctly.</span></span>  
  
 <span data-ttu-id="85d02-144">アダプター メタデータの追加ウィザードを実行する方法の詳細については、次を参照してください。、**アダプター メタデータのウィザード ダイアログ ボックスを追加**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="85d02-144">For information about running the Add Adapter Metadata Wizard, see the **Add Adapter Metadata Wizard Dialog Box** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>