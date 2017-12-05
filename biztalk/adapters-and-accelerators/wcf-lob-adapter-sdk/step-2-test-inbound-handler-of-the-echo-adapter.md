---
title: "手順 2: エコー アダプターの受信ハンドラーのテスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 86dede9b-6b7e-4901-9c79-b75bfee9155f
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94e17bcc987949b9ca25ac25db9a1789ebe980eb
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-2-test-inbound-handler-of-the-echo-adapter"></a>手順 2: エコー アダプターの受信ハンドラーをテストします。
![手順 2 の 2](../../adapters-and-accelerators/adapter-sql/media/step-2of2.gif "Step_2of2")  
  
 **所要時間:** 10 分  
  
 この手順では、エコー アダプターによって提供される受信サービスをテストします。 これを行う Visual Studio では、アダプター サービス参照を Visual Studio プラグインの追加とカスタム コードを使用します。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を完了する必要がありますを行った[チュートリアル 1: エコー アダプターを開発](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)です。 この手順は、独立して完了できる[手順 1: エコー アダプターの送信ハンドラーのテスト](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-test-outbound-handler-of-the-echo-adapter.md)です。  
  
## <a name="create-a-visual-studio-project"></a>Visual Studio プロジェクトを作成します。  
  
1.  Visual Studio を起動します。  
  
2.  Visual Studio での**ファイル** メニューのをポイント**新規**、順にクリック**プロジェクト**です。  
  
3.  **新しいプロジェクト** ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロジェクトの種類**|をクリックして**Visual c#**です。|  
    |**[テンプレート]**|をクリックして**コンソール アプリケーション**です。|  
    |**名前**|型**ConsumeEchoAdapter_Inbound**です。|  
    |**場所**|型**C:\Tutorials**です。|  
    |**[ソリューション名]**|型**ConsumeEchoAdapter_Inbound**です。|  
  
4.  **[OK]**をクリックします。  
  
5.  Visual Studio での**ファイル** メニューのをクリックして**すべて保存**です。  
  
## <a name="browse-search-and-generate-the-wcf-service"></a>参照、検索、および WCF サービスを生成  
  
1.  ウィンドウで、Visual Studio のソリューションを右クリックして**ConsumeEchoAdapter_Inbound**プロジェクトを選択し、**アダプター サービス参照の追加**アダプター サービス参照の追加プラグインを起動します。  
  
2.  **アダプター サービス参照の追加**画面で、バインディングを選択します。 これは、選択で**echoAdapterBindingV2**です。  
  
3.  次に、アダプターとの接続のプロパティを構成する をクリックして**構成**です。  開き、**アダプターの構成**画面。  
  
4.  **アダプターの構成**画面で、、**バインド プロパティ**タブでアダプターのプロパティを構成します。 注意してカスタムのカテゴリのエコー アダプター**受信**と**その他**が表示されます。 下にある、**その他**カテゴリで、をクリックして**InboundFileSystemWatcherFolder**し監視するディレクトリを入力します。  
  
5.  をクリックして**[ok]**を閉じる、**アダプターの構成**画面およびに戻り、**アダプター サービス参照の追加**画面。  
  
6.  次に、をクリックして**接続**エコー アダプタ (およびの仮定の基幹業務システムをサポートしています) に接続します。 しばらくすると、接続の状態を変更する必要があります**接続**とカテゴリ ツリー (**カテゴリを選択**) 設定する必要があります。  
  
7.  使用可能な受信操作を表示するには、変更、**サービス コントラクト型**に**サービス (入力方向の操作)**です。  
  
8.  分類ツリーで、をクリックして**メイン カテゴリ**です。 これには、利用可能なカテゴリと操作を 1 つの受信操作の一覧が表示されます。 カテゴリはありません。  
  
9. **利用可能なカテゴリと操作**、select、 **OnReceiveEcho**操作します。 をクリックして**追加**生成した WCF インターフェイスの選択した操作の一部に取り入れるためです。  
  
10. をクリックして**OK** WCF インターフェイスを生成します。 これにより、アプリケーション構成ファイル (app.config)、WCF インターフェイス (EchoAdapterBindingInterface.cs) および WCF サービス (EchoAdapterBindingService.cs) がプロジェクトに追加します。  
  
11. をクリックして**ファイル**上、 **Visual Studio**メニューを選択し、**すべてを保存**です。  
  
## <a name="test-the-echo-adapter"></a>エコー アダプターをテストします。  
  
1.  ソリューション エクスプ ローラーで、 **EchoAdapterBindingService.cs**ファイル。  
  
2.  Visual Studio エディターで、内部、 **OnReceiveEcho**メソッド、既存の実装を次に置き換えます。  
  
    ```csharp  
    System.Console.WriteLine("path = " + path + ", len = " + length);  
    ```  
  
3.  ソリューション エクスプ ローラーで、 **Program.cs**ファイル。  
  
4.  Main メソッド内の Visual Studio エディターでは、次のコードを WCF サービスのホストを追加します。  
  
    ```csharp  
    try  
    {  
        // Create a ServiceHost for the EchoServiceImpl type  
        // and use the base address from app.config  
        System.ServiceModel.ServiceHost host = new System.ServiceModel.ServiceHost(typeof(EchoAdapterBindingNamespace.EchoAdapterBindingService));  
  
        // Open the ServiceHost to start listening for messages  
        host.Open();  
  
        Console.WriteLine("The service is ready.");  
        Console.WriteLine("Press <ENTER> to terminate service.");  
        Console.ReadLine();  
  
        // Close the ServiceHost  
        host.Close();  
    }  
    catch (TimeoutException ex)  
    {  
        Console.WriteLine(ex.Message);  
        Console.WriteLine();  
    }  
    catch (System.ServiceModel.CommunicationException ex)  
    {  
        Console.WriteLine(ex.Message);  
        Console.WriteLine();  
    }  
    ```  
  
5.  Visual Studio での**ファイル** メニューのをクリックして**すべて保存**です。  
  
6.  F5 キーを押してサンプルを開始します。  
  
7.  このチュートリアルで以前に指定されたディレクトリを"txt"の拡張子を持つファイルをドロップします。 プログラムは、出力ウィンドウでは、次のような情報が表示されます。  
  
     **サービス準備ができました。**  
  
     **キーを押して\<ENTER\>サービスを終了します。**  
  
     **パス = file:///C:/Tutorial/InboundTest/InboundTest.txt、len 229179 を =**  
  
8.  サービスを停止して、Enter キーを押します。  
  
## <a name="what-did-i-just-do"></a>でしただけは何ですか。  
 この手順で作成したテスト アプリケーションで開発されたエコー アダプターによって公開されている受信操作の[チュートリアル 1: エコー アダプターを開発](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)です。 これを行うには、WCF サービスを生成、および WCF サービスをホストするためのコードを提供する、Visual Studio プロジェクトを作成します。 最後に、テスト アプリケーションを実行しました。  
  
## <a name="next-steps"></a>次の手順  
 これは、このチュートリアルの最後の手順です。 受信操作の詳細については、次を参照してください。`Microsoft.ServiceModel.Channels.Common.IInboundHandler`です。 エコー アダプターおよびテストのコードでのダウンロードを表示して、SDK には認証を必要とする WCF サービスをホストする方法を示しますが、 [http://go.microsoft.com/fwlink/?LinkID=96184](http://go.microsoft.com/fwlink/?LinkID=96184)です。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 2: .NET からエコー アダプターを使用します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md)   
 [チュートリアル 1: エコー アダプターを開発する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)