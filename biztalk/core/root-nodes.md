---
title: ルート ノード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2161f877-835e-434d-a8d1-2426f977d60e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d8b2746e9e1886b676e656db883579b28898e3d5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019667"
---
# <a name="root-nodes"></a>ルート ノード
BizTalk エディターの子ノード、**スキーマ**ノードと呼ばれる**ルート**ノード。 **ルート**ノードは、特殊な種類の**レコード**ノードで、通常よりもいくつかのプロパティがあると**レコード**ノード。 **ルート**ノードは、スキーマによって示されるドキュメントの種類を表すし、必要に応じて変更できます。 たとえば、変更、**ルート**ノードその it が purchaseOrder、orderAcknowledgment、shipnotice など、スキーマが表すメッセージの種類について説明します。  

 BizTalk エディターで、新しい XML スキーマを作成するときに、**スキーマ**ノードと 1 つ**ルート**ノードが自動的に作成されます。 その他を作成することができます**ルート**ノードの子として、**スキーマ**ノードである 1 つの XML スキーマ定義 (XSD) 言語表記でスキーマのライブラリを作成できます。 たとえば、スキーマのライブラリを作成して、注文書の送信やさまざまなルート ノードの名前付け (purchaseOrder、orderAcknowledgment、shipNotice など) に関連するメッセージのスキーマを表すことができます。  

## <a name="xsd-representation"></a>XSD 表記  
 次の例に対応するスキーマの XSD 表記で、行を示しています、**ルート**スキーマのツリー ビューでノード。  

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

 **ルート**ノード BizTalk エディターでは問題のメッセージの対応する XML インスタンスの主要な要素を表します。 たとえば場合、**ルート**特定のスキーマのノードの名前が purchaseOrder に、対応する XSD 表現が次の大まかな構造です。  

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
>  ルート ノードがない可能性があります**フィールド**属性。 **フィールド**にアタッチされている属性、**ルート**ノードは、スキーマには保存されません。  

## <a name="see-also"></a>参照  
- [スキーマの BizTalk 表記](../core/biztalk-representation-of-schemas.md)   
- [ノードのプロパティ](../core/node-properties.md)   
- **レコード ノードのプロパティ**  [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
- [ノードのプロパティを設定する方法](../core/how-to-set-node-properties.md)
