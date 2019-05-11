---
title: Web サービスのトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c32bf542-dcc6-4727-b31f-52bb19d4b89d
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d50e7e47b1e774aca8fc0f2a63e8cd86e2a33af
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253636"
---
# <a name="troubleshooting-web-services"></a><span data-ttu-id="663e7-102">Web サービスのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="663e7-102">Troubleshooting Web Services</span></span>
<span data-ttu-id="663e7-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には Web サービスが広く採用され、SOAP アダプターで使用したり、オーケストレーションを Web サービスとして公開したりできるようになっています。</span><span class="sxs-lookup"><span data-stu-id="663e7-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] makes extensive use of Web services for use with the SOAP adapter and when publishing orchestrations as Web services.</span></span> <span data-ttu-id="663e7-104">このトピックでは、Web サービスだけでなく Web サービスの一般的な問題とそれらの問題を解決する方法のトラブルシューティングに利用できるいくつかの手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="663e7-104">This topic provides some steps that you can follow to troubleshoot Web services, as well as some common Web services problems and how to resolve those problems.</span></span>  
  
## <a name="use-net-framework-tracing-to-capture-and-log-errors-in-a-web-service"></a><span data-ttu-id="663e7-105">.NET Framework のトレースを使用してキャプチャし、Web サービスでエラーのログ</span><span class="sxs-lookup"><span data-stu-id="663e7-105">Use .NET Framework tracing to capture and log errors in a Web service</span></span>  
 <span data-ttu-id="663e7-106">.NET Framework **System.Diagnostics.Trace**をキャプチャしてテキスト ファイルにエラーを書き込むクラスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="663e7-106">The .NET Framework **System.Diagnostics.Trace** class can be used to capture and write errors to a text file.</span></span>  
  
#### <a name="to-use-the-systemdiagnosticstrace-class-to-capture-and-write-errors-to-a-text-file"></a><span data-ttu-id="663e7-107">System.Diagnostics.Trace クラスでエラーをキャプチャしてテキスト ファイルに書き込むには</span><span class="sxs-lookup"><span data-stu-id="663e7-107">To use the System.Diagnostics.Trace class to capture and write errors to a text file</span></span>  
  
1. <span data-ttu-id="663e7-108">設定する Web サービスの web.config ファイルを更新、**トレース**コンパイラ ディレクティブを**true**を追加し、 **TraceSwitch**値。</span><span class="sxs-lookup"><span data-stu-id="663e7-108">Update the web.config file for the Web service to set the **TRACE** compiler directive to **true** and add a **TraceSwitch** value:</span></span>  
  
   ```  
   <?xml version="1.0"?>  
   <configuration>  
     <system.codedom>  
       <compilers>  
         <compiler language="c#;cs;csharp"   
                   extension=".cs"   
                   compilerOptions="/d:TRACE"  
                   type="Microsoft.CSharp.CSharpCodeProvider, System, Version=2.0.3500.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" warningLevel="1" />  
         </compilers>  
     </system.codedom>  
     <system.diagnostics>  
       <switches>  
         <add name="WebSvcTraceSwitch" value="2" />  
         <!-- Set to 0, 1, 2, 3, or 4, which corresponds   
         to TraceLevel.Off, TraceLevel.Error, TraceLevel.Warning  
         TraceLevel.Info, and TraceLevel.Verbose. -->  
       </switches>  
     </system.diagnostics>  
   </configuration>  
   ```  
  
   > [!NOTE]
   >  <span data-ttu-id="663e7-109">場合、**トレース**コンパイラ ディレクティブに設定されていない**true**トレース出力は生成されません。</span><span class="sxs-lookup"><span data-stu-id="663e7-109">If the **TRACE** compiler directive is not set to **true** then no trace output will be generated.</span></span> <span data-ttu-id="663e7-110">**TraceSwitch**値は、呼び出し元のクラスで設定することもできますが、便宜上、web.config ファイルで設定しています。</span><span class="sxs-lookup"><span data-stu-id="663e7-110">The **TraceSwitch** value can also be set in the calling class, but is set here in the web.config file for convenience.</span></span> <span data-ttu-id="663e7-111">設定、 **TraceSwitch**開発のための適切なレベルを値し、開発が削減またはトレース出力を抑制する完了した後、値を変更します。</span><span class="sxs-lookup"><span data-stu-id="663e7-111">Set the **TraceSwitch** value to the appropriate level for development purposes and change the value after development is complete to reduce or inhibit trace output.</span></span>  
  
2. <span data-ttu-id="663e7-112">インスタンスを作成、 **TraceSwitch**と**TextWriterTraceListener**クラスとを使用して、 **try… catch** Web サービス [WebMethod] 呼び出しでにエラーをトラップして書き込むブロックトレース出力ファイル。</span><span class="sxs-lookup"><span data-stu-id="663e7-112">Create an instance of the **TraceSwitch** and **TextWriterTraceListener** classes and use a **try…catch** block in the Web service [WebMethod] call to trap and write errors to a trace output file.</span></span> <span data-ttu-id="663e7-113">たとえば、次のコードは、整数型の変数 s2 をオブジェクト変数 o2 の NULL インスタンスに設定しようとしたときに生成されるエラーをトラップします。</span><span class="sxs-lookup"><span data-stu-id="663e7-113">For example, the following code traps an error that is generated when attempting to set the integer variable s2 to a null instance of the object variable o2:</span></span>  
  
   ```  
   using System;  
   using System.Web;  
   using System.Web.Services;  
   using System.Web.Services.Protocols;  
   using System.Diagnostics;  
  
   [WebService(Namespace = "http://tempuri.org/")]  
   [WebServiceBinding(ConformsTo = WsiProfiles.BasicProfile1_1)]  
   public class Service : System.Web.Services.WebService  
   {  
       TraceSwitch WebSvcTraceSwitch = new TraceSwitch("WebSvcTraceSwitch", "Web Service Trace");  
       TextWriterTraceListener TestTracer = new TextWriterTraceListener("C:\\traceout.txt");  
       // Note that by default the local ASPNET account(IIS 5.x) or the   
       // local NETWORK SERVICE account(IIS 6.0) needs write access to  
       // this directory so that the instance of the   
       // TextWriterTraceListener can write to the trace output file.  
   );  
  
       public Service () {  
       }  
  
       [WebMethod]  
       public string HelloWorld()   
       {  
       string h2 = "Hello World";  
       //object o2 = 1;  
       object o2 = null;  
           try  
           {  
               int s2 = (int)o2; //Error if o2 set to null   
               return h2;  
           }  
           catch(Exception e)  
           {  
               Trace.Listeners.Add(TestTracer);  
               Trace.WriteLineIf(WebSvcTraceSwitch.Level = TraceLevel.Warning, "Exception caught: " + e.Message);  
               //Writes to the trace file if specified TraceLevel switch value (in web.config) >= 2  
               TestTracer.Dispose();  
               return "An error occurred in the Web service, please contact the web server administrator.";  
           }  
       }  
   }  
   ```  
  
   > [!NOTE]
   >  <span data-ttu-id="663e7-114">このコードは、新規に作成するときに生成される HelloWorld Web サービスの既定の修正バージョン**ASP.Net Web サービス**microsoft プロジェクト[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="663e7-114">This code is a modified version of the default HelloWorld Web service that is generated when you create a new **ASP.Net Web Service** project in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="663e7-115">Windows Vista では、ルート フォルダーにトレース出力ファイルを書き込むためには、管理者特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="663e7-115">For Windows Vista, Administrator privileges may be required to write the trace output file to the root folder.</span></span>  
  
3. <span data-ttu-id="663e7-116">Web サービス プロジェクトをリビルドします。</span><span class="sxs-lookup"><span data-stu-id="663e7-116">Rebuild the Web service project.</span></span> <span data-ttu-id="663e7-117">ここでエラーが発生した場合、**お試しください**ステートメントで、例外が処理、**キャッチ**ステートメントと、エラーがトレース出力ファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="663e7-117">Now, if an error occurs in the **Try** statement the exception is handled in the **Catch** statement and an error is written to the trace output file.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="663e7-118">既知の問題</span><span class="sxs-lookup"><span data-stu-id="663e7-118">Known Issues</span></span>  
  
#### <a name="a-web-service-returns-an-http-404-file-not-found-error"></a><span data-ttu-id="663e7-119">Web サービスから HTTP 404 (ファイルが見つかりません) エラーが返される</span><span class="sxs-lookup"><span data-stu-id="663e7-119">A Web service returns an HTTP 404 (File Not Found) error</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="663e7-120">問題</span><span class="sxs-lookup"><span data-stu-id="663e7-120">Problem</span></span>  
 <span data-ttu-id="663e7-121">Web サービスを呼び出そうとすると、HTTP 404 (ファイルが見つかりません) エラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="663e7-121">Attempts to call a Web service return an HTTP 404 (File Not Found) error.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="663e7-122">原因</span><span class="sxs-lookup"><span data-stu-id="663e7-122">Cause</span></span>  
 <span data-ttu-id="663e7-123">このエラーは、Web サービスをホストする IIS サーバーに必要な ASP.NET がインストールされていない場合や有効になっていない場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="663e7-123">This error can occur if ASP.NET is not installed and/or enabled on the IIS server that hosts the Web service.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="663e7-124">解決策</span><span class="sxs-lookup"><span data-stu-id="663e7-124">Resolution</span></span>  
 <span data-ttu-id="663e7-125">ASP.NET がインストールされ、有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="663e7-125">Ensure that ASP.NET is installed and enabled.</span></span> <span data-ttu-id="663e7-126">インストール、[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]がインストールされているやを実行しない場合は、 **aspnet_regiis.exe**プログラムの配置では、%WinDir%\Microsoft.NET\Framework\\*vXXX.XXX*\ IIS サーバーのフォルダー。</span><span class="sxs-lookup"><span data-stu-id="663e7-126">Install the [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] if it is not installed and/or run the **aspnet_regiis.exe** program located in the %WinDir%\Microsoft.NET\Framework\\*vXXX.XXX*\ folder of the IIS server.</span></span>  
  
#### <a name="a-systemiofilenotfoundexception-error-occurs-when-a-web-service-is-called"></a><span data-ttu-id="663e7-127">Web サービスの呼び出し時に "System.IO.FileNotFoundException" エラーが発生する</span><span class="sxs-lookup"><span data-stu-id="663e7-127">A "System.IO.FileNotFoundException" error occurs when a Web service is called</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="663e7-128">問題</span><span class="sxs-lookup"><span data-stu-id="663e7-128">Problem</span></span>  
 <span data-ttu-id="663e7-129">Microsoft ASP.NET Web アプリケーションで Web サービスを呼び出すときに、次のエラーが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="663e7-129">When you call a Web service in a Microsoft ASP.NET Web application, you may receive the following error:</span></span>  
  
 <span data-ttu-id="663e7-130">**System.IO.FileNotFoundException**</span><span class="sxs-lookup"><span data-stu-id="663e7-130">**System.IO.FileNotFoundException**</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="663e7-131">原因</span><span class="sxs-lookup"><span data-stu-id="663e7-131">Cause</span></span>  
 <span data-ttu-id="663e7-132">このエラーは、次のいずれかの条件に該当する場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="663e7-132">This error can occur if either of the following conditions is true:</span></span>  
  
-   <span data-ttu-id="663e7-133">ワーカー プロセスにプロセスの Temp ディレクトリの読み取りアクセス許可がなく、ワーカー プロセスにプロセスの Temp ディレクトリへの書き込みアクセス許可がない。</span><span class="sxs-lookup"><span data-stu-id="663e7-133">The worker process does not have permissions to read to the process Temp directory, and the worker process does not have permissions to write to the process Temp directory.</span></span>  
  
-   <span data-ttu-id="663e7-134">XmlSerializer で生成されたコードにコンパイル エラーがある。</span><span class="sxs-lookup"><span data-stu-id="663e7-134">There are compilation errors in the code that XmlSerializer generated.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="663e7-135">解決策</span><span class="sxs-lookup"><span data-stu-id="663e7-135">Resolution</span></span>  
 <span data-ttu-id="663e7-136">このエラーは、マイクロソフト サポート技術情報の資料 823196、記載されて[PRB:クライアント アプリケーションが Web サービスを呼び出すと"System.IO.FileNotFoundException"エラーが発生する](http://go.microsoft.com/fwlink/?LinkID=84694)"。</span><span class="sxs-lookup"><span data-stu-id="663e7-136">This error is documented in Microsoft Knowledge Base article 823196, [PRB: You Receive a "System.IO.FileNotFoundException" Error When the Client Application Calls a Web Service](http://go.microsoft.com/fwlink/?LinkID=84694)".</span></span> <span data-ttu-id="663e7-137">このエラーを解決するには、このサポート技術情報の記事の「解決方法」のセクションの手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="663e7-137">Follow the steps in the Resolution section of this Knowledge Base article to resolve this error.</span></span>  
  
#### <a name="date-fields-are-removed-from-documents-processed-by-a-web-service-generated-with-the-biztalk-server-web-services-publishing-wizard"></a><span data-ttu-id="663e7-138">BizTalk Server の Web サービス公開ウィザードで生成した Web サービスでドキュメントを処理すると、日付フィールドが削除される</span><span class="sxs-lookup"><span data-stu-id="663e7-138">Date fields are removed from documents processed by a web service generated with the BizTalk Server Web Services Publishing Wizard</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="663e7-139">問題</span><span class="sxs-lookup"><span data-stu-id="663e7-139">Problem</span></span>  
 <span data-ttu-id="663e7-140">BizTalk Server Web サービス公開ウィザードで、フィールドに含まれるデータが生成された web サービスを持つドキュメントを処理する場合、**データ型**の**xs:date**と**Nillable**プロパティの**True**ドキュメントから削除されます。</span><span class="sxs-lookup"><span data-stu-id="663e7-140">When you process a document with a web service that was generated with the BizTalk Server Web Services Publishing Wizard, any data contained in a field with a **Data Type** of **xs:date** and a **Nillable** property of **True** is removed from the document.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="663e7-141">原因</span><span class="sxs-lookup"><span data-stu-id="663e7-141">Cause</span></span>  
 <span data-ttu-id="663e7-142">この問題は、Microsoft .NET Framework クラス ライブラリの名前空間 System.Xml.Serialization で提供されている XmlSerializer クラスを使用して既知の問題により発生します。</span><span class="sxs-lookup"><span data-stu-id="663e7-142">This problem occurs because of a known issue with the XmlSerializer class that is available with the Microsoft .NET Framework Class Library namespace System.Xml.Serialization.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="663e7-143">解決策</span><span class="sxs-lookup"><span data-stu-id="663e7-143">Resolution</span></span>  
 <span data-ttu-id="663e7-144">この問題を解決するには、Microsoft サポート技術情報の資料 925272 に記載されている .NET Framework 2.0 修正プログラムのインストール"[修正します。XML シリアル化は、.NET Framework 2.0 の XSD スキーマの一部の省略可能な要素を失う可能性があります](http://go.microsoft.com/fwlink/?LinkId=84696)"。</span><span class="sxs-lookup"><span data-stu-id="663e7-144">To resolve this issue, install the .NET Framework 2.0 hotfix documented in Microsoft Knowledge Base article 925272, "[FIX: The XML serialization may lose some optional elements in an XSD schema in the .NET Framework 2.0](http://go.microsoft.com/fwlink/?LinkId=84696)".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="663e7-145">参照</span><span class="sxs-lookup"><span data-stu-id="663e7-145">See Also</span></span>  
 <span data-ttu-id="663e7-146">[IIS のアクセス許可の問題を解決するためのガイドライン](../core/guidelines-for-resolving-iis-permissions-problems.md) </span><span class="sxs-lookup"><span data-stu-id="663e7-146">[Guidelines for Resolving IIS Permissions Problems](../core/guidelines-for-resolving-iis-permissions-problems.md) </span></span>  
 [<span data-ttu-id="663e7-147">Web サービスのアクセス許可の問題を解決するためのガイドライン</span><span class="sxs-lookup"><span data-stu-id="663e7-147">Guidelines for Resolving Web Services Permissions Problems</span></span>](../core/guidelines-for-resolving-web-services-permissions-problems.md)