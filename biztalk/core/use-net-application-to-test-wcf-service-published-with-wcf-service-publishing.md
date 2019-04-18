---
title: BizTalk WCF サービス公開ウィザードで公開した WCF サービスをテストするための .NET アプリケーションを作成する方法 |Microsoft Docs
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
ms.openlocfilehash: 2d390b54a79ca883b53ff5088638ba2804fa2640
ms.sourcegitcommit: 85e827c42f193e44ca8b5b8d78d6f8b8ac686f1e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58867556"
---
# <a name="how-to-create-a-net-application-to-test-a-wcf-service-published-with-the-biztalk-wcf-service-publishing-wizard"></a>BizTalk WCF サービス公開ウィザードで公開した WCF サービスをテストするための .NET アプリケーションを作成する方法
を、公開済み WCF サービスをテストするには、公開済み WCF サービスを使用する .NET アプリケーションを作成できます。 このトピックでは、公開した WCF サービスをテストするための .NET アプリケーションを作成する方法について説明します。  
  
> [!NOTE]
>  Visual Studio ヘルプ コレクションには、WCF サービスを使用する .NET アプリケーションを作成するため貴重なチュートリアルが含まれています。 このチュートリアルを使用して、公開済み WCF サービスをテストすることができます。 情報と WCF クライアント プロジェクトの作成方法の手順では、次を参照してください。"チュートリアル。Visual Basic または Visual を使用して XML Web サービスへのアクセスC#"で、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ヘルプ コレクション[ http://go.microsoft.com/fwlink/?LinkId=62263](http://go.microsoft.com/fwlink/?LinkId=62263)します。  
> 
> [!NOTE]
>  このトピックでは、Service Model メタデータ ユーティリティ ツール (SvcUtil.exe)、WCF プロキシ クラスを作成してアプリケーション構成ファイルを使用します。 SvcUtil.exe で、Microsoft Windows ソフトウェア開発キット (SDK) の Windows Vista と .NET Framework のランタイム コンポーネントが含まれています。  
  
### <a name="to-create-a-simple-wcf-proxy-class-and-application-configuration-file"></a>単純な WCF プロキシ クラスおよびアプリケーション構成ファイルを作成するには  
  
1.  次のように CMD シェルを開きます: をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Windows SDK**、順にクリックします**CMD シェル**します。  
  
2.  CMD シェルで、プロキシ クラスおよびアプリケーション構成ファイルを配置するディレクトリに移動します。  
  
3.  CMD シェルで次のように、ServiceModel メタデータ ユーティリティ ツール (SvcUtil.exe) WCF プロキシ クラスを作成して、公開済み WCF サービスのアプリケーション構成ファイルを実行します。  
  
    ```  
    svcutil <http://servername/apppath/wcfservicename.svc> /config:App.config  
    ```  
  
    > [!NOTE]
    >  このコマンドラインは、アプリケーションの構成のプロキシ クラスと App.config の BizTalkServiceInstance.cs を生成します。 Svcutil.exe の詳細についてを参照してください「サービス モデル メタデータ ユーティリティ ツール (Svcutil.exe)」 [ http://go.microsoft.com/fwlink/?LinkId=74696](http://go.microsoft.com/fwlink/?LinkId=74696)します。  
  
### <a name="to-compile-your-net-application-that-consumes-the-published-wcf-service"></a>.NET アプリケーションをコンパイルするには、公開した WCF サービスを使用します。  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーで、SvcUtil.exe が作成した BizTalkServiceInstance および App.config ファイルをプロジェクトに追加します。  
  
2. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロキシ コードをコンパイルするには、ソリューション エクスプ ローラー、System.ServiceModel.dll への参照を追加することを確認してください。  
  
3. 生成されたプロキシ コードを使用するコードを作成します。 次のコードでは、生成されたプロキシを使用する方法を示します。  
  
   ```  
   DeliveryNotification deliveryNotification= new DeliveryNotification();  
   deliveryNotification.TrackingNumber = "001";  
               Microsoft_Samples_BizTalk_WCFBasicHttp_BizTalkApp_DeliveryRequestProcess_DeliveryNotificationReceivePortClient service = new Microsoft_Samples_BizTalk_WCFBasicHttp_BizTalkApp_DeliveryRequestProcess_DeliveryNotificationReceivePortClient("BasicHttpBinding_ITwoWayAsyncVoid");  
   service.Submit(deliveryNotification);  
   ```  
  
4. 公開した WCF サービスにメッセージを送信する .NET アプリケーションを実行します。  
  
## <a name="see-also"></a>参照  
 [WCF 受信アダプターで WCF サービスを公開する場合の考慮事項](../core/considerations-when-publishing-wcf-services-with-the-wcf-receive-adapters.md)