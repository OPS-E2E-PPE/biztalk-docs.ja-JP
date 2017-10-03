---
title: "Update2 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 770c9ebb-df3a-428f-be18-b36535352f8d
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4376cae94e91f462974c626a57170b80b0117ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="update"></a>Update
`Update` 要素は、イベントからデータを抽出して、関連する BAM アクティビティにインポートするために使用します。  
  
## <a name="format"></a>Format  
 使用する、`Update`要素、列名と型の両方を指定する必要があります、**式**要素が 1 つ以上含む**操作**要素 1 つの文字列値に評価されます。  
  
```  
<ic:Update DataItemName="Name" Type="Type">  
  <ic:Expression>  
    <!-- one or more Operation elements -->  
  </ic:Expression>  
</ic:Update>  
```  
  
### <a name="attributes"></a>属性  
  
|属性名|Description|  
|--------------------|-----------------|  
|[ColumnName]|BAM アクティビティのチェックポイント名です。 これは、抽出されたデータで更新されるチェックポイントです。|  
|型|チェックポイントの BAM データ型です。次のいずれかを指定する必要があります。<br /><br /> -NVARCHAR<br />-DATETIME<br />-INT<br />FLOAT|  
  
## <a name="remarks"></a>解説  
 次の演算は、`Update` 式ではサポートされていません。  
  
-   And  
  
-   [等しい]  
  
## <a name="example"></a>例  
 次の例で、 **GetContextProperty** WF 操作は、取得に使用される、 **EventTime**プロパティです。 この値として保存されます、 **DATETIME** BAM アクティビティの"StartOrderProcessing"データ項目の種類。  
  
```  
<ic:Update DataItemName="StartOrderProcessing" Type="DATETIME">  
  <ic:Expression>  
    <wf:Operation Name="GetContextProperty">  
      <wf:Argument>EventTime</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:Update>  
```  
  
## <a name="see-also"></a>参照  
 [インターセプタ OnEvent 要素](../core/interceptor-onevent-element.md)