---
title: BizTalk WCF サービス公開ウィザードで公開した WCF サービスをテストするための .NET アプリケーションを作成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF services, .NET applications
- WCF services, WCF Service Publishing Wizard
- creating, .NET applications [WCF services]
- WCF Service Publishing Wizard
ms.assetid: 17e39db2-8471-4f6f-a7f1-833023cdbc39
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb46847361127a915d06ee74eaed549caf40258a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287234"
---
# <a name="how-to-create-a-net-application-to-test-a-wcf-service-published-with-the-biztalk-wcf-service-publishing-wizard"></a>.NET アプリケーションを作成して、BizTalk WCF サービス公開ウィザードで公開した WCF サービスをテストする方法
公開済みの WCF サービスをテストするには、公開済みの WCF サービスを使用する .NET アプリケーションを作成します。 このトピックでは、.NET アプリケーションを作成して、公開済みの WCF サービスをテストする方法を説明します。  
  
> [!NOTE]
>  Visual Studio ヘルプ コレクションには、WCF サービスを使用する .NET アプリケーションを作成するための有用なチュートリアルが含まれています。 このチュートリアルを使用して、公開済みの WCF サービスをテストできます。 WCF クライアント プロジェクトの作成に関する情報および手順を参照してください「チュートリアル: へのアクセス、XML Web サービスを使用して Visual Basic または Visual c#」で、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ヘルプ コレクション[http://go.microsoft.com/fwlink/?LinkId=62263](http://go.microsoft.com/fwlink/?LinkId=62263)です。  
  
> [!NOTE]
>  このトピックでは、ServiceModel メタデータ ユーティリティ ツール (SvcUtil.exe) を使用して、WCF プロキシ クラスおよびアプリケーション構成ファイルを作成します。 SvcUtil.exe は、Windows Vista の Microsoft Windows ソフトウェア開発キット (SDK) および .NET Framework ランタイム コンポーネントに含まれています。  
  
### <a name="to-create-a-simple-wcf-proxy-class-and-application-configuration-file"></a>簡単な WCF プロキシ クラスおよびアプリケーション構成ファイルを作成するには  
  
1.  次のように CMD シェルを開きます: をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Windows SDK**、順にクリック**CMD Shell**です。  
  
2.  CMD シェルで、プロキシ クラスおよびアプリケーション構成ファイルを配置する先のディレクトリに移動します。  
  
3.  CMD シェルで、以下のように ServiceModel メタデータ ユーティリティ ツール (SvcUtil.exe) を実行して、公開済みの WCF サービスの WCF プロキシ クラスおよびアプリケーション構成ファイルを作成します。  
  
    ```  
    svcutil <http://servername/apppath/wcfservicename.svc> /config:App.config  
    ```  
  
    > [!NOTE]
    >  このコマンド ラインにより、プロキシ クラスである BizTalkServiceInstance.cs とアプリケーション構成ファイルである App.config が生成されます。 Svcutil.exe の詳細についてを参照してください「サービス モデル メタデータ ユーティリティ ツール (Svcutil.exe)」 [http://go.microsoft.com/fwlink/?LinkId=74696](http://go.microsoft.com/fwlink/?LinkId=74696)です。  
  
### <a name="to-compile-your-net-application-that-consumes-the-published-wcf-service"></a>公開済みの WCF サービスを使用する .NET アプリケーションをコンパイルするには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ソリューション エクスプローラーで、SvcUtil.exe が作成した BizTalkServiceInstance および App.config の 2 つのファイルをプロジェクトに追加します。  
  
2.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ソリューション エクスプローラーで、プロキシ コードをコンパイルするために System.ServiceModel.dll への参照を追加します。  
  
3.  生成されたプロキシ コードを使用するコードを作成します。 次のコードは、生成されたプロキシの使用方法を示しています。  
  
    ```  
    DeliveryNotification deliveryNotification= new DeliveryNotification();  
    deliveryNotification.TrackingNumber = "001";  
                Microsoft_Samples_BizTalk_WCFBasicHttp_BizTalkApp_DliveryRequestProcess_DeliveryNotificatonReceivePortClient service = new Microsoft_Samples_BizTalk_WCFBasicHttp_BizTalkApp_DliveryRequestProcess_DeliveryNotificatonReceivePortClient("BasicHttpBinding_ITwoWayAsyncVoid");  
    service.Submit(deliveryNotification);  
    ```  
  
4.  .NET アプリケーションを実行して、公開済みの WCF サービスにメッセージを送信します。  
  
## <a name="see-also"></a>参照  
 [受信アダプターの WCF での WCF サービスを発行するときの考慮事項](../core/considerations-when-publishing-wcf-services-with-the-wcf-receive-adapters.md)