---
title: IBaseMessage インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10bfb95c-aef5-46ba-ba0e-9961833f27a3
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 009c9df42e8dbce58f3b731932ef4077693f0f63
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382808"
---
# <a name="ibasemessage-interface"></a>IBaseMessage インターフェイス
使用して、受信アダプターが自身のプロトコルを介して受信データ パケットを受け入れる場合、 **IBaseMessage**メッセージング エンジンに渡すメッセージを作成するインターフェイス。 すべてのメッセージは、このインターフェイスを使用して表されます。  
  
 メッセージで 1 つまたは複数のメッセージ部分として表さ、 **IBaseMessagePart**インターフェイス。 各メッセージ部分はそのデータ全体への参照、 **IStream**インターフェイス ポインター。 メッセージのコンテキストがによって表される、 **IBaseMessageContext**インターフェイス。 次の図は、BizTalk メッセージ オブジェクト モデルを示しています。  
  
 ![](../core/media/ibasemessagestructure.gif "IBaseMessageStructure")  
  
 メッセージ コンテキストは、プロパティ名とプロパティの名前空間の組み合わせで識別されるディクショナリ。 これにより、たとえば、さまざまなソースから同様に名前付きプロパティの間に競合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システム プロパティとカスタム アダプターのプロパティ。 これらのプロパティの値は、.NET 型の**オブジェクト**が、実際には、これらのプロパティは variant 型です。  
  
 各部分がディクショナリになっている部分コンテキストが、名前空間の概念です。 一部のコンテキストの値は、その部分のデータを参照するメタデータです。 この例は、 **Charset**メッセージのエンコードに使用する文字セットを指定するプロパティ。  
  
 プロパティに書き込まれ、メッセージ コンテキストから読み取ることがあります。 また、メッセージのルーティングに使用することも昇格可能性があります。 昇格メッセージと共に渡されるメタデータの一部として書き込まれたことを意味します。 昇格させたプロパティは、送信ポートやオーケストレーションのフィルター式の作成に使用するには、その値を許可します。 下流コンポーネントやオーケストレーション内のユーザー コードが昇格させたプロパティの読み取りし、も新しい値を書き込みを行うことがあります。  
  
 昇格させたプロパティは、既存のサブスクリプションに一致し、メッセージをルーティングするために使用されていますが、後に、プロパティは降格されます循環サブスクリプションと一致するようにします。 降格されたプロパティは、メタデータが、昇格状態を失うと、メッセージ コンテキストに残ります。  
  
 **実装のヒン ト:** メッセージ コンテキスト プロパティは、実行時にメモリに読み込まれます。 この使用できなくなる可能性があるために、膨大なデータをメッセージ コンテキストに書き込まれませんする必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]大きいメッセージをサポートします。 実装すればメッセージ コンテキストにオブジェクトをシリアル化することがあります、 **IPersistStream**インターフェイス。 また、昇格させたプロパティは、255 文字に制限されます。  
  
 メッセージ ファクトリは、新しいメッセージを作成する常に使用する必要があります。  次のコード フラグメントは、アダプターで受信したデータ ストリームから新しい BizTalk メッセージを作成する方法を示しています。  
  
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