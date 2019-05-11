---
title: 候補リスト操作のメッセージのスキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- picklist operations, message schemas for
- picklist operations, message actions
- picklist operations, message
ms.assetid: c0b62a8c-5a68-47ea-8676-1580601b5ec9
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5748a293c8f9dc4e4059ebdecda9527bb0bb63ee
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371405"
---
# <a name="message-schema-for-picklist-operations"></a>候補リスト操作のメッセージ スキーマ
候補リストは、ビジネス コンポーネントで特別なフィールド型です。 これらは、ユーザーが 1 つの値の割り当てを選択ことがあります値のコレクションを表します。 候補リストは、さまざまな種類です。 候補リストとその型の詳細については、Siebel のドキュメントを参照してください。  
  
 列挙型の候補リストとして、アダプターによって表示された候補リストの種類、静的の境界付けられた候補リストのいずれかでデザイン時にアダプターによって生成されたメタデータの種類。 これには、実行時に候補リストの種類を指定する必要があります値の静的なセットが含まれています。  静的範囲指定された候補リストの値を指定する、中には、常に、セットに属している値を指定する必要があります。  
  
 次の例では、境界付けられた候補リストの静的な型のスキーマを示します。  
  
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
  
 [<] = Business component の候補リストのフィールド名  
  
 境界付けられた候補リストの静的な型のプロキシのエクスペリエンスを次に示します。  
  
```  
[BC]InsertRecord[] insertRecs = new [BC]InsertRecord[1];  
insertRecs[0] = new [BC]InsertRecord();  
insertRecs[0].[BC_STATIC_PICKLIST_FIELD] = [BC_PICKLIST_FIELD_NAME]OptionalPickListType.value1;  
```  
  
 [BC_STATIC_PICKLIST_FIELD] ビジネス継続性の境界付けられた候補リストの静的フィールドを =  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk Adapter for Siebel eBusiness Applications のメッセージ スキーマ](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)