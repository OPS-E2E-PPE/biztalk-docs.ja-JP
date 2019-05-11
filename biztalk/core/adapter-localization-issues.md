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
ms.openlocfilehash: d5ebd852d51671d0b3b2312db74433f0af10a974
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361396"
---
# <a name="adapter-localization-issues"></a><span data-ttu-id="44761-102">アダプターのローカライズに関する問題</span><span class="sxs-lookup"><span data-stu-id="44761-102">Adapter Localization Issues</span></span>
<span data-ttu-id="44761-103">次のトピックでは、カスタム アダプターを開発するときに発生する可能性のあるローカライズに関する問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="44761-103">The following topics cover localization issues that you may encounter when developing custom adapters.</span></span>  
  
## <a name="xsd-issues"></a><span data-ttu-id="44761-104">XSD の問題点</span><span class="sxs-lookup"><span data-stu-id="44761-104">XSD Issues</span></span>  
 <span data-ttu-id="44761-105">アダプター フレームワークを使用すると、アダプター開発者は、XML スキーマ定義 (XSD) スキーマを使用したアダプターのプロパティ ページを実装できます。</span><span class="sxs-lookup"><span data-stu-id="44761-105">By using the Adapter Framework, adapter developers can implement adapter property pages with XML Schema Definition (XSD) schemas.</span></span>  
  
 <span data-ttu-id="44761-106">アダプターにグローバリゼーションまたはローカライズの要件がないかどうかは、内の XSD スキーマ文字列をハードコーディングできます、 **IDynamicAdapterConfig:GetConfigSchema**関数。</span><span class="sxs-lookup"><span data-stu-id="44761-106">If your adapter has no globalization or localization requirements, then you can hard code the XSD schema string inside the **IDynamicAdapterConfig:GetConfigSchema** function.</span></span>  
  
 <span data-ttu-id="44761-107">アダプターにグローバリゼーションまたはローカライズの要件がある場合は、2 つの方法のいずれかで、XSD スキーマを実装できます。</span><span class="sxs-lookup"><span data-stu-id="44761-107">If your adapter has globalization or localization requirements, you can implement the XSD schema in one of two ways.</span></span>  
  
- <span data-ttu-id="44761-108">デザイン時バイナリの外部の個別の XSD ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="44761-108">Use separate XSD files outside the design-time binary.</span></span> <span data-ttu-id="44761-109">マニフェスト リソース スキーマのテキスト全体を作成します。</span><span class="sxs-lookup"><span data-stu-id="44761-109">Make the whole text of the schema a manifest resource.</span></span>  
  
- <span data-ttu-id="44761-110">リソースから、プロパティの名前と説明を動的に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="44761-110">Dynamically replace the Property Names and Description from the resource:</span></span>  
  
  -   <span data-ttu-id="44761-111">_LocID をローカライズする各要素に追加します。</span><span class="sxs-lookup"><span data-stu-id="44761-111">Add a _locID to each element that you want to localize.</span></span>  
  
  -   <span data-ttu-id="44761-112">Xpath を使用して、_locID 属性を持つスキーマ内のすべてのノードを取得します。</span><span class="sxs-lookup"><span data-stu-id="44761-112">Use an xpath to pull back all the nodes in the schema that have a _locID attribute.</span></span>  
  
  -   <span data-ttu-id="44761-113">_LocID の値によってインデックス付けされた文字列のリソースを検索します。</span><span class="sxs-lookup"><span data-stu-id="44761-113">Look up the resources for a string indexed by the value of the _locID.</span></span>  
  
  -   <span data-ttu-id="44761-114">ノードのテキストを結果に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="44761-114">Replace the node text with the result.</span></span>  
  
  <span data-ttu-id="44761-115">2 番目のオプションのサンプル コードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="44761-115">The following is sample code for the second option:</span></span>  
  
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