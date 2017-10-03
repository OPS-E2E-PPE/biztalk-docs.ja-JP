---
title: "候補リスト操作のメッセージのスキーマ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- picklist operations, message schemas for
- picklist operations, message actions
- picklist operations, message
ms.assetid: c0b62a8c-5a68-47ea-8676-1580601b5ec9
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d72a16e99e38649a6fb8d74178d2b5da1d059dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-schema-for-picklist-operations"></a>候補リスト操作のメッセージ スキーマ
候補リストは、ビジネス コンポーネントで特別なフィールドの種類です。 これらは、ユーザーが 1 つの値の割り当てを選択ことがあります値のコレクションを表します。 候補リストでは、さまざまな種類です。 候補リストとその種類の詳細については、Siebel のドキュメントを参照してください。  
  
 列挙型の候補リストとして、アダプターで表示されたいずれかの候補リスト型、静的な境界のある候補リストは、デザイン時にアダプターによって生成されたメタデータ内の型。 これには、実行時に候補リストの種類を指定する必要があります値の静的セットが含まれています。  静的範囲指定された候補リストの値を指定する、中には、常に、セットに属している値を指定する必要があります。  
  
 次の例は、静的な境界のある候補リスト型のスキーマを示しています。  
  
```  
<element name="[FIELD_NAME]RequiredPickListType" nillable="true" type="ns1:[FIELD_NAME]RequiredPickListType" />  
<simpleType name="[FIELD_NAME]RequiredPickListType">  
<restriction base="string">  
  <enumeration value="value1" />  
  <enumeration value="value2" />  
  …  
</restriction>  
</simpleType>  
```  
  
 [<] ビジネス コンポーネントの候補リストのフィールド名を =  
  
 静的範囲指定された候補リスト型のプロキシのエクスペリエンスを次に示します。  
  
```  
[BC]InsertRecord[] insertRecs = new [BC]InsertRecord[1];  
insertRecs[0] = new [BC]InsertRecord();  
insertRecs[0].[BC_STATIC_PICKLIST_FIELD] = [BC_PICKLIST_FIELD_NAME]OptionalPickListType.value1;  
```  
  
 [BC_STATIC_PICKLIST_FIELD] ビジネス継続性の境界のある候補リストの静的フィールドを =  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk Adapter for Siebel eBusiness Applications のメッセージ スキーマ](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)