---
title: スキーマ ノードの |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7ea02c2a-ee00-4f44-9086-83d7ac4a8832
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c14658eb48e4031345ec8ce3e9618ef601f5f5ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396936"
---
# <a name="schema-node"></a>スキーマ ノード

## <a name="overview"></a>概要
BizTalk エディターでは、スキーマ階層の最上位は常に、**スキーマ**ノードで、名前を変更することはできません。 **スキーマ**ノードに対応、**スキーマ**スキーマの XML スキーマ定義 (XSD) 言語表記での要素。  
  
> [!NOTE]
>  BizTalk エディターで、**スキーマ**ノードが文字列で表される\<スキーマ\>スキーマ ツリー ビューで。  
  
 一般のプロパティ、**スキーマ**ノードの属性に対応、**スキーマ**要素は、スキーマの XSD 表記でします。 ノードのプロパティの詳細については、次を参照してください。[ノード プロパティ](../core/node-properties.md)します。 プロパティの参照情報について、**スキーマ**ノードを参照してください、**スキーマのノード プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。
  
 BizTalk エディターで、新しい XML スキーマを作成するときに、**スキーマ**ノードと 1 つ**ルート**ノードが自動的に作成されます。  
  
## <a name="xsd-representation"></a>XSD 表記  
 太字に対応するスキーマの XSD 表記での行で、次の例は、 **\<スキーマ\>** スキーマのツリー ビューでノード。  
  
```  
<?xml version="1.0" encoding="utf-16" ?>  
<xs:schema xmlns="http://BizTalk_Server_Project1.Schema2"  
    xmlns:b="http://schemas.microsoft.com/BizTalk/2003"  
    targetNamespace="http://BizTalk_Server_Project1.Schema2"  
    xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:element name="Root">  
        <xs:complexType />  
    </xs:element>  
</xs:schema>  
```  
  
## <a name="see-also"></a>参照  
 [スキーマの BizTalk 表記](../core/biztalk-representation-of-schemas.md)   
 [ノードのプロパティ](../core/node-properties.md)   
 [ノードのプロパティの設定](../core/how-to-set-node-properties.md)