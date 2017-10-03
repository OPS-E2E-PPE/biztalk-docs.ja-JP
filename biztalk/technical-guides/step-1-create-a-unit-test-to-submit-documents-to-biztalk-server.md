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
# <a name="step-1-create-a-unit-test-to-submit-documents-to-biztalk-server"></a><span data-ttu-id="6e9d5-102">手順 1: BizTalk Server にドキュメントを送信する単体テストを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-102">Step 1: Create a Unit Test to Submit Documents to BizTalk Server</span></span>
<span data-ttu-id="6e9d5-103">BizTalk Server などのアプリケーション サーバーのコンピューターは、ユーザーに代わって特定のタスクを実行する設計されています。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-103">Computer application servers such as BizTalk Server are designed to perform particular tasks on behalf of users.</span></span> <span data-ttu-id="6e9d5-104">これらのタスクは、アプリケーション サーバーを認識するプロトコルを使用して、アプリケーション サーバーを理解している標準に準拠するメッセージとして、アプリケーション サーバーに送信されるクライアント要求として開始されます。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-104">These tasks are initiated as client requests sent to the application server as messages that conform to a standard that the application server understands, via a protocol that the application server understands.</span></span> <span data-ttu-id="6e9d5-105">たとえば、クライアントは、SMTP プロトコル経由での電子メール サーバーにインターネット電子メール メッセージを送信して電子メールの処理を開始する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-105">For example, clients may initiate processing of email by sending internet e-mail messages to an email server via the SMTP protocol.</span></span> <span data-ttu-id="6e9d5-106">同様に、HTML クライアントを処理する web サーバーまたはデータベース サーバーの ASP 要求がクライアント SQL 要求を処理され、BizTalk Server はクライアントのさまざまな業界標準プロトコルを使用して複数の業界メッセージ標準に準拠して書式設定のメッセージを処理できます。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-106">Likewise, web servers process client HTML or ASP requests, database servers process client SQL requests and BizTalk Server can process client messages formatted in compliance with multiple industry message standards using numerous industry standard protocols.</span></span> <span data-ttu-id="6e9d5-107">通常、アプリケーション サーバーのワークロードの容量は、一定時間内で、アプリケーション サーバーを処理できるメッセージの数によって測定されます。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-107">The workload capacity of an application server is typically measured by the number of messages that the application server can process in a given time period.</span></span> <span data-ttu-id="6e9d5-108">BizTalk Server のワークロードの容量が、時間、ビジー状態で workday なども長期間にわたっての「1 秒あたりに受信したドキュメント」、「1 秒あたりに処理されたドキュメント」、「1 秒あたりに完了したオーケストレーション」数の平均として測定同様に、作業 1 週間です。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-108">The workload capacity of BizTalk Server is likewise measured as the average number of “documents received per second”, “documents processed per second” and/or “orchestrations completed per second” over an extended period of time, such as a busy workday or even a work week.</span></span> <span data-ttu-id="6e9d5-109">Visual Studio 2010 ロード テストの機能は、最大数百台のサーバー アプリケーションに同時にアクセスするユーザーのロード プロファイルをシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-109">Visual Studio 2010 load test functionality can simulate a load profile of up to hundreds of users simultaneously accessing a server application.</span></span> <span data-ttu-id="6e9d5-110">このロード テスト機能は、今後の分析用のデータベースでこれらのメトリックを保存する機能と、選択した主要業績評価指標のリアルタイムのメトリックを提供します。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-110">This load testing functionality provides real time metrics for selected key performance indicators as well as the ability to store these metrics in a database for future analysis.</span></span> <span data-ttu-id="6e9d5-111">このドキュメントの説明のロード ユニットを作成する方法など、BizTalk Server アプリケーションをテストするために Visual Studio のテスト プロジェクトの使用をテスト、ロード テストを作成する方法に必要なパフォーマンス カウンター データをキャプチャするロード テストを構成する方法BizTalk Server アプリケーションの最大持続可能なスループット (MST) を決定します。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-111">This document desribes the use of Visual Studio Test projects for the purpose of load testing a BizTalk Server application, including how to create unit tests, how to create load tests and how to configure load tests to capture performance counter data required to determine the Maximum Sustainable Throughput (MST) of a BizTalk Server application.</span></span>  
  
## <a name="creating-a-visual-studio-unit-test-to-submit-documents-to-biztalk-server"></a><span data-ttu-id="6e9d5-112">BizTalk Server にドキュメントを送信する Visual Studio 単体テストの作成</span><span class="sxs-lookup"><span data-stu-id="6e9d5-112">Creating a Visual Studio Unit Test to Submit Documents to BizTalk Server</span></span>  
 <span data-ttu-id="6e9d5-113">Visual Studio の単体テストを参照して、 [Microsoft.VisualStudio.TestTools.UnitTesting](http://go.microsoft.com/fwlink/?LinkID=132293) (http://go.microsoft.com/fwlink/?LinkID=132293) の名前空間は単体テストのサポートを提供するいくつかのクラスを提供します。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-113">A Visual Studio Unit test references the [Microsoft.VisualStudio.TestTools.UnitTesting](http://go.microsoft.com/fwlink/?LinkID=132293) (http://go.microsoft.com/fwlink/?LinkID=132293) namespace which supplies several classes that provide support for unit testing.</span></span> <span data-ttu-id="6e9d5-114">特定の重要度、 [UnitTesting](http://go.microsoft.com/fwlink/?LinkID=132293) (http://go.microsoft.com/fwlink/?LinkID = 132293) 名前空間が含まれています、[また Microsoft.VisualStudio.TestTools.UnitTesting.TestContext](http://go.microsoft.com/fwlink/?LinkID=208233) (http://go.microsoft.com/fwlink/?LinkID = 208233) を単体テストに提供される情報を格納するクラスと[Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute](http://go.microsoft.com/fwlink/?LinkID=208235) (http://go.microsoft.com/fwlink/?LinkID = 208235) テスト メソッドを定義するクラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-114">Of particular importance, the [UnitTesting](http://go.microsoft.com/fwlink/?LinkID=132293) (http://go.microsoft.com/fwlink/?LinkID=132293) namespace includes the [Microsoft.VisualStudio.TestTools.UnitTesting.TestContext](http://go.microsoft.com/fwlink/?LinkID=208233) (http://go.microsoft.com/fwlink/?LinkID=208233) class to store information provided to Unit tests and the [Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute](http://go.microsoft.com/fwlink/?LinkID=208235) (http://go.microsoft.com/fwlink/?LinkID=208235) class is used to define Test methods.</span></span> <span data-ttu-id="6e9d5-115">ロード テストの BizTalk Server のために、テスト メソッドが読み込まれるメッセージとメッセージの送信先となるエンドポイントまたは URL で必要があります指定します。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-115">For purposes of load testing BizTalk Server, Test methods should specify the message to be loaded and the endpoint/URL to which the message should be sent.</span></span> <span data-ttu-id="6e9d5-116">エンドポイントの URL/は、対応する BizTalk 受信場所と、BizTalk Server にメッセージ エントリ ポイントが作成されると、機能します。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-116">The endpoint/URL will then serve as the message entry point into BizTalk Server when a corresponding BizTalk receive location is created.</span></span>  
  
 <span data-ttu-id="6e9d5-117">わかりやすくするため、このトピックのサンプル コードについて説明を利用したテスト メソッド、 [System.ServiceModel.ChannelFactory(TChannel)](http://go.microsoft.com/fwlink/?LinkId=208238) (http://go.microsoft.com/fwlink/?LinkID = 208238) 受信アダプターのクラスが監視して、BizTalk WCF カスタムおよび WCF net.tcp エンドポイントを使用するサービス エンドポイントにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-117">For purposes of illustration, the sample code in this topic describes Test methods which utilize the [System.ServiceModel.ChannelFactory(TChannel)](http://go.microsoft.com/fwlink/?LinkId=208238) (http://go.microsoft.com/fwlink/?LinkID=208238) class to send messages to service endpoints that use the WCF net.tcp endpoint and are monitored by the BizTalk WCF-Custom receive adapter.</span></span> <span data-ttu-id="6e9d5-118">テスト メッセージのサービス エンドポイントは、テスト プロジェクトのアプリケーション構成 (app.config) ファイルで定義されます。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-118">Service endpoints for test messages are defined in the Application Configuration (app.config) file of the Test project.</span></span>  
  
 <span data-ttu-id="6e9d5-119">Visual Studio の単体テストの詳細については、次を参照してください。[単体テストの構造](http://go.microsoft.com/fwlink/?LinkID=208232)(http://go.microsoft.com/fwlink/?LinkID=208232)。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-119">For more information about Visual Studio Unit Tests see [Anatomy of a Unit Test](http://go.microsoft.com/fwlink/?LinkID=208232) (http://go.microsoft.com/fwlink/?LinkID=208232).</span></span>  
  
 <span data-ttu-id="6e9d5-120">1 つまたは複数の BizTalk Server コンピューターにドキュメントを送信する単体テストでテスト プロジェクトを作成するには以下のセクションの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-120">Follow the steps in the sections below to create a Test project with a Unit Test to submit documents to one or more BizTalk Server computers.</span></span> <span data-ttu-id="6e9d5-121">Visual Studio 2010 Ultimate Edition を使用してこれらの手順が完了しました。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-121">These steps were completed using Visual Studio 2010 Ultimate Edition.</span></span>  
  
### <a name="set-visual-studio-2010-test-project-options"></a><span data-ttu-id="6e9d5-122">Visual Studio 2010 テスト プロジェクトのオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-122">Set Visual Studio 2010 Test Project Options</span></span>  
  
1.  <span data-ttu-id="6e9d5-123">Visual Studio 2010 Ultimate edition を起動します。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-123">Launch Visual Studio 2010 Ultimate edition.</span></span> <span data-ttu-id="6e9d5-124">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Visual Studio 2010**  をクリックし、 **Microsoft Visual Studio 2010**です。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-124">Click **Start**, point to **All Programs**, point to **Microsoft Visual Studio 2010** and then click **Microsoft Visual Studio 2010**.</span></span>  
  
2.  <span data-ttu-id="6e9d5-125">Visual Studio 2010 でクリックして**ツール** をクリックし、**オプション**を表示する、**オプション** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-125">In Visual Studio 2010, click **Tools** and then click **Options** to display the **Options** dialog box.</span></span>  
  
3.  <span data-ttu-id="6e9d5-126">クリックして展開**テスト ツール** をクリックし、**テスト プロジェクト**新しいテスト プロジェクトを作成するためのオプションを表示します。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-126">Click to expand **Test Tools** and then click **Test Project** to display options for creation of new test projects.</span></span>  
  
4.  <span data-ttu-id="6e9d5-127">設定、**テスト プロジェクトの既定の言語:**に**Visual c# テスト プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-127">Set the **Default test project language:** to **Visual C# test project**.</span></span>  
  
5.  <span data-ttu-id="6e9d5-128">オプションを **は既定では、新しいテスト プロジェクトに追加するファイルを選択:**選択**Visual c# テスト プロジェクト**、Visual c# 用のテストの種類のすべてのテストを除くプロジェクトをオフに**単体テスト**です。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-128">Under the option to **Select the files that will be added to each new test project, by default:** select **Visual C# test project**, and uncheck all of the test types for Visual C# test projects except for **Unit Test**.</span></span>  
  
6.  <span data-ttu-id="6e9d5-129">**[OK]** をクリックして、 **[オプション]** ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-129">Click **OK** to close the **Options** dialog box.</span></span>  
  
### <a name="create-a-new-visual-studio-2010-solution-with-a-test-project"></a><span data-ttu-id="6e9d5-130">テスト プロジェクトで、新しい Visual Studio 2010 ソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-130">Create a new Visual Studio 2010 Solution with a Test Project</span></span>  
  
1.  <span data-ttu-id="6e9d5-131">フォルダーを作成して**C:\Projects** Visual Studio 2010 Ultimate のコンピューターにします。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-131">Create the folder **C:\Projects** on the Visual Studio 2010 Ultimate computer.</span></span>  
  
2.  <span data-ttu-id="6e9d5-132">Visual Studio 2010 でをクリックして**ファイル**、指す**新規**、 をクリック**プロジェクト**を表示する、**新しいプロジェクト** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-132">In Visual Studio 2010 click **File**, point to **New**, and click **Project** to display the **New Project** dialog box.</span></span>  
  
3.  <span data-ttu-id="6e9d5-133">[**インストールされたテンプレート**をクリックして展開**Visual c#**、] をクリック**テスト**です。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-133">Under **Installed Templates** click to expand **Visual C#**, and click **Test**.</span></span>  
  
4.  <span data-ttu-id="6e9d5-134">下部にある、**新しいプロジェクト** ダイアログ ボックスは、次のオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-134">At the bottom of the **New Project** dialog box specify the following options:</span></span>  
  
    -   <span data-ttu-id="6e9d5-135">**[名前]:**</span><span class="sxs-lookup"><span data-stu-id="6e9d5-135">**Name:**</span></span>  
         <span data-ttu-id="6e9d5-136">**BTSLoad**</span><span class="sxs-lookup"><span data-stu-id="6e9d5-136">**BTSLoad**</span></span>  
  
    -   <span data-ttu-id="6e9d5-137">**場所:**</span><span class="sxs-lookup"><span data-stu-id="6e9d5-137">**Location:**</span></span>  
         <span data-ttu-id="6e9d5-138">**C:\Projects\\**</span><span class="sxs-lookup"><span data-stu-id="6e9d5-138">**C:\Projects\\**</span></span>  
  
    -   <span data-ttu-id="6e9d5-139">**ソリューション名:**</span><span class="sxs-lookup"><span data-stu-id="6e9d5-139">**Solution name:**</span></span>  
         <span data-ttu-id="6e9d5-140">**ロード テスト**</span><span class="sxs-lookup"><span data-stu-id="6e9d5-140">**LoadTest**</span></span>  
  
5.  <span data-ttu-id="6e9d5-141">いることを確認するためのオプション**ソリューションのディレクトリを作成**がチェックされ、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-141">Ensure that the option to **Create directory for solution** is checked and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="6e9d5-142">BTSLoad プロジェクトにフォルダーを追加します。このフォルダーは、BizTalk Server に送信するテスト メッセージが格納されます。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-142">Add a folder to the BTSLoad project; this folder will contain test messages to be submitted to BizTalk Server.</span></span> <span data-ttu-id="6e9d5-143">ソリューション エクスプ ローラーでプロジェクトを右クリックして、BTSLoad をポイントし、**追加**、 をクリック**新しいフォルダー**です。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-143">In Solution Explorer, right-click the BTSLoad project, point to **Add**, and click **New Folder**.</span></span> <span data-ttu-id="6e9d5-144">フォルダー アイコンを強調表示されたテキストを**NewFolder1** BTSLoad プロジェクトの種類の下に表示されます**TestMessages**キーを押すと強調表示されたテキストを変更、 **Enter**キーC:\Projects\LoadTest\BTSLoad\TestMessages フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-144">A folder icon with the highlighted text **NewFolder1** will appear under the BTSLoad project, type **TestMessages** to change the highlighted text and press the **Enter** key to create the folder C:\Projects\LoadTest\BTSLoad\TestMessages.</span></span>  
  
### <a name="update-the-code-in-the-test-project-and-add-an-application-configuration-file-to-the-test-project"></a><span data-ttu-id="6e9d5-145">テスト プロジェクトでコードを更新し、テスト プロジェクトに、アプリケーション構成ファイルを追加</span><span class="sxs-lookup"><span data-stu-id="6e9d5-145">Update the Code in the Test Project and add an Application Configuration File to the Test Project</span></span>  
  
1.  <span data-ttu-id="6e9d5-146">ソリューション エクスプ ローラーをクリックして選択で**UnitTest1.cs**し、既存のコードを次のサンプル コードの一覧に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-146">In Solution Explorer click to select **UnitTest1.cs** and replace the existing code with the following sample code listing:</span></span>  
  
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
  
2.  <span data-ttu-id="6e9d5-147">テスト プロジェクトには、アプリケーション構成ファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-147">Add an Application Configuration file to the Test project:</span></span>  
  
    1.  <span data-ttu-id="6e9d5-148">ソリューション エクスプ ローラーでプロジェクトを右クリックして、BTSLoad をポイントし、**追加** をクリック**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-148">In Solution Explorer, right-click the BTSLoad project, point to **Add** and click **New item**.</span></span>  
  
    2.  <span data-ttu-id="6e9d5-149">**新しい項目の追加**ダイアログ ボックスで、**インストールされたテンプレート**をクリックして**全般**です。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-149">In the **Add New Item** dialog box, under **Installed Templates**, click **General**.</span></span>  
  
    3.  <span data-ttu-id="6e9d5-150">表示される項目の一覧でクリックして選択**アプリケーション構成ファイル** をクリックし、**追加**です。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-150">In the list of items that are displayed click to select **Application Configuration File** and then click **Add**.</span></span>  
  
    4.  <span data-ttu-id="6e9d5-151">ソリューション エクスプ ローラーで、app.config ファイルを選択し、app.config ファイルの内容を以下に一覧表示するサンプル コードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-151">In Solution Explorer select the app.config file and replace the contents of the app.config file with the sample code listing below:</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="6e9d5-152">このファイルで定義されている各クライアント エンドポイントの*BizTalk Server コンピューター*に対するテストが実行するコンピューターを読み込む、BizTalk Server の実際の名前のプレース ホルダーです。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-152">For each client endpoint defined in this file, *BizTalk Server Computer* is a placeholder for the actual name of the BizTalk Server computer(s) that you will perform load testing against.</span></span>  
  
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
  
    5.  <span data-ttu-id="6e9d5-153">クリックして、**ファイル**メニューをクリックして Visual Studio 2010**すべて保存**です。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-153">Click the **File** menu in Visual Studio 2010 and then click **Save All**.</span></span>  
  
### <a name="add-a-test-message-to-the-project"></a><span data-ttu-id="6e9d5-154">テスト メッセージをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-154">Add a Test Message to the Project</span></span>  
 <span data-ttu-id="6e9d5-155">この例の目的は、BizTalk Server の場所の送受信ポートが使用するよう構成するパイプラインを通過し、任意のドキュメントの検証は行われません。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-155">For purposes of this example, BizTalk Server receive location(s) and send port(s) will be configured to use pass through pipelines and will not perform any document validation.</span></span> <span data-ttu-id="6e9d5-156">プロジェクトにテスト メッセージを追加する手順に従います。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-156">Follow these steps to add a test message to the project:</span></span>  
  
1.  <span data-ttu-id="6e9d5-157">メモ帳を起動します。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-157">Launch Notepad.</span></span> <span data-ttu-id="6e9d5-158">をクリックして**開始**、 をクリックして**実行**と種類**メモ帳**で、**実行** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-158">Click **Start**, click **Run** and type **Notepad** in the **Run** dialog box.</span></span>  
  
2.  <span data-ttu-id="6e9d5-159">次のテキストをメモ帳にコピーし、"C:\Projects\LoadTest\BTSLoad\TestMessages\TestXmlDocument.xml"として保存</span><span class="sxs-lookup"><span data-stu-id="6e9d5-159">Copy the following text into Notepad and save as “C:\Projects\LoadTest\BTSLoad\TestMessages\TestXmlDocument.xml”</span></span>  
  
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
  
3.  <span data-ttu-id="6e9d5-160">メモ帳を閉じます。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-160">Close Notepad.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6e9d5-161">このファイルは、複数のロード テスト エージェント コンピューターがロード テストのために使用される場合は、すべてのロード テスト エージェント コンピューターで同じファイル名を使用して同じパスに保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-161">This file will need to be saved to the same path using the same file name on every Load Test Agent computer if multiple Load Test Agent computers are used for load testing.</span></span>  
  
### <a name="add-necessary-references-to-the-project-and-build-the-test-project"></a><span data-ttu-id="6e9d5-162">プロジェクトに必要な参照を追加し、テスト プロジェクトをビルド</span><span class="sxs-lookup"><span data-stu-id="6e9d5-162">Add Necessary References to the Project and Build the Test Project</span></span>  
  
1.  <span data-ttu-id="6e9d5-163">ソリューション エクスプ ローラーで右クリックし、**参照**フォルダーをクリックして BTSLoad プロジェクト**参照の追加**です。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-163">In Solution Explorer, right-click the **References** folder for the BTSLoad project and then click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="6e9d5-164">参照の追加 ダイアログ ボックス、 **.NET**  タブを使用して、ctrl キーを押しながらクリック キーボードとマウスの組み合わせを同時に次の .NET 名前空間を選択します。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-164">In the Add Reference dialog box, click the **.NET** tab and use the CTRL+Click keyboard/mouse combination to simultaneously select the following .NET namespaces:</span></span>  
  
    -   <span data-ttu-id="6e9d5-165">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="6e9d5-165">System.Configuration</span></span>  
  
    -   <span data-ttu-id="6e9d5-166">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="6e9d5-166">System.Runtime.Serialization</span></span>  
  
    -   <span data-ttu-id="6e9d5-167">System.ServiceModel.Channels</span><span class="sxs-lookup"><span data-stu-id="6e9d5-167">System.ServiceModel.Channels</span></span>  
  
    -   <span data-ttu-id="6e9d5-168">System.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="6e9d5-168">System.ServiceModel</span></span>  
  
    -   <span data-ttu-id="6e9d5-169">System.Web.Extensions</span><span class="sxs-lookup"><span data-stu-id="6e9d5-169">System.Web.Extensions</span></span>  
  
    -   <span data-ttu-id="6e9d5-170">System.Xml</span><span class="sxs-lookup"><span data-stu-id="6e9d5-170">System.Xml</span></span>  
  
3.  <span data-ttu-id="6e9d5-171">名前空間を選択してからクリックして**OK** BTSLoad テスト プロジェクトへの参照としてこれらのアセンブリを追加します。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-171">After selecting the namespaces click **OK** to add these assemblies as references to the BTSLoad Test project.</span></span>  
  
4.  <span data-ttu-id="6e9d5-172">右クリックして、 **BTSLoad**クリックしてプロジェクト**ビルド**BTSLoad アセンブリにプロジェクトをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="6e9d5-172">Right click the **BTSLoad** project and then click **Build** to compile the project into the BTSLoad assembly.</span></span>