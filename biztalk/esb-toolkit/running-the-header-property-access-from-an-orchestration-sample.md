---
title: オーケストレーションのサンプルからのヘッダー プロパティへのアクセスを実行している |Microsoft ドキュメント
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
ms.openlocfilehash: d2ddbb2ea7ef978c0e5eae07835d5a9c1320bbc2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294778"
---
# <a name="running-the-header-property-access-from-an-orchestration-sample"></a>オーケストレーションのサンプルからヘッダー プロパティへのアクセスを実行します。
このサンプルの一部では、コードと Microsoft biztalk オーケストレーション内のコンポーネントにアクセスできるメッセージ コンテキストのプロパティに、ESB が JMS ヘッダーのメタデータを昇格する方法について説明します。 このサンプルには、JMS ヘッダーのメタデータをメッセージ コンテキスト プロパティに昇格する ESB JMS コンポーネントのインスタンスを含む受信パイプラインが含まれています。  
  
 受信ポートは、メッセージのコンテキスト プロパティから、キューの名前を取得する名前付き JMSRouter RfhUtil ユーティリティによって割り当てられている (およびヘッダーのメタデータで送信される)、オーケストレーションにメッセージを渡します。 オーケストレーションは、動的送信ポートをこのキュー名が割り当てられ、そのポートにメッセージを送信します。  
  
 ポートの送信パイプラインには、メッセージ コンテキスト プロパティは降格されますが、JMS ヘッダー メタデータに ESB JMS コンポーネントのインスタンスが含まれています。  
  
 **ヘッダー プロパティ アクセス サンプルを実行するには**  
  
1.  GlobalBank.ESB アプリケーションが既に実行されていない場合は、BizTalk 管理コンソールを使用して、開始します。  
  
2.  IBM RfhUtil ユーティリティ; を実行します。ESB という名前のキュー マネージャーを選択します。JMS です。このサンプルの第 1 部と同様に、このキュー マネージャーに接続する最初のドロップダウン リストで Sample.QueueManager です。  
  
3.  2 番目のドロップダウン リストで、ESB をという名前のターゲットの送信キューを選択します。JMS です。サンプルです。SENDTOBIZTALK です。  
  
4.  クリックして、 **ReadFile** RfhUtil ユーティリティ ボタンをクリックし、テスト 000128 をという名前のテスト メッセージ ファイルに移動します。JMS が \Source\Samples\JMS\Test\Data\Load をという名前のサブフォルダーにある\\です。 このファイルには、128 テスト メッセージのバッチが含まれていますが、ユーティリティは、最初の 1 つのみを読み込みます。  
  
5.  クリックして、 **RFH**  タブの し、確認だけ、 **JMS**  チェック ボックスをオンします。  
  
6.  クリックして、 **jms** ] タブの [していることを確認、選択した**返信先**キューが ESB です。JMS です。サンプルです。応答と、選択した**送信先キュー** ESB は、します。JMS です。サンプルです。DYNAMICQ2 です。  
  
7.  クリックして、 **Main**  タブをクリックして、**書き込み Q**ボタンをクリックして、キューにメッセージを書き込みます。  
  
8.  遅延後に、アプリケーションの実行中は、ESB に、ESB 出力メッセージが表示されます。JMS です。サンプルです。DYNAMICQ2 キューです。 WebSphere キュー エクスプ ローラーを開き、これを確認するキューを参照します。  
  
## <a name="how-the-sample-works"></a>このサンプルのしくみ  
 コード、オーケストレーション内に含まれていた JMS ヘッダーにメッセージを読み込むことにより、値がアクセスできる、 **XmlDocument**インスタンス、次のコードに示すようにします。  
  
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