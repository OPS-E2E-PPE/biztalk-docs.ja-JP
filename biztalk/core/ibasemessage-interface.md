---
title: "IBaseMessage インターフェイス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 10bfb95c-aef5-46ba-ba0e-9961833f27a3
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7de478b27105ee6c01d582aa9b728bd0496d0487
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="ibasemessage-interface"></a>IBaseMessage インターフェイス
使用して、受信アダプターがそのプロトコルを介して受信データ パケットを受け入れるときに、 **IBaseMessage**メッセージング エンジンに渡すメッセージを作成するインターフェイスです。 すべてのメッセージは、このインターフェイスで表現されます。  
  
 メッセージが 1 つまたは複数のメッセージ部分がによって表される、 **IBaseMessagePart**インターフェイスです。 各メッセージ部分はを通じてデータへの参照、 **IStream**インターフェイス ポインター。 メッセージのコンテキストとして表されますその**IBaseMessageContext**インターフェイスです。 次の図は、BizTalk メッセージ オブジェクト モデルを示しています。  
  
 ![](../core/media/ibasemessagestructure.gif "IBaseMessageStructure")  
  
 メッセージ コンテキストは、プロパティ名とプロパティの名前空間の組み合わせをキーとするディクショナリです。 これにより、ソースの異なる類似した名前のプロパティ ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のシステム プロパティとカスタム アダプター プロパティなど) の間の競合を回避することができます。 これらのプロパティの値は、.NET 型**オブジェクト**、実際のバリアントは、これらのプロパティが、します。  
  
 各部分には部分コンテキストがあり、同じくディクショナリとして機能しますが、名前空間の概念はありません。 部分コンテキストの値は、その部分に対応するデータを参照するメタデータです。 この例は、 **Charset**メッセージのエンコードを使用した文字セットを指定するプロパティです。  
  
 プロパティは、メッセージ コンテキストに書き込むことも、メッセージ コンテキストから読み取ることもできます。 また、昇格させてメッセージのルーティングに使用することもできます。 昇格させたプロパティは、メッセージと共に渡されるメタデータの一部として書き込まれます。 昇格させたプロパティの値は、送信ポートやオーケストレーションのフィルター式の作成に使用できます。 下流コンポーネントやオーケストレーション内のユーザー コードで、昇格させたプロパティを読み取ったり新しい値を書き込んだりできます。  
  
 昇格させたプロパティが既存のサブスクリプションと照合されてメッセージのルーティングに使用されると、サブスクリプションの照合が繰り返されないように、そのプロパティは降格されます。 降格されたプロパティはメタデータとしてメッセージ コンテキストに残りますが、昇格状態は失われます。  
  
 **実装のヒン ト:**メッセージ コンテキスト プロパティは、実行時にメモリに読み込まれます。 膨大なデータをメッセージ コンテキストに書き込むことは、サイズの大きいメッセージをサポートする [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の機能を損なう可能性があるのでお勧めできません。 実装すればメッセージ コンテキストにオブジェクトをシリアル化することがあります、 **IPersistStream**インターフェイスです。 なお、昇格させたプロパティは 255 文字までに制限されます。  
  
 新しいメッセージの作成には、必ずメッセージ ファクトリを使用します。  次のコードは、アダプターで受信したデータ ストリームから新しい BizTalk メッセージを作成する方法を示しています。  
  
```  
using Microsoft.BizTalk.Message.Interop;  
  
IBaseMessage CreateMessage( Stream s, IBaseMessageFactory msgFactory )  
{  
IBaseMessage msg = null;  
IBaseMessagePart part = msgFactory.CreateMessagePart();  
part.Data = s;  
msg = msgFactory.CreateMessage();  
msg.AddPart("body", part, true);  
return msg;  
}  
```