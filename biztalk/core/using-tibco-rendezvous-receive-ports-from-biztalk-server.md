---
title: "使用して TIBCO Rendezvous 受信ポートを BizTalk Server から |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: receive ports, using from BizTalk Server
ms.assetid: 26cb20f9-4d26-48f6-a5e9-a51348a56538
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b8e0999362844570bb56cfbc488e5fd5775e286
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-tibco-rendezvous-receive-ports-from-biztalk-server"></a>BizTalk Server からの TIBCO Rendezvous 受信ポートの使用
受信ポートを使用するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に受信メッセージのスキーマを提供します。 受信ポートは、サブジェクト名の特定のセットを待機するように構成されます。 受信ポートでは、オプションのワイルドカード文字と共にサブジェクト名を使用して、複数のサブジェクト名が照合されます。 ユーザーは、特定の文字列に一致する可能性のあるサブジェクトごとに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションで異なるポート操作を定義します。  
  
> [!NOTE]
>  アダプターは、オーケストレーションとメッセージ シナリオの両方をサポートしています。  
  
## <a name="defining-schemas"></a>スキーマの定義  
 たとえば、ポートが、サブジェクト名をリッスンするように構成されている場合**STOCK です。マーケットです。インデックス。 >** ('**>**' は、右側に何を意味するワイルドカード文字)、などのサブジェクト名の操作を定義する有効なことになります**STOCK です。マーケットです。インデックスです。NYSE です。SP500**、 **STOCK です。マーケットです。インデックスです。TSX.TSX60**のようにします。 説明している方法を使用してメッセージがアダプターにより生成[TIBCO Rendezvous の受信ハンドラーのデータ型マッピング](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)、ルート要素名と名前空間のリッスンに基づくを生成および名と受信したメッセージの件名それぞれのサブジェクト名します。  
  
 前の例では、アダプターには、SP500 イベントの次のようなメッセージが生成されます。  
  
```  
<ns:STOCK.MARKET.INDICES.NYSE.SP500 xmlns:ns='   
http://schemas.microsoft.com/TibcoRendezvous/Types/  
STOCK.MARKET.INDICES.NYSE.GTWILDCARD'  
xmlns:tibrv=' http://schemas.microsoft.com/TibcoRendezvous/Types' … >  
<message body>  
</ns: STOCK.MARKET.INDICES.NYSE.SP500>  
  
```  
  
 同じ規則を使用するスキーマを定義する必要があります。 例:  
  
```  
<xsd:schema  
targetNamespace='   
  
http://schemas.microsoft.com/TibcoRendezvous/Types/STOCK.MARKET.INDICES.N  
YSE.GTWILDCARD'  
xmlns:xsd=' http://www.w3.org/2001/XMLSchema'  
xmlns:tibrv=' http://schemas.microsoft.com/TibcoRendezvous/Types'>  
xmlns:b="http://schemas.microsoft.com/BizTalk/2003"  
<xsd:element name='STOCK.MARKET.INDICES.NYSE.SP500'>  
  
 <xs:annotation>  
   <xs:appinfo>  
     <b:recordInfo rootTypeName="STOCK_MARKET_INDICES_NYSE_SP500" />  
   </xs:appinfo>  
  
 </xs:annotation>  
<xsd:complexType>  
<SP500 message definitions goes here>  
</xsd:complexType>  
<xsd:element name='STOCK.MARKET.INDICES.TSX.TSX60'>  
  
 <xs:annotation>  
   <xs:appinfo>  
     <b:recordInfo rootTypeName="STOCK_MARKET_INDICES_TSX_TSX60" />  
   </xs:appinfo>  
  
 </xs:annotation>  
<xsd:complexType>  
<TSX60 message definitions goes here>  
</xsd:complexType>  
  
```  
  
 使用に注意してください、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] **recordInfo/rootTypeName**注釈。 これは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]/BizTalk Integration に対して、ドットを含む名前ではなく、生成された .NET Framework の種類の名前を使用するように指定しています。 任意のものを指定できます。 例では、ドットはアンダースコアに置き換えられています。  
  
> [!NOTE]
>  ドットにより、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 開発ツールによって無効な名前が生成されます。  
  
## <a name="see-also"></a>参照  
 [TIBCO Rendezvous でのデータ型マッピングの受信ハンドラー](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)   
 [作成元の TIBCO Rendezvous 受信ハンドラー](../core/creating-tibco-rendezvous-receive-handlers.md)