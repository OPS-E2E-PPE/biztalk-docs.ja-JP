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
# <a name="adapter-localization-issues"></a>アダプターのローカライズに関する問題
次のトピックでは、カスタム アダプターを開発するときに発生する可能性のあるローカライズに関する問題について説明します。  
  
## <a name="xsd-issues"></a>XSD の問題点  
 アダプター フレームワークを使用すると、アダプター開発者は、XML スキーマ定義 (XSD) スキーマを使用したアダプターのプロパティ ページを実装できます。  
  
 アダプターにグローバリゼーションまたはローカライズの要件がないかどうかは、内の XSD スキーマ文字列をハードコーディングできます、 **IDynamicAdapterConfig:GetConfigSchema**関数。  
  
 アダプターにグローバリゼーションまたはローカライズの要件がある場合は、2 つの方法のいずれかで、XSD スキーマを実装できます。  
  
- デザイン時バイナリの外部の個別の XSD ファイルを使用します。 マニフェスト リソース スキーマのテキスト全体を作成します。  
  
- リソースから、プロパティの名前と説明を動的に置き換えます。  
  
  -   _LocID をローカライズする各要素に追加します。  
  
  -   Xpath を使用して、_locID 属性を持つスキーマ内のすべてのノードを取得します。  
  
  -   _LocID の値によってインデックス付けされた文字列のリソースを検索します。  
  
  -   ノードのテキストを結果に置き換えます。  
  
  2 番目のオプションのサンプル コードを次に示します。  
  
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