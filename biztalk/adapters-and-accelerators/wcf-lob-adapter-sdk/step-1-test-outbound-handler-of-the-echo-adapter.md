---
title: '手順 1: エコー アダプターの送信ハンドラーのテスト |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad4a8164-a584-436f-b20b-4c884f6e2b37
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba2b1d6586588d17c58c0ca9a74cb11a7a9bd9f2
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
---
# <a name="step-1-test-outbound-handler-of-the-echo-adapter"></a>手順 1: エコー アダプターの送信ハンドラーをテストします。
![2 の手順 1.](../../adapters-and-accelerators/adapter-sql/media/step-1of2.gif "Step_1of2")  
  
 **完了時間:** 15 分  
  
 この手順では、エコー アダプターによって提供される 3 つの送信操作をテストします。 これを行う Visual Studio では、アダプター サービス参照を Visual Studio プラグインの追加とカスタム コードを使用します。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を完了する必要がありますを行った[チュートリアル 1: エコー アダプターを開発](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)です。  
  
## <a name="create-a-visual-studio-project"></a>Visual Studio プロジェクトを作成します。  
  
1.  Visual Studio を起動します。  
  
2.  Visual Studio での**ファイル** メニューのをポイント**新規**、順にクリック**プロジェクト**です。  
  
3.  **新しいプロジェクト**  ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロジェクトの種類**|クリックして **Visual c#**します。|  
    |**テンプレート**|クリックして **コンソール アプリケーション**します。|  
    |**名前**|型**ConsumeEchoAdapter_Outbound**です。|  
    |**場所**|型**C:\Tutorials**です。|  
    |**[ソリューション名]**|型**ConsumeEchoAdapter_Outbound**です。|  
  
4.  **[OK]**をクリックします。  
  
5.  Visual Studio での**ファイル** メニューのをクリックして**すべて保存**です。  
  
## <a name="browse-search-and-generate-the-wcf-client"></a>参照、検索、および WCF クライアントの生成  
  
1.  ウィンドウで、Visual Studio のソリューションを右クリックして**ConsumeEchoAdapter_Outbound**を選択し、[プロジェクト]**アダプター サービス参照の追加**アダプター サービス参照の追加プラグインを起動します。  
  
2.  **アダプター サービス参照の追加**画面で、バインディングを選択します。 これは、選択で**echoAdapterBindingV2**です。  
  
3.  次に、アダプターとの接続のプロパティを構成する をクリックして**構成しています**.  これが表示されます、**アダプターの構成**画面。  
  
4.  **アダプターの構成**画面で、、 **URI プロパティ**タブで接続のプロパティを構成します。 カスタムのカテゴリのエコー アダプターが示されている通知:**接続**と**形式**です。 下にある、**形式**カテゴリで、変更**EchoInUpperCase**に**True**です。  
  
5.  **アダプターの構成**画面で、、**バインド プロパティ**タブでアダプターのプロパティを構成します。 注意してカスタムのカテゴリのエコー アダプター**受信**と**その他**が表示されます。 下にある、**その他**カテゴリで、変更**カウント**に**3**です。  
  
6.  をクリックして**[ok]**を閉じる、**アダプターの構成**画面およびに戻り、**アダプター サービス参照の追加**画面。  
  
7.  次に、をクリックして**接続**エコー アダプタ (およびの仮定の基幹業務システムをサポートしています) に接続します。 しばらくすると、接続の状態を変更する必要があります**接続**とカテゴリ ツリー (**カテゴリを選択**) 設定する必要があります。  
  
8.  分類ツリーで、をクリックして**メイン カテゴリ**です。 これにより、利用可能なカテゴリと操作と、次の 3 つの送信操作の一覧が表示されます。 カテゴリされません。  
  
    > [!NOTE]
    >  既定のコントラクトの種類は、送信です。 カテゴリの結果には、このコントラクトの型は一致します。  
  
9. **利用可能なカテゴリと操作**、3 つすべての操作を選択します。 多数の操作が存在する場合、選択範囲を絞り込む検索を使用する可能性があります。この場合はのみ 3 つあります。 をクリックして**追加**生成した WCF インターフェイスの選択した操作の一部に取り入れるためです。  
  
10. をクリックして**OK** WCF インターフェイスを生成します。 アプリケーション構成ファイル (app.config) と WCF クライアント プロキシ (EchoAdapterBindingClient.cs) は、プロジェクトにこの追加されます。  
  
11. をクリックして**ファイル**Visual Studio のメニューで選択**すべてを保存**です。  
  
## <a name="configure-adapter-authentication"></a>アダプターの認証を構成します。  
  
1.  Visual Studio ソリューション ウィンドウで、ダブルクリック**app.config**です。  
  
2.  検索、`address`属性、`endpoint`要素。 これは次のようになります。  
  
    ```  
    <endpoint address="echov2://lobhostname/lobapplication?enableAuthentication=False&echoInUpperCase=True"  
        binding="echoAdapterBindingV2" bindingConfiguration="EchoAdapterBinding"  
        contract="EchoOutboundContract" name="EchoAdapterBinding_EchoOutboundContract" />  
    ```  
  
     変更**enableAuthentication**から**False**に**True**次のようにします。 資格情報をアダプターに渡す呼び出し元のアプリケーションが必要になります。  
  
    ```  
    <endpoint address="echov2://lobhostname/lobapplication?enableAuthentication=True&echoInUpperCase=True"  
        binding="echoAdapterBindingV2" bindingConfiguration="EchoAdapterBinding"  
        contract="EchoOutboundContract" name="EchoAdapterBinding_EchoOutboundContract" />  
    ```  
  
3.  クリックして、ソリューションを保存**ファイル**Visual Studio でメニュー**すべて保存**です。  
  
## <a name="create-a-sample-xml-file"></a>サンプル XML ファイルを作成します。  
  
1.  メモ帳のインスタンスを起動します。 [スタート] メニューを使用してクリックして**すべてのプログラム** &#124; **アクセサリ**を選択し**メモ帳**です。  
  
2.  メモ帳などのエディターに次のサンプル データをコピーします。  
  
    ```  
    <?xml version="1.0" encoding="utf-16"?>  
    <ns0:greeting xmlns:ns0="echov2://microsoft.adapters.samples.echov2/PreDefinedTypes">  
      <ns0:address>  
        <ns0:street1>123 Microsoft Way</ns0:street1>  
        <ns0:street2>Building # 4599</ns0:street2>  
        <ns0:city>Redmond</ns0:city>  
        <ns0:state>WA</ns0:state>  
        <ns0:zip>98052</ns0:zip>  
      </ns0:address>  
      <ns0:greetingText>Welcome to Redmond!</ns0:greetingText>  
    </ns0:greeting>              
    ```  
  
3.  メモ帳のメニューをクリックして**ファイル**を選択し**名前を付けて保存しています**. "CustomGreetingInstance.xml"ファイル名の入力しのエンコーディングの Unicode を選択し、プロジェクト ディレクトリまたは別の適切な場所に保存します。 完全なパスとファイル名の後で参照に注意してください。  
  
4.  ファイルが正常に保存されるときに、テキスト エディターを閉じます。  
  
## <a name="test-the-echo-adapter"></a>エコー アダプターをテストします。  
  
1.  ソリューション エクスプ ローラーで、 **Program.cs**ファイル。  
  
2.  Visual Studio エディターで、内部、 **Main**メソッド、生成された WCF クライアントのインスタンスを作成するコードの次の行を追加します。  
  
    ```csharp  
    EchoOutboundContractClient client = new EchoOutboundContractClient();  
    ```  
  
3.  これでアダプター用の資格情報を確立するコードを追加します。 エコー アダプタで認証が有効の場合、ユーザー名の有無が確認されますが、値を確認できません。  
  
    ```csharp  
    // pass client credentials  
    client.ClientCredentials.UserName.UserName = "username";  
    ```  
  
4.  EchoStrings 操作を呼び出すコードを追加して続行します。  
  
    ```csharp  
    // Invoke EchoStrings()  
    Console.WriteLine("Invoking EchoStrings() method against the adapter...");  
    string[] response = client.EchoStrings("Bonjour!");  
    foreach (string data in response)  
    {  
        Console.WriteLine(data);  
    }  
    ```  
  
5.  EchoGreetings 操作を呼び出すコードを追加して続行します。  
  
    ```csharp  
    // Invoke EchoGreetings()  
    Console.WriteLine("\nInvoking EchoGreetings() method against the adapter...");  
    microsoft.adapters.samples.echov2.Types.Greeting greeting = new microsoft.adapters.samples.echov2.Types.Greeting();  
    greeting.id = Guid.NewGuid();  
    greeting.sentDateTime = DateTime.Now;  
    greeting.greetingText = "Hello World!";  
    greeting.name = new microsoft.adapters.samples.echov2.Types.Name();  
    greeting.name.salutation = microsoft.adapters.samples.echov2.Types.Salutation.Miss;  
    greeting.name.firstName = "Jane";  
    greeting.name.middleName = "Z.";  
    greeting.name.lastName = "Smith";  
    microsoft.adapters.samples.echov2.Types.Greeting[] greetingArray = client.EchoGreetings(greeting);  
    foreach (microsoft.adapters.samples.echov2.Types.Greeting data in greetingArray)  
    {  
        Console.WriteLine(data.id + " " + data.sentDateTime + " " + data.greetingText + " " + data.name.firstName );  
    }  
    ```  
  
6.  EchoCustomGreetingsFromFile 操作を呼び出すコードを追加して続行します。  
  
    ```csharp  
    // Invoke EchoCustomGreetingFromFile()  
    Console.WriteLine("\nInvoking EchoCustomGreetingFromFile() method against the adapter ...");  
    // Copy the sample data from CustomGreeting-instance.xml file and place in appropriate folder  
    // as specified in the operation parameter  
    microsoft.adapters.samples.echov2.PreDefinedTypes.CustomGreeting   
    // change the Uri to point to the greeting instance xml file you created  
    customGreeting = client.EchoCustomGreetingFromFile(new Uri(@"c:\CustomGreetingInstance.xml"));  
    Console.WriteLine(customGreeting.greetingText + " " + customGreeting.address.city);  
    client.Close();  
    Console.ReadLine();  
    ```  
  
7.  EchoCustomGreetingsFromFile テスト コードでカスタムの案内応答は、前の手順で作成したファイルを使用しているかどうかを確認します。 ファイルの場所を反映するようにコードを変更します。  
  
8.  Visual Studio での**ファイル** メニューのをクリックして**すべて保存**です。  
  
9. アプリケーションを実行します。 次のような出力が表示されます。  
  
     **アダプターに対する EchoStrings() メソッドを呼び出す.**  
  
     **Bonjour!**  
  
     **Bonjour!**  
  
     **Bonjour!**  
  
     **Bonjour!**  
  
     **Bonjour!**  
  
     **アダプターに対する EchoGreetings() メソッドを呼び出す.**  
  
     **179665bb-db21-42ac-810e-77ebfa99d460 9/13/2007 3時 18分: 07 PM Hello World!加藤さん**  
  
     **179665bb-db21-42ac-810e-77ebfa99d460 9/13/2007 3時 18分: 07 PM Hello World!加藤さん**  
  
     **179665bb-db21-42ac-810e-77ebfa99d460 9/13/2007 3時 18分: 07 PM Hello World!加藤さん**  
  
     **179665bb-db21-42ac-810e-77ebfa99d460 9/13/2007 3時 18分: 07 PM Hello World!加藤さん**  
  
     **179665bb-db21-42ac-810e-77ebfa99d460 9/13/2007 3時 18分: 07 PM Hello World!加藤さん**  
  
     **アダプターに対する EchoCustomGreetingFromFile() メソッドを呼び出す.**  
  
     **Redmond へようこそ!Redmond**  
  
10. プログラムを停止するのには Enter キーを押します。  
  
## <a name="what-did-i-just-do"></a>でしただけは何ですか。  
 このステップでは、チュートリアル 1 で開発されたエコー アダプターによって公開される 3 つの送信操作用のテスト アプリケーションを作成します。 これを行うには、WCF サービスを生成、および WCF サービスをホストするためのコードを提供する、Visual Studio プロジェクトを作成します。 最後に、テスト アプリケーションを実行しました。  
  
## <a name="next-steps"></a>次の手順  
 受信操作をテストするに進みます[手順 2: エコー アダプターの受信ハンドラーのテスト](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-test-inbound-handler-of-the-echo-adapter.md)です。  
  
## <a name="see-also"></a>参照  
  [チュートリアル 2: .NET からエコー アダプターを使用します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md)   
 [手順 2: エコー アダプターの受信ハンドラーをテストする](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-test-inbound-handler-of-the-echo-adapter.md)