---
title: メッセージ ボックスの直接バインド ポートを使用する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1839184b-408e-4ac6-94a4-a0eb708183f6
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a37717639b12d3394ae3fc9e5de421c971fc2e73
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333426"
---
# <a name="how-to-use-messagebox-direct-bound-ports"></a>メッセージ ボックスの直接バインド ポートを使用する方法
メッセージ ボックスの直接バインド ポートを使用せず、明示的な受信者がメッセージ ボックス データベースに直接メッセージをドロップして、特定の送信者から送信されるメッセージではなく、特定の条件を満たすメッセージをサブスクライブすることができます。  
  
 メッセージ ボックスでメッセージを送信の直接バインド ポートはメッセージ バスへのメッセージの公開に相当: ここでは、メッセージ ボックス データベースにします。 任意の数、公開されたメッセージのサブスクライバーのでき、場合、サブスクライバーが存在しないメッセージで発行する時点で、「サブスクリプションが見つかりません」例外がスローされます。 特定の値にプロパティを設定するとする可能性がありますを考慮して特定の受信者にメッセージ ボックスの直接バインド ポートを通じてメッセージを送信する場合、**メッセージの割り当て**を探して、目的のサブスクライバーの形状。 BizTalk Server 定義済みプロパティの定義または独自のプロパティ定義に基づいてプロパティを設定することができます。 例 :  
  
```  
myMessage(PropertyNamespace.PropertyName) = "My Property")  
```  
  
 メッセージ ボックスの直接バインド ポートを通じてメッセージを受信することは、フィルター条件を持つメッセージ バスのサブスクライブと同じです。 メッセージの受信者をオーケストレーションを含む送信ポート、メッセージにサブスクライブできるサービスの任意の型を指定できます。 アクティブ化**受信**図形、サブスクリプションがメッセージの種類と、フィルター式と非アクティブの**受信**図形、サブスクリプションは、メッセージの種類と、相関関係を設定します。 すべて**受信**図形は、そのサブスクリプションの一部としてのメッセージの種類を常に含まれます。  
  
> [!NOTE]
>  アクティブ化がある場合は、フィルター式を使用する必要があります**受信**型のメッセージの受信図形**System.Xml.XmlDocument**または**という**直接バインド ポートでのサブスクリプション定義のルーティングします。  
  
 アクティブでいずれかのフィルター条件を指定しなかった場合**受信**図形が、メッセージ ボックスの直接バインド ポートに接続し、サブスクリプションは、次のようになります。  
  
```  
http://schemas.microsoft.com/BizTalk/2003/system-properties.ReceivePortID == {2F6A80E1-2518-4A69-9C28-401C2DB1CBF6} And  
http://schemas.microsoft.com/BizTalk/2003/system-properties.MessageType == http://MyMessageType  
```  
  
 前の例では、メッセージ ボックスの直接バインド受信ポート、ポートの操作が構成されているメッセージ型と一致するすべてのメッセージが表示されます。  
  
> [!NOTE]
>  ポートを受信するメッセージ ボックスの直接バインドを使用して、できるだけ具体的にフィルターが作成する必要があります。 行っていないフィルターだけの具体性、オーケストレーションから不要なメッセージが表示されます。  
  
 メッセージ ボックスの直接バインド ポートを構成するには、選択**ポート間のルーティングが、メッセージ ボックス データベースの着信メッセージのフィルター式によって定義される**ポート構成ウィザードでします。  
  
 メッセージ ボックスの直接バインド ポートを使用する方法の例を参照してください、SDK サンプル「直接バインドする、メッセージ ボックス データベースでオーケストレーション」 [ http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)します。  
  
## <a name="see-also"></a>参照  
 [自己関連付けを行う Direct を使用する方法のポートのバインド](../core/how-to-use-self-correlating-direct-bound-ports.md)   
 [パートナー オーケストレーション直接バインド ポートの使用方法](../core/how-to-use-partner-orchestration-direct-bound-ports.md)