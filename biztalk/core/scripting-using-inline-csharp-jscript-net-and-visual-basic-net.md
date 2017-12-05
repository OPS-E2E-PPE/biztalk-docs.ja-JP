---
title: "インライン c#、JScript .NET、および Visual Basic .NET を使用するスクリプト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Scripting functoids, JScript
- Scripting functoids, warnings
- Scripting functoids, Visual Basic .NET
- Scripting functoids, inline C#
- Scripting functoids, .NET
ms.assetid: dda60024-58bd-483f-a750-31b21059eded
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe2002bd92342a953406a21e076b801d3e90b938
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="scripting-using-inline-c-jscript-net-and-visual-basic-net"></a>インライン C#、JScript .NET、および Visual Basic .NET を使用するスクリプト
インライン スクリプトは、カスタム コードとして利用できます。ただし、このコードは、アプリケーション以外で使用されることはほとんどありません。  
  
 BizTalk は、マップを定義する XSLT (Extensible Stylesheet Language Transformations) スタイルシートでインライン スクリプトを保存します。 このため、インライン スクリプトは、他の XSLT スタイルシート スクリプトと同じ名前空間を使用できます。 使用可能な名前空間は、次のとおりです。  
  
|名前空間|Description|  
|---------------|-----------------|  
|システム|System クラスです。|  
|System.Collection|コレクション クラスです。|  
|System.Text|テキスト クラスです。|  
|System.Text.RegularExpressions|正規表現のクラスです。|  
|System.Xml|コア XML クラスです。|  
|System.Xml.Xsl|XSLT クラスです。|  
|System.Xml.Xpath|XPath クラスです。|  
|Microsoft.VisualBasic|Visual Basic スクリプト クラスです。|  
  
 名前空間およびデータ型の詳細についてを検索して"XSLT スタイル シートのスクリプトを使用して\<msxsl:script\>"と「system.xml.xsl.xslcompiledtransform」で .NET Framework のコレクション。  
  
> [!CAUTION]
>  同じメソッド シグネチャを複数回使用しないでください。 複数のスクリプト Functoid が同じメソッド シグネチャを持つ場合、BizTalk は、最初の実装を選択し、他の実装を無視します。  
  
 一度のみのスクリプトに役立つだけでなく、インライン スクリプトは、多くのスクリプトで使用するグローバル変数を宣言する場合にも利用できます。 たとえば、C# インライン スクリプトで、クラスの外部に次のコード行を配置できます。  
  
```  
ArrayList statusList = new ArrayList();  
```  
  
 これを作成、 **ArrayList**、`statusList`は、マップ内のすべてのインライン スクリプトを利用できます。  
  
 サンプル インライン スクリプトでは、次を参照してください。 [XML ツール (BizTalk Server Samples フォルダ)](../core/xml-tools-biztalk-server-samples-folder.md)です。  
  
## <a name="see-also"></a>参照  
 [スクリプト Functoid](../core/scripting-functoid.md)   
 [外部アセンブリを使用するスクリプト](../core/scripting-using-external-assemblies.md)   
 [スクリプトを使用してインライン XSLT および XSLT 呼び出しテンプレート](../core/scripting-using-inline-xslt-and-xslt-call-templates.md)   
 [スクリプト Functoid をマップに追加する方法](../core/how-to-add-scripting-functoids-to-a-map.md)   
 [スクリプト Functoid を構成する方法](../core/how-to-configure-the-scripting-functoid.md)