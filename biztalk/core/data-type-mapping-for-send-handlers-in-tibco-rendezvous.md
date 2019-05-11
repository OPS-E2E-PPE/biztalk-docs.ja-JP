---
title: TIBCO Rendezvous のデータ型のマッピングの送信ハンドラーの |Microsoft Docs
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
ms.openlocfilehash: 57987751e57353820f243d914da08f2fc57a73c3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352662"
---
# <a name="data-type-mapping-for-send-handlers-in-tibco-rendezvous"></a>TIBCO Rendezvous での送信ハンドラーのデータ型マッピング
XML スキーマの種類から TIBCO Rendezvous の型へのマッピングは、TIBCO Rendezvous は、型情報を提供します。 場合にのみ実行可能 (xsi:type =)。 サポートされていない型は、可能な場合、文字列にマップされます。 マッピングが可能であれば、ない場合、またはポートの構成で、オプションが無効になっている場合は、エラーが生成されます。  
  
## <a name="xml-schema-to-tibco-rendezvous-data-type-mapping"></a>XML スキーマと TIBCO Rendezvous のデータ型のマッピング  
 次の表では、TIBCO Rendezvous の型を XML スキーマ型から可能なマッピングを示します。  
  
|XML 型|TIBCO RV 型|  
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
|その他 - デバッグ メッセージあり|TIBRVMSG_STRING ログ。|  
  
 BizTalk Adapter for TIBCO Rendezvous は、スキーマへのアクセスがあるない BizTalk Server から TIBCO Rendezvous に送信するときに、ために、XML を指定する必要があります`xsi:type`非文字列フィールドの属性。 アダプターでは、その情報を使用して、TIBCO Rendezvous メッセージに適切なメッセージ フィールドの型を生成します。  
  
## <a name="message-mapping-example"></a>メッセージ マッピングの例  
 次の例では、BizTalk Server から TIBCO Rendezvous へのメッセージのマッピングを示します。 型をマップする方法については、データ型のマッピング テーブルを参照してください。  
  
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
  
 前のメッセージが構造化 TIBCO Rendezvous メッセージとして生成されると、6 つのフィールドの最上位 TibcoMsg インスタンスがあります。 最後のフィールドは、配列型の 2 つのフィールドから成る、サブ メッセージ ('item' 要素は TIBCO Rendezvous メッセージ フィールドには、型の 1 つのメッセージ フィールド内の要素にマップされていない`array`)。 型の指定がない、MarketCap フィールドは、メッセージの文字列フィールドとして送信されます。  
  
## <a name="see-also"></a>参照  
 [TIBCO Rendezvous 送信ハンドラーの作成](../core/creating-tibco-rendezvous-send-handlers.md)