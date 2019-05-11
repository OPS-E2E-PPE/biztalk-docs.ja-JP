---
title: 参照 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b916c55a-c84c-4008-8927-f8e584c36fe9
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 820e4f77da27a1dd934c1a1b842615c9b60158ad
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398014"
---
# <a name="reference"></a>リファレンス
**参照**要素を使用して、BAM アクティビティに 1 つまたは複数のリレーションシップを追加します。 これは、主キー、ID、または URL のようなポインターを関連するメッセージに添付する場合に便利です。 たとえば、発注アクティビティで出荷バッチへの参照を格納する場合があります。  
  
## <a name="format"></a>形式  
 `Reference`要素は、両方をサポート、**データ**と**LongData** BAM アクティビティにアタッチするデータを指定する式を含む子要素。 任意の組み合わせを使用する**データ**と**LongData**追跡要件を満たすためにします。  
  
### <a name="attributes"></a>属性  
  
|属性名|説明|  
|--------------------|-----------------|  
|名前|BAM アクティビティに追加されるリレーションシップの名前。|  
|型|BAM アクティビティに追加されるリレーションシップの種類を指定する任意の文字列。 任意の文字列と次のような BAM の定義済みの種類の両方がサポートされています。<br /><br /> -BizTalkService<br />-MessageID<br />-アクティビティ<br />-   DocumentUrl<br />-InstanceID<br /><br /> 定義済みの BAM 参照型の詳細については、次を参照してください。[参照プロパティ](http://go.microsoft.com/fwlink/?LinkId=119601)します。|  
  
### <a name="child-elements"></a>子要素  
  
|実行状態|説明|  
|----------------------|-----------------|  
|data|BAM アクティビティに追加される最大 128 文字の文字列データを抽出する方法を指定します。|  
|LongData|BAM アクティビティに追加される任意の長さの文字列データを抽出する方法を指定します。|  
  
> [!NOTE]
>  A`Reference`要素は、1 つまたは複数を組み合わせることができます**データ**と**LongData**に応じて子要素。  
  
## <a name="remarks"></a>コメント  
 次の一般的な操作は、Reference 式では使用できません。  
  
-   And  
  
-   [等しい]  
  
## <a name="example"></a>例  
 使用して次のサンプルでは、種類が"DocumentUrl"の"Related Document"をという名前の参照が作成されます`GetUserData`ワークフロー。 ユーザー データが予想されるより少ない 1024 文字の長さにするため、`Data`を格納する要素が使用される、`Expression`要素。  
  
```  
<ic:Reference Name="Related Document" Type="DocumentUrl">  
  <ic:Data>  
    <ic:Expression>  
      <wf:Operation Name="GetUserData" />  
    </ic:Expression>  
  </ic:Data>  
</ic:Reference>  
```  
  
 **参照**要素の組み合わせをサポートして`Data`と`LongData`要素。 次の例で、注文書の国の名前とメモのフィールドが WCF サービスから取得され、種類が"MyType"リレーションシップの"Long and Short Data"に書き込まれます。 式を囲む [メモ] フィールドでは、1,024 個を超える文字をサポートするため、`LongData`要素。  
  
```  
<ic:Reference Name="Long and Short Data" Type="MyType">  
  <ic:Data>  
    <ic:Expression>  
      <ic:Operation Name="Constant">  
        <ic:Argument>Country: </ic:Argument>  
      </ic:Operation>  
      <wcf:Operation Name="XPath">  
        <wcf:Argument>//s:Body//po:Country</wcf:Argument>  
      </wcf:Operation>  
       <ic:Operation Name="Concatenate" />  
    </ic:Expression>  
  </ic:Data>  
  <ic:LongData>  
    <ic:Expression>  
      <ic:Operation Name="Constant">  
        <ic:Argument>Note: </ic:Argument>  
      </ic:Operation>  
      <wcf:Operation Name="XPath">  
        <wcf:Argument>//s:Body//po:Note</wcf:Argument>  
      </wcf:Operation>  
      <ic:Operation Name="Concatenate" />  
    </ic:Expression>  
  </ic:LongData>  
</ic:Reference>  
```  
  
## <a name="see-also"></a>参照  
 [インターセプター OnEvent 要素](../core/interceptor-onevent-element.md)   
 [EventStream.AddRelatedActivity メソッド](http://go.microsoft.com/fwlink/?LinkId=119602)