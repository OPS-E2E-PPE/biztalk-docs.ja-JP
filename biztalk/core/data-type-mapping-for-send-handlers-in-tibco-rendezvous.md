---
title: TIBCO Rendezvous のデータ型のマッピングの送信ハンドラーの |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fa1a9233-8781-45a8-9c55-a18ecaa0f456
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bda336d149d373477b26efeb2e4b05de4aac7554
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015241"
---
# <a name="data-type-mapping-for-send-handlers-in-tibco-rendezvous"></a>TIBCO Rendezvous での送信ハンドラーのデータ型マッピング
XML スキーマの種類は、TIBCO Rendezvous に型情報 (xsi:type=) が提供されている場合にのみ、TIBCO Rendezvous の型にマップできます。 サポートされない型はすべて、可能な場合は、文字列にマップされます。 マップできない場合、またはポート構成でこのオプションが無効である場合は、エラーが生成されます。  
  
## <a name="xml-schema-to-tibco-rendezvous-data-type-mapping"></a>XML スキーマと TIBCO Rendezvous のデータ型マッピング  
 次の表に、XML スキーマの種類から TIBCO Rendezvous の型への可能なマッピングを示します。  
  
|XML の種類|TIBCO RV 型|  
|--------------|-------------------|  
||TIBRVMSG_MSG|  
||TIBRVMSG_XML|  
|xsd:dateTime|TIBRVMSG_DATETIME|  
|xsd:boolean|TIBRVMSG_BOOL|  
|xsd:byte|TIBRVMSG_I8|  
|xsd:short|TIBRVMSG_I16|  
|xsd:int|TIBRVMSG_I32|  
|xsd:long|TIBRVMSG_I64|  
|xsd:unsignedByte|TIBRVMSG_U8|  
|xsd:unsignedShort|TIBRVMSG_U16|  
|xsd:unsignedInt|TIBRVMSG_U32|  
|xsd:unsignedLong|TIBRVMSG_U64|  
|xsd:float|TIBRVMSG_F32|  
|xsd:double|TIBRVMSG_F64|  
|tibrv:IPaddress|TIBRVMSG_IPADDR32|  
|tibrv:IPport|TIBRVMSG_IPPORT16|  
|tibrv:arrayOfByte|TIBRVMSG_I8ARRAY|  
|tibrv:arrayOfShort|TIBRVMSG_I16ARRAY|  
|tibrv:arrayOfInt|TIBRVMSG_I32ARRAY|  
|tibrv:arrayOfLong|TIBRVMSG_I64ARRAY|  
|tibrv:arrayOfUnsignedByte|TIBRVMSG_U8ARRAY|  
|tibrv:arrayOfUnsignedShort|TIBRVMSG_U16ARRAY|  
|tibrv:arrayOfUnsignedInt|TIBRVMSG_U32ARRAY|  
|tibrv:arrayOfUnsignedLong|TIBRVMSG_U64ARRAY|  
|tibrv:arrayOfFloat|TIBRVMSG_F32ARRAY|  
|tibrv:arrayOfDouble|TIBRVMSG_F64ARRAY|  
|その他 - デバッグ メッセージあり|TIBRVMSG_STRING (ログ)|  
  
 BizTalk Adapter for TIBCO Rendezvous はスキーマにアクセスできないので、BizTalk Server から TIBCO Rendezvous に送信する場合は、すべての非文字列フィールドについて XML `xsi:type` 属性を提供する必要があります。 アダプターはこの情報を使用して、TIBCO Rendezvous メッセージに、適切なメッセージ フィールドの型を生成します。  
  
## <a name="message-mapping-example"></a>メッセージ マッピングの例  
 次に、BizTalk Server から TIBCO Rendezvous へのメッセージ マッピングの例を示します。 型のマップ方法の詳細は、データ型マッピングの表を参照してください。  
  
```  
<ns:QuoteUpdate xmlns:xsi http://www.w3.org/2001/XMLSchema-instance"  
xmlns:xsd http://www.w3.org/2001/XMLSchema"  
xmlns:tibrv="http://schemas.microsoft.com/TibcoRendezvous/Types"  
xmlns:ns="some namespace for this message [value not important, unless the schema is also used for receive ports]">  
  
<ns:SymbolName id=1 xsi:type="xsd:string">MSFT</ns:SymbolName>  
  
<ns:LastTrade id=2 xsi:type="xsd:double">28.40</ns:LastTrade>   
<ns:DayLow id=3 xsi:type="xsd:double">28.25</ns:DayLow>  
  
```  
  
|||  
|-|-|  
|`<ns:DayHigh`|`id=4 xsi:type="xsd:double">28.40</ns:DayHigh>`|  
|`<ns:MarketCap`|`id=10>262575234981</ns:MarketCap>`|  
|`<ns:Bids`|`id=100 xsi:type="tibrv:message">`|  
  
```  
<ns:TopBids id=1 xsi:type="tibrv:arrayOfDouble">  
<item>28.40</item>  
<item>28.39</item>  
<item>28.39</item>  
<item>28.39</item>  
<item>28.38</item>  
  
</ns:TopBids>  
  
<ns:BidsSize id=2 xsi:type="tibrv:arrayOfLong">  
<item>500</item>  
<item>1000</item>  
<item>100</item>  
<item>100</item>  
<item>2000</item>  
  
</ns:BidsSize>  
</ns:Bids>  
</ns:QuoteUpdate>  
  
```  
  
 前のメッセージが構造化された TIBCO Rendezvous メッセージとして生成されると、6 つのフィールドがある最上位 TibcoMsg インスタンスになります。 最後のフィールドは、配列型の 2 つのフィールドで構成されるサブメッセージです (アイテム要素は TIBCO Rendezvous メッセージ フィールドにはマップされず、`array` 型のメッセージ フィールドの要素としてマップされます)。 型の仕様を持たない、MarketCap フィールドは文字列フィールドのメッセージとして送信されます。  
  
## <a name="see-also"></a>参照  
 [TIBCO Rendezvous 送信ハンドラーの作成](../core/creating-tibco-rendezvous-send-handlers.md)