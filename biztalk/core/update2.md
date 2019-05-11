---
title: Update2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 770c9ebb-df3a-428f-be18-b36535352f8d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c090d11686babacfcb854782484b689dff2102e0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398618"
---
# <a name="update"></a>更新
`Update`要素を使用して、イベントからデータを抽出し、関連する BAM アクティビティにインポートします。  
  
## <a name="format"></a>形式  
 使用する、`Update`要素の場合、列名と型の両方を指定する必要があります、**式**要素の 1 つ以上含む**操作**1 つの文字列値に評価される要素。  
  
```  
<ic:Update DataItemName="Name" Type="Type">  
  <ic:Expression>  
    <!-- one or more Operation elements -->  
  </ic:Expression>  
</ic:Update>  
```  
  
### <a name="attributes"></a>属性  
  
|属性名|説明|  
|--------------------|-----------------|  
|[ColumnName]|BAM のアクティビティ チェックポイントの名前。 これは、抽出されたデータで更新されるチェックポイントです。|  
|型|のチェックポイントの BAM データ型次のいずれかを指定する必要があります。<br /><br /> -   NVARCHAR<br />-DATETIME<br />-INT<br />-FLOAT|  
  
## <a name="remarks"></a>コメント  
 次の操作がサポートされていない、`Update`式。  
  
-   And  
  
-   [等しい]  
  
## <a name="example"></a>例  
 次の例では、 **GetContextProperty** WF の操作を使用して、取得、 **EventTime**プロパティ。 としてこの値が格納される、 **DATETIME** BAM アクティビティの"StartOrderProcessing"データ項目の種類。  
  
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
 [インターセプター OnEvent 要素](../core/interceptor-onevent-element.md)