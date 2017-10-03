---
title: "アダプターのローカリゼーション |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d200ce9-1a60-455b-88b0-6ec86092a786
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8862318547f2a7b8b4fa5dc7291e1673f1b9ba29
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="adapter-localization-issues"></a><span data-ttu-id="0dc7e-102">アダプターのローカリゼーションの問題</span><span class="sxs-lookup"><span data-stu-id="0dc7e-102">Adapter Localization Issues</span></span>
<span data-ttu-id="0dc7e-103">ここでは、カスタム アダプターを作成するときに発生する可能性のあるローカライズに関する問題を取り上げます。</span><span class="sxs-lookup"><span data-stu-id="0dc7e-103">The following topics cover localization issues that you may encounter when developing custom adapters.</span></span>  
  
## <a name="xsd-issues"></a><span data-ttu-id="0dc7e-104">XSD の問題点</span><span class="sxs-lookup"><span data-stu-id="0dc7e-104">XSD Issues</span></span>  
 <span data-ttu-id="0dc7e-105">アダプターの開発者は、アダプター フレームワークを使用して、アダプターのプロパティ ページを XML スキーマ定義 (XSD) スキーマで実装できます。</span><span class="sxs-lookup"><span data-stu-id="0dc7e-105">By using the Adapter Framework, adapter developers can implement adapter property pages with XML Schema Definition (XSD) schemas.</span></span>  
  
 <span data-ttu-id="0dc7e-106">アダプターにグローバリゼーションまたはローカライズの要件がない場合、XSD スキーマ内の文字列をハードコーディングできます、 **IDynamicAdapterConfig:GetConfigSchema**関数。</span><span class="sxs-lookup"><span data-stu-id="0dc7e-106">If your adapter has no globalization or localization requirements, then you can hard code the XSD schema string inside the **IDynamicAdapterConfig:GetConfigSchema** function.</span></span>  
  
 <span data-ttu-id="0dc7e-107">アダプターにグローバリゼーションまたはローカライズの要件がある場合は、2 つの方法のうちのいずれかを使用して XSD スキーマを実装できます。</span><span class="sxs-lookup"><span data-stu-id="0dc7e-107">If your adapter has globalization or localization requirements, you can implement the XSD schema in one of two ways.</span></span>  
  
-   <span data-ttu-id="0dc7e-108">デザイン時バイナリの外で個別の XSD ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="0dc7e-108">Use separate XSD files outside the design-time binary.</span></span> <span data-ttu-id="0dc7e-109">スキーマのテキスト全体をマニフェスト リソースにします。</span><span class="sxs-lookup"><span data-stu-id="0dc7e-109">Make the whole text of the schema a manifest resource.</span></span>  
  
-   <span data-ttu-id="0dc7e-110">プロパティ名と説明をリソースから動的に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="0dc7e-110">Dynamically replace the Property Names and Description from the resource:</span></span>  
  
    -   <span data-ttu-id="0dc7e-111">_locID をローカライズする各要素に追加します。</span><span class="sxs-lookup"><span data-stu-id="0dc7e-111">Add a _locID to each element that you want to localize.</span></span>  
  
    -   <span data-ttu-id="0dc7e-112">xpath を使用して、_locID 属性を持つスキーマ内のすべてのノードを返します。</span><span class="sxs-lookup"><span data-stu-id="0dc7e-112">Use an xpath to pull back all the nodes in the schema that have a _locID attribute.</span></span>  
  
    -   <span data-ttu-id="0dc7e-113">リソースで、_locID の値によりインデックス化された文字列を検索します。</span><span class="sxs-lookup"><span data-stu-id="0dc7e-113">Look up the resources for a string indexed by the value of the _locID.</span></span>  
  
    -   <span data-ttu-id="0dc7e-114">ノードのテキストを結果に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="0dc7e-114">Replace the node text with the result.</span></span>  
  
 <span data-ttu-id="0dc7e-115">2 つ目のオプションのサンプル コードを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="0dc7e-115">The following is sample code for the second option:</span></span>  
  
```  
string mySchema = GetSchemaFromResource(“mySchema”);  
string myLocalizedSchema = LocalizeSchemaDOM (mySchema, resourceManager);  
//  where…  
protected string GetSchemaFromResource (string name)  
{  
Assembly assem = this.GetType().Assembly;  
Stream stream = assem.GetManifestResourceStream(name);  
StreamReader reader = new StreamReader(stream);  
string schema = reader.ReadToEnd();  
return schema;  
}  
  
protected XmlDocument LocalizeSchemaDOM (string schema, ResourceManager resourceManager)  
{  
XmlDocument document = new XmlDocument();  
document.LoadXml(schema);  
XmlNodeList nodes = document.SelectNodes  
("/descendant::*[@_locID]");  
foreach (XmlNode node in nodes)  
{  
string locID = node.Attributes["_locID"].Value;  
node.InnerText = resourceManager.GetString(locID);  
}  
return document;  
}  
```