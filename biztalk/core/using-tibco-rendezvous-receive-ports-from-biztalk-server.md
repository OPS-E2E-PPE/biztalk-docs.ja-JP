---
title: 受信スキーマと TIBCO Rendezvous アダプターを使用したイベントの処理 |Microsoft Docs
description: TIBCO Rendezvous のスキーマ、受信側と biztalk TIBCO Rendezvous の BizTalk アダプターを使用してイベント処理の操作します。
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
ms.openlocfilehash: d459ac2019ccf20edfd718815c7ee789a9089be5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302387"
---
# <a name="using-tibco-rendezvous-receive-ports-from-biztalk-server"></a>使用して TIBCO Rendezvous から BizTalk Server のポートの受信

## <a name="overview"></a>概要
受信ポートを使用するにはスキーマを提供できる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]受信メッセージ。 受信ポートは、特定のサブジェクト名のセットをリッスンするように構成されます。 省略可能なワイルドカード文字を含む複数のサブジェクト名に一致するのにサブジェクト名を使用します。 別のポート操作を定義する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]のオーケストレーションを指定した文字列に一致する可能性のある各サブジェクト。  
  
> [!NOTE]
>  アダプターは、オーケストレーションとメッセージング シナリオの両方をサポートします。  
  
## <a name="define-schemas"></a>スキーマを定義します。  
 たとえば、ポートが、サブジェクト名をリッスンするように構成されている場合**STOCK します。市場です。インデックス。 >** ('**>**' が右側に何を意味するワイルドカード文字)、などのサブジェクト名の操作を定義する有効なことが**STOCK します。市場です。インデックスです。NYSE します。SP500**、**素材です。市場です。インデックスです。TSX.TSX60**など。 アダプターにより生成されるメッセージで説明されている方法を使用した[Data Type Mapping for TIBCO rendezvous 受信ハンドラー](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)、ルート要素名とリッスンに基づく名前空間を生成しますサブジェクト名と受信したメッセージ。それぞれのサブジェクト名します。  
  
 前の例では、アダプターには、SP500 イベントは、次のようなメッセージが生成されます。  
  
```  
<ns:STOCK.MARKET.INDICES.NYSE.SP500 xmlns:ns='   
http://schemas.microsoft.com/TibcoRendezvous/Types/  
STOCK.MARKET.INDICES.NYSE.GTWILDCARD'  
xmlns:tibrv=' http://schemas.microsoft.com/TibcoRendezvous/Types' … >  
<message body>  
</ns: STOCK.MARKET.INDICES.NYSE.SP500>  
  
```  
  
 同じ規則を使用するスキーマを定義する必要があります。 以下に例を示します。  
  
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
  
 使用に注意してください、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] **recordInfo/rootTypeName**注釈。 これに指示する、 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]/BizTalk integration のドットを含む名前ではなく、生成された .NET Framework 型の名前を使用します。 何も指定することができます。 例では、ドットはアンダー スコアに置き換えられます。  
  
> [!NOTE]
>  ドットで生成される無効な名前が発生する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]開発ツール。  

## <a name="event-processing"></a>イベント処理
Microsoft BizTalk Adapter for TIBCO Rendezvous は、複数のスレッドのキューからイベントをディスパッチします。 BizTalk Server の受信場所が 1 つの TIBCO Rendezvous イベント キューとディスパッチャー スレッドのプールに関連付けられています。  
  
### <a name="memory-use-and-errors"></a>メモリの使用とエラー  
 イベントの処理中、アダプターは使用されるリソースを監視します。 メモリの使用量が上限 Watermark を超えると、アダプターはメモリ使用量が下限 Watermark に達するまでイベントのディスパッチを停止します。 これにより TIBCO Rendezvous メッセージが未証明メッセージとして失われる場合があることに注意してください (TIBCO RV コンシューマーは 60 秒経過したらメッセージをキューから削除します)。 このデータ損失はエラーとして報告されます。 アダプターが TIBCO Rendezvous のシステム通知 NO_MEMORY メッセージを受け取ったら、メッセージは既に失われています。  
  
 BizTalk Adapter for TIBCO Rendezvous は状態を保持しており、状態に応じて異なるタスクを実行します。 BizTalk メッセージ エンジンがエラーを報告し、アダプターが証明されたリスナーとして構成されている場合、アダプターは TIBCO Rendezvous にエラーを報告してメッセージを再送信できるようにします。  
  
## <a name="see-also"></a>参照  
 [TIBCO Rendezvous の概念](../core/tibco-rendezvous-concepts.md)   
 [データ型マッピングの TIBCO Rendezvous 受信ハンドラー](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)   
 [TIBCO Rendezvous 受信ハンドラーの作成](../core/creating-tibco-rendezvous-receive-handlers.md)