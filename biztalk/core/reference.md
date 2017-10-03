---
title: "リファレンス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b916c55a-c84c-4008-8927-f8e584c36fe9
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3e32145e2340a4d86a6893db3e9209b79c2b5e7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="reference"></a>リファレンス
**参照**BAM アクティビティを 1 つまたは複数のリレーションシップを追加する要素を使用できます。 この機能は、主キー、ID、URL などのポインタを関連するメッセージに追加する必要がある場合に便利です。 たとえば、出荷バッチへの参照を発注アクティビティに保存できます。  
  
## <a name="format"></a>Format  
 `Reference`要素では、両方がサポートする、**データ**と**LongData**を BAM アクティビティにアタッチするデータを指定する式を含む子要素です。 任意の組み合わせを使用する**データ**と**LongData**を追跡要件を満たすようにします。  
  
### <a name="attributes"></a>属性  
  
|属性名|Description|  
|--------------------|-----------------|  
|名前|BAM アクティビティに追加されるリレーションシップの名前です。|  
|型|BAM アクティビティに追加されるリレーションシップの種類を指定する任意の文字列です。 任意の文字列だけでなく、以下の定義済みの BAM の種類もサポートされています。<br /><br /> -BizTalkService<br />-MessageID<br />-アクティビティ<br />-DocumentUrl<br />-InstanceID<br /><br /> 定義済みの BAM 参照型の詳細については、次を参照してください。[参照プロパティ](http://go.microsoft.com/fwlink/?LinkId=119601)です。|  
  
### <a name="child-elements"></a>子要素  
  
|実行状態|Description|  
|----------------------|-----------------|  
|data|BAM アクティビティに追加される最大 128 文字の文字列データを抽出する方法を指定します。|  
|LongData|BAM アクティビティに追加される任意の長さの文字列データを抽出する方法を指定します。|  
  
> [!NOTE]
>  A`Reference`要素は、1 つまたは複数を組み合わせることができます**データ**と**LongData**必要に応じて、子要素です。  
  
## <a name="remarks"></a>解説  
 次の一般的な演算は、Reference 式では許可されていません。  
  
-   And  
  
-   [等しい]  
  
## <a name="example"></a>例  
 次のサンプルでは、ワークフローに対して `GetUserData` を使用して、種類が "DocumentUrl" の "Related Document" という参照が作成されます。 ユーザー データの長さは 1,024 文字未満であることが予想されるため、`Data` 要素を格納するために `Expression` 要素が使用されます。  
  
```  
<ic:Reference Name="Related Document" Type="DocumentUrl">  
  <ic:Data>  
    <ic:Expression>  
      <wf:Operation Name="GetUserData" />  
    </ic:Expression>  
  </ic:Data>  
</ic:Reference>  
```  
  
 **参照**要素の組み合わせをサポートしている`Data`と`LongData`要素。 次のサンプルでは、注文書の国名フィールドとメモ フィールドが WCF サービスから取得され、種類が "MyType" の "Long and Short Data" というリレーションシップに書き込まれます。 メモ フィールドには 1,024 文字より長い文字列を入力できるので、式は `LongData` 要素で囲まれています。  
  
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
 [インターセプタ OnEvent 要素](../core/interceptor-onevent-element.md)   
 [EventStream.AddRelatedActivity メソッド](http://go.microsoft.com/fwlink/?LinkId=119602)