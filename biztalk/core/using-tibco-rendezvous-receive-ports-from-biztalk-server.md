---
title: 受信スキーマと TIBCO Rendezvous アダプターを持つイベントを処理 |Microsoft ドキュメント
description: スキーマの操作が TIBCO Rendezvous の受信側と biztalk TIBCO Rendezvous の BizTalk アダプターを使用してイベント処理
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 26cb20f9-4d26-48f6-a5e9-a51348a56538
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbbae69dc1b7df1f5675442dde544a444cec02fb
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24014097"
---
# <a name="using-tibco-rendezvous-receive-ports-from-biztalk-server"></a>BizTalk Server からの TIBCO Rendezvous 受信ポートの使用

## <a name="overview"></a>概要
受信ポートを使用するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に受信メッセージのスキーマを提供します。 受信ポートは、サブジェクト名の特定のセットを待機するように構成されます。 受信ポートでは、オプションのワイルドカード文字と共にサブジェクト名を使用して、複数のサブジェクト名が照合されます。 ユーザーは、特定の文字列に一致する可能性のあるサブジェクトごとに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションで異なるポート操作を定義します。  
  
> [!NOTE]
>  アダプターは、オーケストレーションとメッセージング シナリオの両方をサポートします。  
  
## <a name="define-schemas"></a>スキーマを定義します。  
 たとえば、ポートが、サブジェクト名をリッスンするように構成されている場合**STOCK です。マーケットです。インデックス。 >** ('**>**' は、右側に何を意味するワイルドカード文字)、などのサブジェクト名の操作を定義する有効なことになります**STOCK です。マーケットです。インデックスです。NYSE です。SP500**、 **STOCK です。マーケットです。インデックスです。TSX.TSX60**のようにします。 説明している方法を使用してメッセージがアダプターにより生成[TIBCO Rendezvous の受信ハンドラーのデータ型マッピング](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)、ルート要素名と名前空間のリッスンに基づくを生成および名と受信したメッセージの件名それぞれのサブジェクト名します。  
  
 前の例では、アダプターには、SP500 イベントは、次のようなメッセージが生成されます。  
  
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

## <a name="event-processing"></a>イベント処理
Microsoft BizTalk Adapter for TIBCO Rendezvous は、複数のスレッドのキューからイベントをディスパッチします。 BizTalk Server の受信場所 1 つの TIBCO Rendezvous イベント キュー、およびそのディスパッチャー スレッドのプールに関連付けられています。  
  
### <a name="memory-use-and-errors"></a>メモリの使用とエラー  
 イベントの処理中、アダプターは使用されるリソースを監視します。 メモリの使用量が上限 Watermark を超えると、アダプターはメモリ使用量が下限 Watermark に達するまでイベントのディスパッチを停止します。 これにより TIBCO Rendezvous メッセージが未証明メッセージとして失われる場合があることに注意してください (TIBCO RV コンシューマーは 60 秒経過したらメッセージをキューから削除します)。 このデータ損失はエラーとして報告されます。 アダプターが TIBCO Rendezvous のシステム通知 NO_MEMORY メッセージを受け取ったら、メッセージは既に失われています。  
  
 BizTalk Adapter for TIBCO Rendezvous は状態を保持しており、状態に応じて異なるタスクを実行します。 BizTalk メッセージ エンジンがエラーを報告し、アダプターが証明されたリスナーとして構成されている場合、アダプターは TIBCO Rendezvous にエラーを報告してメッセージを再送信できるようにします。  
  
## <a name="see-also"></a>参照  
 [TIBCO Rendezvous の概念](../core/tibco-rendezvous-concepts.md)   
 [TIBCO Rendezvous でのデータ型マッピングの受信ハンドラー](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)   
 [TIBCO Rendezvous 受信ハンドラーの作成](../core/creating-tibco-rendezvous-receive-handlers.md)