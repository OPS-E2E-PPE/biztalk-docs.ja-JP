---
title: "ルート ノード |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2161f877-835e-434d-a8d1-2426f977d60e
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2070982a6bca09e8bffb2bcc88e5997360c86851
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="root-nodes"></a>ルート ノード
BizTalk エディターでの子ノード、**スキーマ**ノードと呼ばれる**ルート**ノード。 **ルート**ノードは、特殊な種類の**レコード**ノード、通常よりも、いくつかのプロパティがあると**レコード**ノード。 **ルート**ノードが、スキーマによって示されるドキュメントの種類を表し、必要に応じて変更することができます。 たとえば、名前を変更できます、**ルート**ノードが purchaseOrder、orderAcknowledgment、shipnotice など、スキーマを表すメッセージの種類を説明するようにします。  
  
 BizTalk エディターで、新しい XML スキーマを作成するときに、**スキーマ**ノードおよび**ルート**ノードが自動的に作成されます。 追加作成することができます**ルート**ノードの子として、**スキーマ**ノードです。 これにより、単一の XML スキーマ定義 (XSD) 言語表記でスキーマのライブラリを作成します。 たとえば、スキーマのライブラリを作成して、注文書の送信やさまざまなルート ノードの名前付け (purchaseOrder、orderAcknowledgment、shipNotice など) に関連するメッセージのスキーマを表すことができます。  
  
## <a name="xsd-representation"></a>XSD 表記  
 次の例に対応するスキーマの XSD 表記で、行を示しています、**ルート**スキーマのツリー ビュー内のノードです。  
  
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
  
 **ルート**ノード BizTalk エディターでは対象のメッセージの対応する XML インスタンス内の主な要素を表します。 たとえば場合、**ルート**特定のスキーマのノードの名前が purchaseOrder に、対応する XSD 表記は、次の大まかな構造です。  
  
```  
<?xml version="1.0" encoding="utf-16" ?>  
<xs:schema xmlns="http://BizTalk_Server_Project1.Schema2"  
    xmlns:b="http://schemas.microsoft.com/BizTalk/2003"  
    targetNamespace="http://BizTalk_Server_Project1.Schema2"  
    xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:element name="">  
        <xs:complexType>   
            ...  
        </xs:complexType>   
    </xs:element>  
</xs:schema>  
```  
  
 対応する XML インスタンス メッセージには、次の基本構造が必要です。  
  
```  
<?xml version="1.0"?>  
<purchaseOrder ...>  
    ...  
</purchaseOrder>  
```  
  
> [!NOTE]
>  ルート ノードがない可能性があります**フィールド**属性。 **フィールド**に属性が追加されている、**ルート**ノードは、スキーマには保存されません。  
  
## <a name="see-also"></a>参照  
-  [スキーマの BizTalk 表記](../core/biztalk-representation-of-schemas.md)   
-  [ノードのプロパティ](../core/node-properties.md)   
-  **レコード ノードのプロパティ**  [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
-  [ノードのプロパティを設定する方法](../core/how-to-set-node-properties.md)