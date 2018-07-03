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
# <a name="adapter-localization-issues"></a>アダプターのローカライズに関する問題
ここでは、カスタム アダプターを作成するときに発生する可能性のあるローカライズに関する問題を取り上げます。  
  
## <a name="xsd-issues"></a>XSD の問題点  
 アダプターの開発者は、アダプター フレームワークを使用して、アダプターのプロパティ ページを XML スキーマ定義 (XSD) スキーマで実装できます。  
  
 アダプターにグローバリゼーションまたはローカライズの要件がないかどうかは、内の XSD スキーマ文字列をハードコーディングできます、 **IDynamicAdapterConfig:GetConfigSchema**関数。  
  
 アダプターにグローバリゼーションまたはローカライズの要件がある場合は、2 つの方法のうちのいずれかを使用して XSD スキーマを実装できます。  
  
- デザイン時バイナリの外で個別の XSD ファイルを使用します。 スキーマのテキスト全体をマニフェスト リソースにします。  
  
- プロパティ名と説明をリソースから動的に置き換えます。  
  
  -   _locID をローカライズする各要素に追加します。  
  
  -   xpath を使用して、_locID 属性を持つスキーマ内のすべてのノードを返します。  
  
  -   リソースで、_locID の値によりインデックス化された文字列を検索します。  
  
  -   ノードのテキストを結果に置き換えます。  
  
  2 つ目のオプションのサンプル コードを以下に示します。  
  
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