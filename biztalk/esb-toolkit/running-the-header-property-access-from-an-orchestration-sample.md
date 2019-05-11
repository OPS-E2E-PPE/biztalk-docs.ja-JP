---
title: オーケストレーション サンプルからヘッダー プロパティ アクセスを実行している |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2059eb2c-50a3-4618-a6ec-faa1a9e5d368
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b785157d4d3a03e25bc80b1a370f419de72822f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242772"
---
# <a name="running-the-header-property-access-from-an-orchestration-sample"></a>オーケストレーション サンプルからヘッダー プロパティ アクセスを実行しています。
サンプルのこの部分では、コードと Microsoft biztalk オーケストレーション内のコンポーネントにアクセスできるメッセージ コンテキストのプロパティに、ESB が JMS ヘッダー メタデータを昇格する方法を示します。 このサンプルには、JMS ヘッダー メタデータをメッセージ コンテキスト プロパティに昇格する ESB JMS コンポーネントのインスタンスを含む受信パイプラインが含まれています。  
  
 受信ポートは、メッセージのコンテキスト プロパティから、キュー名を取得する名前付きの JMSRouter RfhUtil ユーティリティによって割り当てられている (およびヘッダーのメタデータで送信される)、オーケストレーションにメッセージを渡します。 オーケストレーションでは、動的送信ポートをこのキュー名が割り当てられ、そのポートにメッセージを送信します。  
  
 ポートの送信パイプラインには、JMS ヘッダーのメタデータに、メッセージ コンテキスト プロパティを降格する ESB JMS コンポーネントのインスタンスが含まれています。  
  
 **ヘッダー プロパティ アクセス サンプルを実行するには**  
  
1.  GlobalBank.ESB アプリケーションが実行されていない場合は、BizTalk 管理コンソールを使用して開始します。  
  
2.  IBM RfhUtil ユーティリティを実行します。ESB をという名前のキュー マネージャーを選択します。JMS します。このサンプルの第 1 部のように、このキュー マネージャーに接続する最初のドロップダウン リストで Sample.QueueManager します。  
  
3.  2 番目のドロップダウン リストでは、ESB をという名前のターゲットの送信キューを選択します。JMS します。サンプルです。SENDTOBIZTALK します。  
  
4.  をクリックして、 **ReadFile** RfhUtil ユーティリティでボタンをクリックし、テスト 000128 をという名前のテスト メッセージ ファイルに移動します。JMS \Source\Samples\JMS\Test\Data\Load をという名前のサブフォルダーにある\\します。 このファイルには、128 のテスト メッセージのバッチが含まれていますが、ユーティリティは、最初の 1 つのみを読み込みます。  
  
5.  をクリックして、 **RFH**  タブの し、確認しか、 **JMS**  チェック ボックスをオンします。  
  
6.  をクリックして、 **jms** ] タブの [、いることを確認し、選択した**返信先**キューが ESB。JMS します。サンプルです。応答と、選択した**送信先キュー** ESB は、します。JMS します。サンプルです。DYNAMICQ2 します。  
  
7.  をクリックして、 **Main**タブをクリックし、をクリックし、**書き込み Q**ボタンをクリックして、キューにメッセージを書き込みます。  
  
8.  遅延後に、アプリケーションの実行中に、ESB で、ESB の出力メッセージが表示されます。JMS します。サンプルです。DYNAMICQ2 キューです。 WebSphere キュー エクスプ ローラーを開き、これを確認するキューを参照します。  
  
## <a name="how-the-sample-works"></a>サンプルのしくみ  
 コード、オーケストレーション内にメッセージを読み込むことによって、JMS ヘッダーに含まれていた値にアクセスできる、 **XmlDocument**インスタンス、次のコードに示すようにします。  
  
```csharp  
if (null != InboundMsg(  
    Microsoft.Practices.ESB.JMS.Schemas.Property.MQRFH2_NameValueData))  
{     
  jmsInfo.LoadXml(InboundMsg(  
     Microsoft.Practices.ESB.JMS.Schemas.Property.MQRFH2_NameValueData));  
  if (null != jmsInfo)  
  {  
    if (null != jmsInfo.SelectSingleNode("//Dst"))  
    {  
      xElement = jmsInfo.SelectSingleNode("//Dst");  
      destinationQueue = xElement.InnerText.ToUpper(  
                         System.Globalization.CultureInfo.CurrentCulture);  
    }  
    if (null != jmsInfo.SelectSingleNode("//Rto"))  
    {  
      xElement = jmsInfo.SelectSingleNode("//Rto");  
      replyToQueue = xElement.InnerText.ToUpper(  
                     System.Globalization.CultureInfo.CurrentCulture);  
    }  
  }  
}  
```  
  
 さらに、コードは、すべてのメッセージの MQMD コンテキスト プロパティにアクセスできます。