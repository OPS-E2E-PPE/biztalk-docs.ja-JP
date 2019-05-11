---
title: 手順 2:エコー アダプターの受信ハンドラーをテストする |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 86dede9b-6b7e-4901-9c79-b75bfee9155f
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f238a6ddafb70aa30d8b736042e48b0466b77a42
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363260"
---
# <a name="step-2-test-inbound-handler-of-the-echo-adapter"></a>手順 2:エコー アダプターの受信ハンドラーをテストします。
![手順 2 の 2](../../adapters-and-accelerators/adapter-sql/media/step-2of2.gif "Step_2of2")  
  
 **所要時間:** 10 分  
  
 この手順では、エコー アダプターによって提供される受信サービスをテストします。 これを行う Visual Studio では、アダプター サービス参照を Visual Studio プラグインの追加およびカスタム コードを使用します。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を完了する必要がありますを行った[チュートリアル 1。エコー アダプターを開発](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)します。 この手順は、独立して完了できます[手順 1。エコー アダプターの送信ハンドラーをテストする](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-test-outbound-handler-of-the-echo-adapter.md)します。  
  
## <a name="create-a-visual-studio-project"></a>Visual Studio プロジェクトを作成します。  
  
1.  Visual Studio を起動します。  
  
2.  Visual Studio での**ファイル**メニューで、**新規**、順にクリックします**プロジェクト**します。  
  
3.  **新しいプロジェクト** ダイアログ ボックスで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロジェクトの種類**|クリックして**Visual c#** します。|  
    |**[テンプレート]**|クリックして**コンソール アプリケーション**します。|  
    |**名前**|型**ConsumeEchoAdapter_Inbound**します。|  
    |**場所**|型**C:\Tutorials**します。|  
    |**[ソリューション名]**|型**ConsumeEchoAdapter_Inbound**します。|  
  
4.  **[OK]** をクリックします。  
  
5.  Visual Studio での**ファイル** メニューのをクリックして**すべて保存**します。  
  
## <a name="browse-search-and-generate-the-wcf-service"></a>参照、検索、および WCF サービスを生成します。  
  
1.  Visual Studio ソリューション ウィンドウで右クリック**ConsumeEchoAdapter_Inbound**プロジェクト選び**アダプター サービス参照の追加**アダプター サービス参照の追加プラグインを起動します。  
  
2.  **アダプター サービス参照の追加**画面で、バインドを選択します。 これは、選択で**echoAdapterBindingV2**します。  
  
3.  次に、アダプターと接続のプロパティをクリックして構成**構成**します。  開き、**アダプターの構成**画面。  
  
4.  **アダプターの構成**画面で、、**バインドのプロパティ**タブをアダプターのプロパティを構成します。 注意してエコー アダプターのカスタム カテゴリ**受信**と**Misc**が表示されます。 下、**その他**カテゴリで、をクリックして**InboundFileSystemWatcherFolder**し監視するディレクトリを入力します。  
  
5.  をクリックして**OK**を閉じる、**アダプターの構成**画面に戻って、**アダプター サービス参照の追加**画面。  
  
6.  次に、クリックして**Connect**エコー アダプター (および仮定の基幹業務システムをサポートしています) に接続します。 しばらくすると、接続の状態を変更する必要があります**接続**とカテゴリ ツリー (**カテゴリを選択**) 設定する必要があります。  
  
7.  使用可能な受信操作を表示するには、変更、**サービス コントラクト型**に**サービス (受信操作)** します。  
  
8.  カテゴリのツリーで、クリックして**メイン カテゴリ**します。 これには、利用可能なカテゴリと 1 つの受信操作での操作の一覧が表示されます。 カテゴリはありません。  
  
9. **利用可能なカテゴリと操作**を選択、 **OnReceiveEcho**操作。 クリックして**追加**選択した操作を生成した WCF インターフェイスの一部にします。  
  
10. クリックして**OK** WCF インターフェイスを生成します。 これにより、アプリケーション構成ファイル (app.config)、WCF インターフェイス (EchoAdapterBindingInterface.cs) および WCF サービス (EchoAdapterBindingService.cs) がプロジェクトに追加します。  
  
11. をクリックして**ファイル**上、 **Visual Studio**メニュー選択**すべてを保存**。  
  
## <a name="test-the-echo-adapter"></a>エコー アダプターをテストします。  
  
1.  ソリューション エクスプ ローラーで、 **EchoAdapterBindingService.cs**ファイル。  
  
2.  Visual Studio エディターでの内部、 **OnReceiveEcho**メソッドを次の既存の実装に置き換えます。  
  
    ```csharp  
    System.Console.WriteLine("path = " + path + ", len = " + length);  
    ```  
  
3.  ソリューション エクスプ ローラーで、 **Program.cs**ファイル。  
  
4.  Main メソッド内で、Visual Studio エディターでは、次のコードを WCF サービスのホストを追加します。  
  
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
  
5.  Visual Studio での**ファイル** メニューのをクリックして**すべて保存**します。  
  
6.  F5 キーを押して、サンプルを開始します。  
  
7.  このチュートリアルで前に指定されたディレクトリに"txt"拡張子を持つファイルを削除します。 プログラムの出力ウィンドウに次のような情報が表示されます。  
  
     **サービスの準備ができました。**  
  
     **キーを押して\<ENTER\>サービスを終了します。**  
  
     **パス = file:///C:/Tutorial/InboundTest/InboundTest.txt、len 229179 を =**  
  
8.  サービスを停止して、Enter キーを押します。  
  
## <a name="what-did-i-just-do"></a>でしただけ何か。  
 この手順でアプリケーションを作成したテストで開発されたエコー アダプターによって公開されている受信操作の[チュートリアル 1。エコー アダプターを開発](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)します。 これを行うには、WCF サービスでは、生成された、および WCF サービスをホストするためのコードを提供する Visual Studio プロジェクトを作成します。 最後に、テスト アプリケーションを実行します。  
  
## <a name="next-steps"></a>次の手順  
 これは、このチュートリアルの最後の手順です。 受信操作の詳細については、次を参照してください。`Microsoft.ServiceModel.Channels.Common.IInboundHandler`します。 SDK 認証が必要な WCF サービスをホストする方法を示す例を確認するには、ダウンロードでエコー アダプターとテスト コード[ http://go.microsoft.com/fwlink/?LinkID=96184](http://go.microsoft.com/fwlink/?LinkID=96184)します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 2: .NET からエコー アダプターを使用します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md)   
 [チュートリアル 1:エコー アダプターを開発する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)