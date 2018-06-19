---
title: BizTalk エディターを拡張 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77c93ab2-0a9b-4c9d-81e5-3871fc8e6e13
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f8e4f574e652420ae11410e52268a199639cf6e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246242"
---
# <a name="extending-biztalk-editor"></a><span data-ttu-id="5aab5-102">BizTalk エディターの拡張</span><span class="sxs-lookup"><span data-stu-id="5aab5-102">Extending BizTalk Editor</span></span>
<span data-ttu-id="5aab5-103">BizTalk エディターの機能を拡張して、他のインスタンス メッセージ形式をサポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="5aab5-103">BizTalk Editor is designed to allow extensions that support alternative instance message formats.</span></span> <span data-ttu-id="5aab5-104">実際には、XML 形式は、BizTalk エディターに組み込まれている唯一の形式です。</span><span class="sxs-lookup"><span data-stu-id="5aab5-104">In fact, the XML format is the only format that is built into BizTalk Editor.</span></span> <span data-ttu-id="5aab5-105">ただし、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に含まれるフラット ファイル形式のサポートも、BizTalk エディターの拡張機能として実装されます。これは、拡張機能によって追加できる機能の代表的な例です。</span><span class="sxs-lookup"><span data-stu-id="5aab5-105">Even support for flat file formats, which is included in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], is implemented as a BizTalk Editor extension, thereby serving as a good example of the type of functionality that can be added by such extensions.</span></span>  
  
 <span data-ttu-id="5aab5-106">通常、BizTalk エディターの拡張機能は、スキーマ ツリーのノードに対応する XSD 要素に関連付けられている XSD (XML Schema Definition) 言語の注釈として、カスタム データを保存します。</span><span class="sxs-lookup"><span data-stu-id="5aab5-106">In general, BizTalk Editor extensions persist their custom data as XML Schema definition (XSD) language annotations associated with the XSD elements that correspond to the nodes in the schema tree.</span></span> <span data-ttu-id="5aab5-107">また、フラット ファイル拡張機能によって BizTalk エディターに追加される数多くの注釈のセットは、BizTalk エディターの拡張機能スキーマにカスタム データを保存する方法を示す代表的な例といえます。</span><span class="sxs-lookup"><span data-stu-id="5aab5-107">Again, the extensive set of annotations added by the Flat File Extension to BizTalk Editor serves as a good example of the way in which BizTalk Editor extensions can persist their custom data in the schema.</span></span>  
  
 <span data-ttu-id="5aab5-108">BizTalk エディターの拡張機能は、BizTalk エディターの機能を拡張する .NET アセンブリです。</span><span class="sxs-lookup"><span data-stu-id="5aab5-108">BizTalk Editor extensions are .NET assemblies that extend the functionality of BizTalk Editor.</span></span> <span data-ttu-id="5aab5-109">拡張機能として識別する、アセンブリの 1 つのクラスを実装する必要があります、 **IExtension**インターフェイス、および製品のインストール ディレクトリの Developer tools \schema Editor Extensions フォルダーの下にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="5aab5-109">To be identified as an extension, an assembly must have one class that implements the **IExtension** interface, and must be located under the Developer Tools\Schema Editor Extensions folder in the product installation directory.</span></span>  
  
 <span data-ttu-id="5aab5-110">拡張機能の開発者は、拡張機能を BizTalk エディターに公開するために必要なすべてのインターフェイスの定義が格納されている Microsoft.BizTalk.SchemaEditor.Extensibility.dll を、アセンブリで参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5aab5-110">The developer of an extension must have its assembly reference the Microsoft.BizTalk.SchemaEditor.Extensibility.dll, which contains the definition of all the interfaces needed for exposing extended functionality to BizTalk Editor.</span></span> <span data-ttu-id="5aab5-111">これらのインターフェイスが定義されている、 **Microsoft.BizTalk.SchemaEditor.Extensibility**名前空間。</span><span class="sxs-lookup"><span data-stu-id="5aab5-111">Those interfaces are defined under the **Microsoft.BizTalk.SchemaEditor.Extensibility** namespace.</span></span>  
  
 <span data-ttu-id="5aab5-112">**IExtension**インターフェイスは、BizTalk エディター元となるプロパティ マネージャー、カスタム ビュー、スキーマの検証、ネイティブ インスタンスの生成、およびネイティブなど、拡張機能にアクセスする、拡張機能のエントリ ポイントインスタンスの検証。</span><span class="sxs-lookup"><span data-stu-id="5aab5-112">The **IExtension** interface is the entry point for the extension, from which BizTalk Editor accesses the extended functionality, such as property managers, custom views, schema validation, native instance generation, and native instance validation.</span></span>  
  
 <span data-ttu-id="5aab5-113">特定のスキーマに関連付けられている複数の拡張子を持つことができます。 が、特定の時点で、標準として 1 つだけを設定できます。この設定は、**標準**のプロパティ、**スキーマ**ノード。</span><span class="sxs-lookup"><span data-stu-id="5aab5-113">A given schema can have multiple extensions associated with it, but only one can be set as the standard at a given time; this is set in the **Standard** property of the **Schema** node.</span></span> <span data-ttu-id="5aab5-114">現在、標準設定として使用できる拡張機能は、ネイティブ インスタンスの生成や検証に使用される機能、およびスキーマ検証に使用される機能です。</span><span class="sxs-lookup"><span data-stu-id="5aab5-114">The extension currently set as the standard is the one used for native instance generation and validation, and for schema validation.</span></span>  
  
 <span data-ttu-id="5aab5-115">拡張機能を関連付ける特定のスキーマを編集して、**スキーマ エディター拡張機能**のプロパティ、**スキーマ**ノード。</span><span class="sxs-lookup"><span data-stu-id="5aab5-115">Extensions can be associated with a given schema by editing the **Schema Editor Extensions** property of the **Schema** node.</span></span> <span data-ttu-id="5aab5-116">スキーマに関連付けられている拡張機能に関する情報はスキーマ自体内で、**注釈**の要素、**スキーマ**要素は、次の XSD フラグメントに示すようにします。</span><span class="sxs-lookup"><span data-stu-id="5aab5-116">The information about the extensions associated with a schema is stored in the schema itself, within the **annotation** element of the **schema** element, as illustrated in the following XSD fragment.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-16" ?>   
<xs:schema xmlns="http://BizTalk_Server_Project1.Schema11"  
        xmlns:b="http://schemas.microsoft.com/BizTalk/2003"  
        targetNamespace="http://BizTalk_Server_Project1.Schema11"  
        xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:annotation>  
        <xs:appinfo>  
            <schemaEditorExtension:schemaInfo namespaceAlias="b"  
                extensionClass="Microsoft.BizTalk.FlatFileExtension.FlatFileExtension"  
                standardName="Flat File"  
                xmlns:schemaEditorExtension="http://schemas.microsoft.com/BizTalk/2003/SchemaEditorExtensions" />  
            <b:schemaInfo schema_type="document" root_reference="Root"  
                is_receipt="no" schema_name="abc"  
                standard="Flat File"  
                count_positions_by_byte="false" />   
        </xs:appinfo>  
    </xs:annotation>  
    <xs:element name="Root">  
        ...  
  
```  
  
 <span data-ttu-id="5aab5-117">フレームワークを呼び出す拡張オブジェクトをインスタンス化した後、**初期化**のメソッド、 **IExtension**インターフェイスを渡して、 **ITree**オブジェクトように拡張機能スキーマ ツリーに関する情報にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5aab5-117">After instantiating the extension object, the framework invokes the **Initialize** method of the **IExtension** interface, passing an **ITree** object so that the extension can access information about the schema tree.</span></span> <span data-ttu-id="5aab5-118">たとえば、拡張機能は、アクセスすることでのすべての子ノードを通過でした、 **ITree.RootNode**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="5aab5-118">For example, the extension could traverse all child nodes by accessing the **ITree.RootNode** property.</span></span>  
  
 <span data-ttu-id="5aab5-119">このセクションでは、BizTalk エディターの拡張機能を BizTalk エディター環境に統合して、既存の BizTalk エディター コマンドにフックする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5aab5-119">This section describes the ways in which a BizTalk Editor extension can integrate into the BizTalk Editor environment and hook itself into existing BizTalk Editor commands.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5aab5-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5aab5-120">In This Section</span></span>  
  
-   [<span data-ttu-id="5aab5-121">プロパティ マネージャー</span><span class="sxs-lookup"><span data-stu-id="5aab5-121">Property Managers</span></span>](../core/property-managers.md)  
  
-   [<span data-ttu-id="5aab5-122">カスタム ビュー</span><span class="sxs-lookup"><span data-stu-id="5aab5-122">Custom Views</span></span>](../core/custom-views.md)  
  
-   [<span data-ttu-id="5aab5-123">スキーマの検証</span><span class="sxs-lookup"><span data-stu-id="5aab5-123">Schema Validation</span></span>](../core/schema-validation1.md)  
  
-   [<span data-ttu-id="5aab5-124">インスタンスの検証</span><span class="sxs-lookup"><span data-stu-id="5aab5-124">Instance Validation</span></span>](../core/instance-validation.md)  
  
-   [<span data-ttu-id="5aab5-125">インスタンスの生成</span><span class="sxs-lookup"><span data-stu-id="5aab5-125">Instance Generation</span></span>](../core/instance-generation.md)