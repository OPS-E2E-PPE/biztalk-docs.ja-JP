---
title: メッセージ ボックスの直接バインド ポートを使用する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 82fbe52d46847bdaa7caffbb4402ce8d380a73f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255914"
---
# <a name="how-to-use-messagebox-direct-bound-ports"></a>メッセージ ボックスの直接バインド ポートの使用方法
メッセージ ボックスの直接バインド ポートを使用すると、明示的な受信者がない状態でメッセージをメッセージ ボックス データベースに直接ドロップでき、特定の送信者からのメッセージではなく特定の条件を満たすメッセージをサブスクライブできます。  
  
 MessageBox でメッセージを送信の直接バインド ポートはメッセージ バスへのメッセージの公開に相当 — この場合、メッセージ ボックス データベースにします。 公開されたメッセージに対しては任意の数のサブスクライバーが存在することができ、メッセージを公開したときにメッセージに関連するサブスクライバーが存在しない場合は、"サブスクリプションが見つかりません。" 例外がスローされます。 特定の受信者を念頭にメッセージ ボックスの直接バインド ポートを通じてメッセージを送信する可能性がある場合に特定の値に設定されたプロパティ、**メッセージの割り当て**を探して、目的のサブスクライバーの形状。 BizTalk Server 定義済みプロパティ定義または独自のプロパティ定義に基づいてプロパティを設定できます。 例:  
  
```  
myMessage(PropertyNamespace.PropertyName) = "My Property")  
```  
  
 メッセージ ボックスの直接バインド ポートを使用したメッセージの受信は、フィルター条件を使用したメッセージ バスのサブスクライブに相当します。 メッセージの受信者は、オーケストレーションおよび送信ポートを含む、メッセージをサブスクライブできる任意の種類のサービスにすることができます。 アクティブ化**受信**図形、サブスクリプションがメッセージの種類とフィルター式と非アクティブの**受信**図形、サブスクリプションがメッセージの種類と、相関関係を設定します。 各**受信**図形は常に、そのサブスクリプションの一部としてメッセージの種類を含めます。  
  
> [!NOTE]
>  アクティブ化がある場合は、フィルター式を使用する必要があります**受信**型のメッセージを受信図形**System.Xml.XmlDocument**または**という**直接バインド ポートでのサブスクリプション定義ルーティングします。  
  
 アクティブでいずれかのフィルター条件を指定しなかった場合**受信**図形は、メッセージ ボックスの直接バインド ポートに接続し、サブスクリプションは、次のようになります。  
  
```  
http://schemas.microsoft.com/BizTalk/2003/system-properties.ReceivePortID == {2F6A80E1-2518-4A69-9C28-401C2DB1CBF6} And  
http://schemas.microsoft.com/BizTalk/2003/system-properties.MessageType == http://MyMessageType  
```  
  
 前の例では、メッセージ ボックスの直接バインド受信ポートは、ポートの操作の構成対象であるメッセージの種類と一致するすべてのメッセージを受信します。  
  
> [!NOTE]
>  メッセージ ボックスの直接バインド受信ポートを使用する場合は、フィルターをできるだけ具体的なものにする必要があります。 フィルターを十分に具体的なものにしなかった場合、オーケストレーションが不要なメッセージを受信する可能性があります。  
  
 メッセージ ボックスの直接バインド ポートを構成するには、選択**ポート間のルーティングが、メッセージ ボックス データベース内の着信メッセージのフィルター式によって定義される**ポート構成ウィザードでします。  
  
 メッセージ ボックスの直接バインド ポートを使用する方法の例を参照してください、SDK サンプル「直接バインドに、メッセージ ボックス データベースでオーケストレーション」 [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)です。  
  
## <a name="see-also"></a>参照  
 [自己関連付けを行う Direct を使用する方法のポートのバインド](../core/how-to-use-self-correlating-direct-bound-ports.md)   
 [パートナー オーケストレーション直接バインド ポートを使用する方法](../core/how-to-use-partner-orchestration-direct-bound-ports.md)