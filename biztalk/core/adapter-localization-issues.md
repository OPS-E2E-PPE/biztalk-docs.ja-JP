---
title: アダプターのローカライズに関する問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d200ce9-1a60-455b-88b0-6ec86092a786
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c829ce496c124f3333c353f481eb3958e29d5c77
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996339"
---
# <a name="adapter-localization-issues"></a><span data-ttu-id="dfe02-102">アダプターのローカライズに関する問題</span><span class="sxs-lookup"><span data-stu-id="dfe02-102">Adapter Localization Issues</span></span>
<span data-ttu-id="dfe02-103">ここでは、カスタム アダプターを作成するときに発生する可能性のあるローカライズに関する問題を取り上げます。</span><span class="sxs-lookup"><span data-stu-id="dfe02-103">The following topics cover localization issues that you may encounter when developing custom adapters.</span></span>  
  
## <a name="xsd-issues"></a><span data-ttu-id="dfe02-104">XSD の問題点</span><span class="sxs-lookup"><span data-stu-id="dfe02-104">XSD Issues</span></span>  
 <span data-ttu-id="dfe02-105">アダプターの開発者は、アダプター フレームワークを使用して、アダプターのプロパティ ページを XML スキーマ定義 (XSD) スキーマで実装できます。</span><span class="sxs-lookup"><span data-stu-id="dfe02-105">By using the Adapter Framework, adapter developers can implement adapter property pages with XML Schema Definition (XSD) schemas.</span></span>  
  
 <span data-ttu-id="dfe02-106">アダプターにグローバリゼーションまたはローカライズの要件がないかどうかは、内の XSD スキーマ文字列をハードコーディングできます、 **IDynamicAdapterConfig:GetConfigSchema**関数。</span><span class="sxs-lookup"><span data-stu-id="dfe02-106">If your adapter has no globalization or localization requirements, then you can hard code the XSD schema string inside the **IDynamicAdapterConfig:GetConfigSchema** function.</span></span>  
  
 <span data-ttu-id="dfe02-107">アダプターにグローバリゼーションまたはローカライズの要件がある場合は、2 つの方法のうちのいずれかを使用して XSD スキーマを実装できます。</span><span class="sxs-lookup"><span data-stu-id="dfe02-107">If your adapter has globalization or localization requirements, you can implement the XSD schema in one of two ways.</span></span>  
  
- <span data-ttu-id="dfe02-108">デザイン時バイナリの外で個別の XSD ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="dfe02-108">Use separate XSD files outside the design-time binary.</span></span> <span data-ttu-id="dfe02-109">スキーマのテキスト全体をマニフェスト リソースにします。</span><span class="sxs-lookup"><span data-stu-id="dfe02-109">Make the whole text of the schema a manifest resource.</span></span>  
  
- <span data-ttu-id="dfe02-110">プロパティ名と説明をリソースから動的に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="dfe02-110">Dynamically replace the Property Names and Description from the resource:</span></span>  
  
  -   <span data-ttu-id="dfe02-111">_locID をローカライズする各要素に追加します。</span><span class="sxs-lookup"><span data-stu-id="dfe02-111">Add a _locID to each element that you want to localize.</span></span>  
  
  -   <span data-ttu-id="dfe02-112">xpath を使用して、_locID 属性を持つスキーマ内のすべてのノードを返します。</span><span class="sxs-lookup"><span data-stu-id="dfe02-112">Use an xpath to pull back all the nodes in the schema that have a _locID attribute.</span></span>  
  
  -   <span data-ttu-id="dfe02-113">リソースで、_locID の値によりインデックス化された文字列を検索します。</span><span class="sxs-lookup"><span data-stu-id="dfe02-113">Look up the resources for a string indexed by the value of the _locID.</span></span>  
  
  -   <span data-ttu-id="dfe02-114">ノードのテキストを結果に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="dfe02-114">Replace the node text with the result.</span></span>  
  
  <span data-ttu-id="dfe02-115">2 つ目のオプションのサンプル コードを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="dfe02-115">The following is sample code for the second option:</span></span>  
  
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