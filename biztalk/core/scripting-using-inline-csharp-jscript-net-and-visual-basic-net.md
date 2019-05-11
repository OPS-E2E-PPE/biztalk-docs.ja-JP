---
title: インラインを使用したスクリプトをC#、JScript .NET、および Visual Basic .NET |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scripting functoids, JScript
- Scripting functoids, warnings
- Scripting functoids, Visual Basic .NET
- Scripting functoids, inline C#
- Scripting functoids, .NET
ms.assetid: dda60024-58bd-483f-a750-31b21059eded
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74eca3ecd01af709b6b8c7aefe250e02679445a1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65251222"
---
# <a name="scripting-using-inline-c-jscript-net-and-visual-basic-net"></a>インライン c#、JScript .NET、および Visual Basic .NET を使用するスクリプト
インライン スクリプトは、いない可能性がある他の場所を使用する、アプリケーションでカスタム コードに便利です。  
  
 BizTalk は、マップを定義する拡張スタイル シート言語変換 (XSLT) スタイル シートでインライン スクリプトを保存します。 このため、インライン スクリプトは、他の XSLT スタイル シート スクリプトと同じ名前空間を使用する場合があります。 次の表では、使用可能な名前空間を示します。  
  
|Namespace|説明|  
|---------------|-----------------|  
|システム|System クラスです。|  
|System.Collection|コレクション クラスです。|  
|System.Text|テキスト クラスです。|  
|System.Text.RegularExpressions|正規表現クラス。|  
|System.Xml|コア XML クラスです。|  
|System.Xml.Xsl|XSLT クラスです。|  
|System.Xml.Xpath|XPath クラスです。|  
|Microsoft.VisualBasic|Visual Basic スクリプト クラスです。|  
  
 名前空間およびデータの種類の詳細については、検索"XSLT スタイル シートのスクリプトを使用して\<msxsl:script\>」と「system.xml.xsl.xslcompiledtransform」で、.NET Framework のコレクション。  
  
> [!CAUTION]
>  同じメソッド シグネチャを複数回使用しないでください。 複数のスクリプト functoid には、同じメソッド シグネチャがある、BizTalk は最初の実装を選択し、他は無視されます。  
  
 1 回限りのスクリプトの便利なだけインライン スクリプトもスクリプトの数の間で使用するためのグローバル変数を宣言する場合に便利です。 など、C#インライン スクリプトでは、次の任意のクラスの外部でのコード行に配置することです。  
  
```  
ArrayList statusList = new ArrayList();  
```  
  
 これを作成、 **ArrayList**、`statusList`マップ内のすべてのインライン スクリプトを使用できます。  
  
 サンプル インライン スクリプトでは、次を参照してください。 [XML ツール (BizTalk Server Samples フォルダー)](../core/xml-tools-biztalk-server-samples-folder.md)します。  
  
## <a name="see-also"></a>参照  
 [スクリプト Functoid](../core/scripting-functoid.md)   
 [外部アセンブリを使用するスクリプト](../core/scripting-using-external-assemblies.md)   
 [使用してインライン XSLT および XSLT 呼び出しテンプレート スクリプト](../core/scripting-using-inline-xslt-and-xslt-call-templates.md)   
 [マップにスクリプト Functoid を追加する方法](../core/how-to-add-scripting-functoids-to-a-map.md)   
 [スクリプト Functoid の構成方法](../core/how-to-configure-the-scripting-functoid.md)