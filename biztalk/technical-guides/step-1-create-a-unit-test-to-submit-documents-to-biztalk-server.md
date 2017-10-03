---
title: "手順 1: BizTalk Server にドキュメントを送信する単体テストの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 688b14e4-bb16-4d12-86b8-37b8b6808472
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8016bc237b55c2404a21c91e2e68d78fdd21bcf9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-create-a-unit-test-to-submit-documents-to-biztalk-server"></a>手順 1: BizTalk Server にドキュメントを送信する単体テストを作成します。
BizTalk Server などのアプリケーション サーバーのコンピューターは、ユーザーに代わって特定のタスクを実行する設計されています。 これらのタスクは、アプリケーション サーバーを認識するプロトコルを使用して、アプリケーション サーバーを理解している標準に準拠するメッセージとして、アプリケーション サーバーに送信されるクライアント要求として開始されます。 たとえば、クライアントは、SMTP プロトコル経由での電子メール サーバーにインターネット電子メール メッセージを送信して電子メールの処理を開始する可能性があります。 同様に、HTML クライアントを処理する web サーバーまたはデータベース サーバーの ASP 要求がクライアント SQL 要求を処理され、BizTalk Server はクライアントのさまざまな業界標準プロトコルを使用して複数の業界メッセージ標準に準拠して書式設定のメッセージを処理できます。 通常、アプリケーション サーバーのワークロードの容量は、一定時間内で、アプリケーション サーバーを処理できるメッセージの数によって測定されます。 BizTalk Server のワークロードの容量が、時間、ビジー状態で workday なども長期間にわたっての「1 秒あたりに受信したドキュメント」、「1 秒あたりに処理されたドキュメント」、「1 秒あたりに完了したオーケストレーション」数の平均として測定同様に、作業 1 週間です。 Visual Studio 2010 ロード テストの機能は、最大数百台のサーバー アプリケーションに同時にアクセスするユーザーのロード プロファイルをシミュレートできます。 このロード テスト機能は、今後の分析用のデータベースでこれらのメトリックを保存する機能と、選択した主要業績評価指標のリアルタイムのメトリックを提供します。 このドキュメントの説明のロード ユニットを作成する方法など、BizTalk Server アプリケーションをテストするために Visual Studio のテスト プロジェクトの使用をテスト、ロード テストを作成する方法に必要なパフォーマンス カウンター データをキャプチャするロード テストを構成する方法BizTalk Server アプリケーションの最大持続可能なスループット (MST) を決定します。  
  
## <a name="creating-a-visual-studio-unit-test-to-submit-documents-to-biztalk-server"></a>BizTalk Server にドキュメントを送信する Visual Studio 単体テストの作成  
 Visual Studio の単体テストを参照して、 [Microsoft.VisualStudio.TestTools.UnitTesting](http://go.microsoft.com/fwlink/?LinkID=132293) (http://go.microsoft.com/fwlink/?LinkID=132293) の名前空間は単体テストのサポートを提供するいくつかのクラスを提供します。 特定の重要度、 [UnitTesting](http://go.microsoft.com/fwlink/?LinkID=132293) (http://go.microsoft.com/fwlink/?LinkID = 132293) 名前空間が含まれています、[また Microsoft.VisualStudio.TestTools.UnitTesting.TestContext](http://go.microsoft.com/fwlink/?LinkID=208233) (http://go.microsoft.com/fwlink/?LinkID = 208233) を単体テストに提供される情報を格納するクラスと[Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute](http://go.microsoft.com/fwlink/?LinkID=208235) (http://go.microsoft.com/fwlink/?LinkID = 208235) テスト メソッドを定義するクラスを使用します。 ロード テストの BizTalk Server のために、テスト メソッドが読み込まれるメッセージとメッセージの送信先となるエンドポイントまたは URL で必要があります指定します。 エンドポイントの URL/は、対応する BizTalk 受信場所と、BizTalk Server にメッセージ エントリ ポイントが作成されると、機能します。  
  
 わかりやすくするため、このトピックのサンプル コードについて説明を利用したテスト メソッド、 [System.ServiceModel.ChannelFactory(TChannel)](http://go.microsoft.com/fwlink/?LinkId=208238) (http://go.microsoft.com/fwlink/?LinkID = 208238) 受信アダプターのクラスが監視して、BizTalk WCF カスタムおよび WCF net.tcp エンドポイントを使用するサービス エンドポイントにメッセージを送信します。 テスト メッセージのサービス エンドポイントは、テスト プロジェクトのアプリケーション構成 (app.config) ファイルで定義されます。  
  
 Visual Studio の単体テストの詳細については、次を参照してください。[単体テストの構造](http://go.microsoft.com/fwlink/?LinkID=208232)(http://go.microsoft.com/fwlink/?LinkID=208232)。  
  
 1 つまたは複数の BizTalk Server コンピューターにドキュメントを送信する単体テストでテスト プロジェクトを作成するには以下のセクションの手順に従います。 Visual Studio 2010 Ultimate Edition を使用してこれらの手順が完了しました。  
  
### <a name="set-visual-studio-2010-test-project-options"></a>Visual Studio 2010 テスト プロジェクトのオプションを設定します。  
  
1.  Visual Studio 2010 Ultimate edition を起動します。 をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Visual Studio 2010**  をクリックし、 **Microsoft Visual Studio 2010**です。  
  
2.  Visual Studio 2010 でクリックして**ツール** をクリックし、**オプション**を表示する、**オプション** ダイアログ ボックス。  
  
3.  クリックして展開**テスト ツール** をクリックし、**テスト プロジェクト**新しいテスト プロジェクトを作成するためのオプションを表示します。  
  
4.  設定、**テスト プロジェクトの既定の言語:**に**Visual c# テスト プロジェクト**です。  
  
5.  オプションを **は既定では、新しいテスト プロジェクトに追加するファイルを選択:**選択**Visual c# テスト プロジェクト**、Visual c# 用のテストの種類のすべてのテストを除くプロジェクトをオフに**単体テスト**です。  
  
6.  **[OK]** をクリックして、 **[オプション]** ダイアログ ボックスを閉じます。  
  
### <a name="create-a-new-visual-studio-2010-solution-with-a-test-project"></a>テスト プロジェクトで、新しい Visual Studio 2010 ソリューションを作成します。  
  
1.  フォルダーを作成して**C:\Projects** Visual Studio 2010 Ultimate のコンピューターにします。  
  
2.  Visual Studio 2010 でをクリックして**ファイル**、指す**新規**、 をクリック**プロジェクト**を表示する、**新しいプロジェクト** ダイアログ ボックス。  
  
3.  [**インストールされたテンプレート**をクリックして展開**Visual c#**、] をクリック**テスト**です。  
  
4.  下部にある、**新しいプロジェクト** ダイアログ ボックスは、次のオプションを指定します。  
  
    -   **[名前]:**  
         **BTSLoad**  
  
    -   **場所:**  
         **C:\Projects\\**  
  
    -   **ソリューション名:**  
         **ロード テスト**  
  
5.  いることを確認するためのオプション**ソリューションのディレクトリを作成**がチェックされ、をクリックして**OK**です。  
  
6.  BTSLoad プロジェクトにフォルダーを追加します。このフォルダーは、BizTalk Server に送信するテスト メッセージが格納されます。 ソリューション エクスプ ローラーでプロジェクトを右クリックして、BTSLoad をポイントし、**追加**、 をクリック**新しいフォルダー**です。 フォルダー アイコンを強調表示されたテキストを**NewFolder1** BTSLoad プロジェクトの種類の下に表示されます**TestMessages**キーを押すと強調表示されたテキストを変更、 **Enter**キーC:\Projects\LoadTest\BTSLoad\TestMessages フォルダーを作成します。  
  
### <a name="update-the-code-in-the-test-project-and-add-an-application-configuration-file-to-the-test-project"></a>テスト プロジェクトでコードを更新し、テスト プロジェクトに、アプリケーション構成ファイルを追加  
  
1.  ソリューション エクスプ ローラーをクリックして選択で**UnitTest1.cs**し、既存のコードを次のサンプル コードの一覧に置き換えます。  
  
    ```csharp  
    #region Using Directives  
    using System;  
    using System.IO;  
    using System.Diagnostics;  
    using System.Text;  
    using System.Configuration;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Xml;  
    using System.ServiceModel;  
    using System.ServiceModel.Channels;  
    using Microsoft.VisualStudio.TestTools.UnitTesting;  
    #endregion  
  
    namespace Microsoft.BizTalk.Samples  
    {  
        [TestClass]  
        public class BTSLoadTest  
        {  
            #region Constants  
            private const int MaxBufferSize = 2097152;  
            private const string Source = "BTS Load Test";  
            private const string Star = "*";  
            private const string TestMessageFolderParameter = "testMessageFolder";  
            private const string TestMessageFolderDefault = @"C:\Projects\LoadTest\BTSLoad\TestMessages";  
            private const string TestMessageFolderFormat = @"Test Message Folder = {0}";  
            private const string TestXmlDocument = "testxmldocument.xml";  
            #endregion  
  
            #region Private Instance Fields  
            private TestContext testContextInstance;  
            #endregion  
  
            #region Private ThreadStatic Fields  
            [ThreadStatic]  
            private static ChannelFactory<IRequestChannel> channelFactory;  
            [ThreadStatic]  
            private static IRequestChannel channel = null;  
            [ThreadStatic]  
            private static byte[] buffer = null;  
            #endregion  
  
            #region Private Static Fields  
            private static string testMessageFolder = null;  
            #endregion  
  
            #region Public Instance Constructor  
            public BTSLoadTest()  
            {  
            }  
            #endregion  
  
            #region Public Static Constructor  
            static BTSLoadTest()  
            {  
                try  
                {  
                    testMessageFolder = ConfigurationManager.AppSettings[TestMessageFolderParameter];  
                    if (string.IsNullOrEmpty(testMessageFolder))  
                    {  
                        testMessageFolder = TestMessageFolderDefault;  
                    }  
                }  
                catch (Exception ex)  
                {  
                    Trace.WriteLine(ex.Message);  
                    EventLog.WriteEntry(Source, ex.Message, EventLogEntryType.Error);  
                }  
            }  
            #endregion  
  
            #region Public Properties  
            /// <summary>  
            ///Gets or sets the test context which provides  
            ///information about and functionality for the current test run.  
            ///</summary>  
            public TestContext TestContext  
            {  
                get  
                {  
                    return testContextInstance;  
                }  
                set  
                {  
                    testContextInstance = value;  
                }  
            }  
            #endregion  
  
            #region Test Methods  
  
            [TestMethod]  
            public void BTSMessaging()  
            {  
                InvokeBizTalkReceiveLocation("BTSMessagingEP",  
                                               testMessageFolder,  
                                               TestXmlDocument,  
                                               MessageVersion.Default,  
                                               SessionMode.Allowed);  
            }  
  
            [TestMethod]  
            public void BTSMessaging2()  
            {  
                InvokeBizTalkReceiveLocation("BTSMessagingEP2",  
                                               testMessageFolder,  
                                               TestXmlDocument,  
                                               MessageVersion.Default,  
                                               SessionMode.Allowed);  
            }  
  
            [TestMethod]  
            public void BTSOrchestration()  
            {  
                InvokeBizTalkReceiveLocation("BTSOrchestrationEP",  
                                               testMessageFolder,  
                                               TestXmlDocument,  
                                               MessageVersion.Default,  
                                               SessionMode.Allowed);  
            }  
            #endregion  
  
            #region Helper Methods  
            public void InvokeBizTalkReceiveLocation(string endpointConfigurationName,  
                                               string requestMessageFolder,  
                                               string requestMessageName,  
                                               MessageVersion messageVersion,  
                                               SessionMode sessionMode)  
            {  
                XmlTextReader xmlTextReader = null;  
                Message requestMessage = null;  
                Message responseMessage = null;  
  
                try  
                {  
                    if (channel == null || channel.State != CommunicationState.Opened)  
                    {  
                        channelFactory = new ChannelFactory<IRequestChannel>(endpointConfigurationName);  
                        channelFactory.Endpoint.Contract.SessionMode = sessionMode;  
                        channel = channelFactory.CreateChannel();  
                    }  
                    if (buffer == null)  
                    {  
                        string path = Path.Combine(requestMessageFolder, requestMessageName);  
  
                        string message;  
                        using (StreamReader reader = new StreamReader(File.Open(path, FileMode.Open, FileAccess.Read, FileShare.Read)))  
                        {  
                            message = reader.ReadToEnd();  
                        }  
                        buffer = Encoding.UTF8.GetBytes(message);  
                    }  
                    MemoryStream stream = new MemoryStream(buffer);  
                    xmlTextReader = new XmlTextReader(stream);  
                    requestMessage = Message.CreateMessage(messageVersion, Star, xmlTextReader);  
                    TestContext.BeginTimer(requestMessageName);  
                    responseMessage = channel.Request(requestMessage);  
                }  
                catch (FaultException ex)  
                {  
                    HandleException(ex);  
                    throw;  
                }  
                catch (CommunicationException ex)  
                {  
                    HandleException(ex);  
                    throw;  
                }  
                catch (TimeoutException ex)  
                {  
                    HandleException(ex);  
                    throw;  
                }  
                catch (Exception ex)  
                {  
                    HandleException(ex);  
                    throw;  
                }  
                finally  
                {  
                    TestContext.EndTimer(requestMessageName);  
                    CloseObjects(xmlTextReader,  
                                 requestMessage,  
                                 responseMessage);  
                }  
            }  
  
            private void HandleException(Exception ex)  
            {  
                try  
                {  
                    Trace.WriteLine(ex.Message);  
                    EventLog.WriteEntry(Source, ex.Message, EventLogEntryType.Error);  
                }  
                catch (Exception)  
                {  
                }  
            }  
  
            private void CloseObjects(XmlTextReader xmlTextReader,  
                               Message requestMessage,  
                               Message responseMessage)  
            {  
                try  
                {  
                    if (xmlTextReader != null)  
                    {  
                        xmlTextReader.Close();  
                    }  
                    if (requestMessage != null)  
                    {  
                        requestMessage.Close();  
                    }  
                    if (responseMessage != null)  
                    {  
                        responseMessage.Close();  
                    }  
                }  
                catch (Exception)  
                {  
                }  
            }  
  
            #endregion  
        }  
    }  
    ```  
  
2.  テスト プロジェクトには、アプリケーション構成ファイルを追加します。  
  
    1.  ソリューション エクスプ ローラーでプロジェクトを右クリックして、BTSLoad をポイントし、**追加** をクリック**新しい項目の**します。  
  
    2.  **新しい項目の追加**ダイアログ ボックスで、**インストールされたテンプレート**をクリックして**全般**です。  
  
    3.  表示される項目の一覧でクリックして選択**アプリケーション構成ファイル** をクリックし、**追加**です。  
  
    4.  ソリューション エクスプ ローラーで、app.config ファイルを選択し、app.config ファイルの内容を以下に一覧表示するサンプル コードに置き換えます。  
  
        > [!IMPORTANT]  
        >  このファイルで定義されている各クライアント エンドポイントの*BizTalk Server コンピューター*に対するテストが実行するコンピューターを読み込む、BizTalk Server の実際の名前のプレース ホルダーです。  
  
        ```xml  
  
        <configuration>  
          <system.serviceModel>  
            <!-- Bindings used by client endpoints -->  
            <bindings>  
              <netTcpBinding>  
                <binding name="netTcpBinding" closeTimeout="01:10:00" openTimeout="01:10:00" receiveTimeout="01:10:00" sendTimeout="01:10:00" transactionFlow="false" transferMode="Buffered" transactionProtocol="OleTransactions" hostNameComparisonMode="StrongWildcard" listenBacklog="100" maxBufferPoolSize="1048576" maxBufferSize="10485760" maxConnections="400" maxReceivedMessageSize="10485760">  
                  <readerQuotas maxDepth="32" maxStringContentLength="8192" maxArrayLength="16384" maxBytesPerRead="4096" maxNameTableCharCount="16384" />  
                  <reliableSession ordered="true" inactivityTimeout="00:10:00" enabled="false" />  
                  <security mode="None">  
                    <transport clientCredentialType="Windows" protectionLevel="EncryptAndSign" />  
                    <message clientCredentialType="Windows" />  
                  </security>  
                </binding>  
              </netTcpBinding>  
            </bindings>  
            <client>  
              <!-- Client endpoints used to exchange messages with WCF Receive Locations -->  
  
              <!-- BTSMessagingEP -->  
              <endpoint address="net.tcp://BizTalk Server Computer:8123/btsloadtest" binding="netTcpBinding" bindingConfiguration="netTcpBinding" contract="System.ServiceModel.Channels.IRequestChannel" name="BTSMessagingEP" />  
              <endpoint address="net.tcp://BizTalk Server Computer:8123/btsloadtest" binding="netTcpBinding" bindingConfiguration="netTcpBinding" contract="System.ServiceModel.Channels.IRequestChannel" name="BTSMessagingEP" />  
  
              <!-- BTSOrchestrationEP -->  
              <endpoint address="net.tcp://BizTalk Server Computer:8122/btsloadtest" binding="netTcpBinding" bindingConfiguration="netTcpBinding" contract="System.ServiceModel.Channels.IRequestChannel" name="BTSOrchestrationEP" />  
            </client>  
          </system.serviceModel>  
          <appSettings>  
            <!-- Folder containing test messages -->  
            <add key="testMessageFolder" value="C:\Projects\LoadTest\BTSLoad\TestMessages" />  
            <add key="ClientSettingsProvider.ServiceUri" value="" />  
          </appSettings>  
        </configuration>  
        ```  
  
    5.  クリックして、**ファイル**メニューをクリックして Visual Studio 2010**すべて保存**です。  
  
### <a name="add-a-test-message-to-the-project"></a>テスト メッセージをプロジェクトに追加します。  
 この例の目的は、BizTalk Server の場所の送受信ポートが使用するよう構成するパイプラインを通過し、任意のドキュメントの検証は行われません。 プロジェクトにテスト メッセージを追加する手順に従います。  
  
1.  メモ帳を起動します。 をクリックして**開始**、 をクリックして**実行**と種類**メモ帳**で、**実行** ダイアログ ボックス。  
  
2.  次のテキストをメモ帳にコピーし、"C:\Projects\LoadTest\BTSLoad\TestMessages\TestXmlDocument.xml"として保存  
  
    ```  
    <BTSLoadTest xmlns="http://Microsoft.BizTalk.Samples.BTSLoadTest">  
    <MessageText>  
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    </MessageText>  
    </BTSLoadTest>  
    ```  
  
3.  メモ帳を閉じます。  
  
> [!IMPORTANT]  
>  このファイルは、複数のロード テスト エージェント コンピューターがロード テストのために使用される場合は、すべてのロード テスト エージェント コンピューターで同じファイル名を使用して同じパスに保存する必要があります。  
  
### <a name="add-necessary-references-to-the-project-and-build-the-test-project"></a>プロジェクトに必要な参照を追加し、テスト プロジェクトをビルド  
  
1.  ソリューション エクスプ ローラーで右クリックし、**参照**フォルダーをクリックして BTSLoad プロジェクト**参照の追加**です。  
  
2.  参照の追加 ダイアログ ボックス、 **.NET**  タブを使用して、ctrl キーを押しながらクリック キーボードとマウスの組み合わせを同時に次の .NET 名前空間を選択します。  
  
    -   System.Configuration  
  
    -   System.Runtime.Serialization  
  
    -   System.ServiceModel.Channels  
  
    -   System.ServiceModel  
  
    -   System.Web.Extensions  
  
    -   System.Xml  
  
3.  名前空間を選択してからクリックして**OK** BTSLoad テスト プロジェクトへの参照としてこれらのアセンブリを追加します。  
  
4.  右クリックして、 **BTSLoad**クリックしてプロジェクト**ビルド**BTSLoad アセンブリにプロジェクトをコンパイルします。