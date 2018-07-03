---
title: BizTalk Web サービスのトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cdc86de8-e41e-4878-a66e-e242bcf3b705
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c2e14955b05397e69c326ce7302108cb6c0eb00
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990667"
---
# <a name="troubleshooting-biztalk-web-services"></a><span data-ttu-id="091e1-102">BizTalk Web サービスのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="091e1-102">Troubleshooting BizTalk Web Services</span></span>
<span data-ttu-id="091e1-103">このセクションでは、Web サービスの一般的な問題を特定し、解決するためのヒントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="091e1-103">This section offers advice on how to identify and resolve common Web service issues.</span></span>  
  
## <a name="general-troubleshooting"></a><span data-ttu-id="091e1-104">一般的なトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="091e1-104">General Troubleshooting</span></span>  
  
### <a name="enabling-web-services-publishing-wizard-tracing"></a><span data-ttu-id="091e1-105">Web サービス公開ウィザードのトレースを有効にする</span><span class="sxs-lookup"><span data-stu-id="091e1-105">Enabling Web Services Publishing Wizard tracing</span></span>  
 <span data-ttu-id="091e1-106">コメントを解除して、BizTalk Web サービス公開ウィザードをデバッグするトレースを有効にした、\<追加\>BTSWebSvcWiz.exe.config ファイル内のノード。</span><span class="sxs-lookup"><span data-stu-id="091e1-106">You can enable tracing to debug the BizTalk Web Services Publishing Wizard by uncommenting the \<add\> node in the BTSWebSvcWiz.exe.config file.</span></span> <span data-ttu-id="091e1-107">Web サービス公開ウィザードからトレース情報の取得の詳細については、次を参照してください。 [BTSWebSvcWiz.exe.config を変更する方法](../core/how-to-modify-btswebsvcwiz-exe-config.md)します。</span><span class="sxs-lookup"><span data-stu-id="091e1-107">For more information about obtaining trace information from the Web Services Publishing Wizard, see [How to Modify BTSWebSvcWiz.exe.config](../core/how-to-modify-btswebsvcwiz-exe-config.md).</span></span>  
  
### <a name="enabling-soap-message-tracing"></a><span data-ttu-id="091e1-108">SOAP メッセージ トレースを有効にする</span><span class="sxs-lookup"><span data-stu-id="091e1-108">Enabling SOAP message tracing</span></span>  
 <span data-ttu-id="091e1-109">SOAP メッセージ トレースを有効にすることにより、SOAP 拡張を使用して Web サービス公開アプリケーションをデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="091e1-109">You can enable SOAP message tracing to help you debug the Web services publishing application by using a SOAP extension.</span></span> <span data-ttu-id="091e1-110">SOAP 拡張機能の詳細については、次を参照してください。[方法: SOAP 拡張機能を実装](http://go.microsoft.com/fwlink/?LinkId=62314)します。</span><span class="sxs-lookup"><span data-stu-id="091e1-110">For more information about SOAP extensions, see [How to: Implement a SOAP Extension](http://go.microsoft.com/fwlink/?LinkId=62314).</span></span>  
  
### <a name="using-the-throwdetailederror-switch"></a><span data-ttu-id="091e1-111">ThrowDetailedError スイッチの使用</span><span class="sxs-lookup"><span data-stu-id="091e1-111">Using the ThrowDetailedError switch</span></span>  
 <span data-ttu-id="091e1-112">Web クライアントが受け取るジェネリックでエラーが発生する場合**SoapException**します。</span><span class="sxs-lookup"><span data-stu-id="091e1-112">If an error occurs, the Web client receives a generic **SoapException**.</span></span>  
  
 <span data-ttu-id="091e1-113">公開済みの Web サービスをデバッグするには、web.config ファイルにスイッチを追加して、公開済みの Web サービスから返される例外の詳細レベルを制御します。</span><span class="sxs-lookup"><span data-stu-id="091e1-113">To debug your published Web service, you can add a switch to the web.config file to control the level of the exception details returned from the published Web service.</span></span> <span data-ttu-id="091e1-114">スイッチが**ThrowDetailedError**に設定すると、 **True**サーバー プロキシは、公開された Web サービスをデバッグできるように、Web クライアントに内部例外情報を返します。</span><span class="sxs-lookup"><span data-stu-id="091e1-114">The switch is **ThrowDetailedError**, and when it is set to **True** the server proxy returns inner exception information to the Web client, enabling you to debug the published Web service.</span></span>  
  
 <span data-ttu-id="091e1-115">次の XML コードは、 **ThrowDetailedError**スイッチで web.config ファイルに表示される、 \<appSettings\>ノード。</span><span class="sxs-lookup"><span data-stu-id="091e1-115">The following XML code shows the **ThrowDetailedError** switch that appears in the web.config file under the \<appSettings\> node:</span></span>  
  
```  
<appSettings>  
  <add key="ThrowDetailedError" value="False" />  
<appSettings/>  
```  
  
> [!WARNING]
>  <span data-ttu-id="091e1-116">内部例外には、機密情報が含まれていることがあります。</span><span class="sxs-lookup"><span data-stu-id="091e1-116">The inner exception may contain sensitive information.</span></span> <span data-ttu-id="091e1-117">デバッグするには、後に設定する必要があります、 **ThrowDetailedError**に切り替える**False**します。</span><span class="sxs-lookup"><span data-stu-id="091e1-117">After debugging, you should set the **ThrowDetailedError** switch to **False**.</span></span>  
  
### <a name="using-net-framework-tracing-to-capture-and-log-errors-in-the-web-service"></a><span data-ttu-id="091e1-118">.NET Framework のトレース機能を使用して Web サービスのエラーをキャプチャしログに記録する</span><span class="sxs-lookup"><span data-stu-id="091e1-118">Using .NET Framework tracing to capture and log errors in the Web service</span></span>  
 <span data-ttu-id="091e1-119">.NET Framework **System.Diagnostics.Trace**をキャプチャしてテキスト ファイルにエラーを書き込むクラスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="091e1-119">The .NET Framework **System.Diagnostics.Trace** class can be used to capture and write errors to a text file.</span></span>  
  
##### <a name="to-use-the-systemdiagnosticstrace-class-to-capture-and-write-errors-to-a-text-file"></a><span data-ttu-id="091e1-120">System.Diagnostics.Trace クラスでエラーをキャプチャしてテキスト ファイルに書き込むには</span><span class="sxs-lookup"><span data-stu-id="091e1-120">To use the System.Diagnostics.Trace class to capture and write errors to a text file</span></span>  
  
1. <span data-ttu-id="091e1-121">TRACE コンパイラ ディレクティブに設定する Web サービスの web.config ファイルを更新**true**を追加し、 **TraceSwitch**値。</span><span class="sxs-lookup"><span data-stu-id="091e1-121">Update the web.config file for the Web service to set the TRACE compiler directive to **true** and add a **TraceSwitch** value:</span></span>  
  
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
   >  <span data-ttu-id="091e1-122">TRACE コンパイラ ディレクティブに設定されていない場合**true**トレース出力は生成されません。</span><span class="sxs-lookup"><span data-stu-id="091e1-122">If the TRACE compiler directive is not set to **true** then no trace output will be generated.</span></span> <span data-ttu-id="091e1-123">**TraceSwitch**値は、呼び出し元のクラスで設定することもできますが、便宜上、web.config ファイルで設定しています。</span><span class="sxs-lookup"><span data-stu-id="091e1-123">The **TraceSwitch** value can also be set in the calling class but is set here in the web.config file for convenience.</span></span> <span data-ttu-id="091e1-124">設定、 **TraceSwitch**開発のための適切なレベルを値し、開発が削減またはトレース出力を抑制する完了した後、値を変更します。</span><span class="sxs-lookup"><span data-stu-id="091e1-124">Set the **TraceSwitch** value to the appropriate level for development purposes and change the value after development is complete to reduce or inhibit trace output.</span></span>  
  
2. <span data-ttu-id="091e1-125">インスタンスを作成、 **TraceSwitch**と**TextWriterTraceListener**クラスとを使用して、 **try… catch** Web サービス [WebMethod] 呼び出しでにエラーをトラップして書き込むブロックトレース出力ファイル。</span><span class="sxs-lookup"><span data-stu-id="091e1-125">Create an instance of the **TraceSwitch** and **TextWriterTraceListener** classes and use a **try…catch** block in the Web service [WebMethod] call to trap and write errors to a trace output file.</span></span> <span data-ttu-id="091e1-126">たとえば、次のコードは、整数型の変数 s2 をオブジェクト変数 o2 の NULL インスタンスに設定しようとしたときに生成されるエラーをトラップします。</span><span class="sxs-lookup"><span data-stu-id="091e1-126">For example, the following code traps an error that is generated when attempting to set the integer variable s2 to a null instance of the object variable o2:</span></span>  
  
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
               Trace.WriteLineIf(WebSvcTraceSwitch.Level = TraceLevel.Warning,"Exception caught: " + e.Message);  
               //Writes to the trace file if specified TraceLevel switch value (in web.config) >= 2  
               TestTracer.Dispose();  
               return "An error occurred in the Web service, please contact the web server administrator.";  
           }  
       }  
   }  
   ```  
  
   > [!NOTE]
   >  <span data-ttu-id="091e1-127">このコードは、新規に作成するときに、既定で生成される HelloWorld Web サービスの修正バージョン**ASP.Net Web サービス**プロジェクト[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="091e1-127">This code is a modified version of the HelloWorld Web service that is generated by default when you create a new **ASP.Net Web Service** project in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="091e1-128">Windows Vista では、ルート フォルダーにトレース出力ファイルを書き込むためには、管理者特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="091e1-128">For Windows Vista, Administrator privileges may be required to write the trace output file to the root folder.</span></span>  
  
3. <span data-ttu-id="091e1-129">Web サービス プロジェクトをリビルドします。</span><span class="sxs-lookup"><span data-stu-id="091e1-129">Rebuild the Web service project.</span></span> <span data-ttu-id="091e1-130">ここでエラーが発生した場合、**お試しください**ステートメントで、例外が処理、**キャッチ**ステートメントと、エラーがトレース出力ファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="091e1-130">Now, if an error occurs in the **Try** statement the exception is handled in the **Catch** statement and an error is written to the trace output file.</span></span>  
  
## <a name="general-troubleshooting-questions-and-answers"></a><span data-ttu-id="091e1-131">一般的なトラブルシューティングに関する質問と回答</span><span class="sxs-lookup"><span data-stu-id="091e1-131">General Troubleshooting Questions and Answers</span></span>  
 <span data-ttu-id="091e1-132">このセクションでは、Web サービスで発生する問題を解決するのに役立つ質問と回答を示します。</span><span class="sxs-lookup"><span data-stu-id="091e1-132">This section contains a set of questions and answers designed to help you resolve issues with Web services.</span></span>  
  
### <a name="i-am-receiving-errors-when-consuming-a-web-service-how-can-i-avoid-them"></a><span data-ttu-id="091e1-133">Web サービスを使用しているときにエラーが発生しますが、どうすればエラーを避けることができますか。</span><span class="sxs-lookup"><span data-stu-id="091e1-133">I am receiving errors when consuming a Web service; how can I avoid them?</span></span>  
 <span data-ttu-id="091e1-134">Web サービスを使用するとき、多数の事項を考慮する必要があります。その主なものは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="091e1-134">There are many details to consider when consuming a Web service, including the following:</span></span>  
  
- <span data-ttu-id="091e1-135">パラメーター名で 2 つのアンダースコア文字を使用しない。</span><span class="sxs-lookup"><span data-stu-id="091e1-135">Avoid using two underscore characters in a parameter name.</span></span>  
  
- <span data-ttu-id="091e1-136">使用、**任意**要素、または**anyAttribute**属性は Web メソッドではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="091e1-136">Use of the **any** element or the **anyAttribute** attribute is not supported in Web methods.</span></span>  
  
- <span data-ttu-id="091e1-137">XLANG/s キーワードを Web サービス名または Web メソッド名として使用しない。</span><span class="sxs-lookup"><span data-stu-id="091e1-137">Avoid using XLANG/s keywords as a Web service name or Web method name.</span></span>  
  
- <span data-ttu-id="091e1-138">XLANG/s でサポートされていない Web メソッド パラメーター型を使用しない。</span><span class="sxs-lookup"><span data-stu-id="091e1-138">Avoid using Web method parameter types that are not supported by XLANG/s.</span></span>  
  
- <span data-ttu-id="091e1-139">C# のキーワードである要素名または C# の識別子としては無効とされる要素名をスキーマ内で使用しない。</span><span class="sxs-lookup"><span data-stu-id="091e1-139">Do not use element names that are C# keywords or will be invalid as a C# identifier in your schemas.</span></span>  
  
- <span data-ttu-id="091e1-140">Web サービス記述言語 (WSDL) ファイルで複数のサービスまたはポート タイプ定義を使用しない。</span><span class="sxs-lookup"><span data-stu-id="091e1-140">Avoid Web Services Description Language (WSDL) files with multiple service or port type definitions.</span></span>  
  
- <span data-ttu-id="091e1-141">Web メソッドのパラメーターは XML シリアル化が可能である必要がある。</span><span class="sxs-lookup"><span data-stu-id="091e1-141">Web method parameters must be Xml Serializable.</span></span>  
  
- <span data-ttu-id="091e1-142">使用する Web サービスに複数ルートのスキーマが含まれている場合は、その Web サービスを参照しないようにする。</span><span class="sxs-lookup"><span data-stu-id="091e1-142">Avoid references to consumed Web services that contain multi-rooted schemas.</span></span>  
  
- <span data-ttu-id="091e1-143">NULL 許容パラメーターなどのジェネリック パラメーターを想定した Web メソッドを持つ Web サービスは参照しない。</span><span class="sxs-lookup"><span data-stu-id="091e1-143">Avoid referencing Web services with Web methods expecting generic-based parameters such as nullable parameters.</span></span>  
  
- <span data-ttu-id="091e1-144">WSDL のインポート要素はサポートされない。</span><span class="sxs-lookup"><span data-stu-id="091e1-144">The WSDL import element is not supported.</span></span>  
  
  <span data-ttu-id="091e1-145">これらの詳細については、関連する考慮事項を参照してくださいと[に関する考慮事項と Web サービスの利用](../core/considerations-when-consuming-web-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="091e1-145">For more information about these and related considerations, see [Considerations When Consuming Web Services](../core/considerations-when-consuming-web-services.md).</span></span>  
  
### <a name="why-am-i-getting-errors-publishing-my-schema-that-uses-the-include-element"></a><span data-ttu-id="091e1-146">なぜエラーを使用したスキーマを公開、\<含める\>要素でしょうか。</span><span class="sxs-lookup"><span data-stu-id="091e1-146">Why am I getting errors publishing my schema that uses the \<include\> element?</span></span>  
 <span data-ttu-id="091e1-147">循環参照が含まれる場合、スキーマをパブリッシュできません (インクルードされるスキーマが、**含める**をインクルードするスキーマの要素) または未解決**schemaLocation**属性。</span><span class="sxs-lookup"><span data-stu-id="091e1-147">Schemas cannot be published if they include circular references (the included schema has an **include** element to the including schema) or have an unresolved **schemaLocation** attribute.</span></span>  
  
 <span data-ttu-id="091e1-148">制限の詳細については、**含める**要素を参照してください[Include 要素のバインディング サポート](http://go.microsoft.com/fwlink/?LinkId=62312)します。</span><span class="sxs-lookup"><span data-stu-id="091e1-148">For more information about the limitation of the **include** element, see [Include Element Binding Support](http://go.microsoft.com/fwlink/?LinkId=62312).</span></span> <span data-ttu-id="091e1-149">Web サービス公開ウィザードでは、.NET Framework 2.0 の XSD.exe と同じ制限詳細については、次を参照してください。 [Import 要素のバインディング サポート](http://go.microsoft.com/fwlink/?LinkId=119606)します。</span><span class="sxs-lookup"><span data-stu-id="091e1-149">The Web Services Publishing Wizard has the same limitations as XSD.exe in .NET Framework 2.0; for more information, see [Import Element Binding Support](http://go.microsoft.com/fwlink/?LinkId=119606).</span></span>  
  
### <a name="why-do-i-receive-errors-when-publishing-my-envelope-schema"></a><span data-ttu-id="091e1-150">エンベロープ スキーマを公開するときにエラーになるのはなぜですか。</span><span class="sxs-lookup"><span data-stu-id="091e1-150">Why do I receive errors when publishing my envelope schema?</span></span>  
 <span data-ttu-id="091e1-151">Web サービスとして公開するエンベロープ スキーマがある場合、生成された Web プロジェクトを手動で変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="091e1-151">If you have an envelope schema that you are publishing as a Web service, you need to manually modify the generated Web project.</span></span>  
  
##### <a name="to-modify-the-generated-web-project-for-envelope-schemas"></a><span data-ttu-id="091e1-152">エンベロープ スキーマの生成された Web プロジェクトを変更するには</span><span class="sxs-lookup"><span data-stu-id="091e1-152">To modify the generated Web project for envelope schemas</span></span>  
  
1.  <span data-ttu-id="091e1-153">開く、  *\<myWebService\>*。 ある asmx.cs ファイル。</span><span class="sxs-lookup"><span data-stu-id="091e1-153">Open the *\<myWebService\>*.asmx.cs file.</span></span>  
  
2.  <span data-ttu-id="091e1-154">ファイルで `bodyTypeAssemblyQualifiedName = <dll.name.version>``bodyTypeAssemblyQualifiedName = null` を  に変更します。</span><span class="sxs-lookup"><span data-stu-id="091e1-154">Edit the file and change `bodyTypeAssemblyQualifiedName = <dll.name.version>` to `bodyTypeAssemblyQualifiedName = null`</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="091e1-155">以前の .dll ファイルが ASP.NET のワーカー プロセス内にまだ存在する場合は、インターネット インフォメーション サービス (IIS) をリセットする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="091e1-155">You may need to reset Internet Information Services (IIS) if the previous .dll file is still in the ASP.NET worker process.</span></span>  
  
### <a name="clients-of-published-web-services-may-not-receive-server-script-time-out-errors"></a><span data-ttu-id="091e1-156">公開済み Web サービスのクライアントがサーバー スクリプトのタイムアウト エラーを受信しない</span><span class="sxs-lookup"><span data-stu-id="091e1-156">Clients of published Web services may not receive server script time-out errors</span></span>  
 <span data-ttu-id="091e1-157">.NET Framework を使用する Web クライアントが、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Web サービス公開ウィザードを使用して生成された Web サービスを呼び出している場合、既定では先にクライアント要求タイムアウトが発生するため、クライアントがサーバー スクリプト タイムアウト エラーを受信できないことがあります。</span><span class="sxs-lookup"><span data-stu-id="091e1-157">If Web clients that use .NET Framework are calling a Web service generated with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Web Services Publishing Wizard, it is possible that the client cannot receive server script time-out errors because the client request time-out occurs first by default.</span></span> <span data-ttu-id="091e1-158">この問題を解決するには、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="091e1-158">To resolve this problem you can do one of the following:</span></span>  
  
-   <span data-ttu-id="091e1-159">値を増やすことで、サーバー スクリプト タイムアウトよりも大きい値にクライアント要求タイムアウトを増やす、 **HttpWebRequest.Timeout**クライアントのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="091e1-159">Increase the client request time-out to a value greater than the server script time-out by increasing the value for the **HttpWebRequest.Timeout** property on the client.</span></span>  
  
-   <span data-ttu-id="091e1-160">値を減らすことで、クライアント要求タイムアウトよりも小さい値に、サーバー スクリプト タイムアウトを減らす、 **HttpServerUtility.ScriptTimeout**サーバーのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="091e1-160">Reduce the server script time-out to a value less than the client request time-out by reducing the value for the **HttpServerUtility.ScriptTimeout** property on the server.</span></span>  
  
## <a name="common-errors"></a><span data-ttu-id="091e1-161">一般的なエラー</span><span class="sxs-lookup"><span data-stu-id="091e1-161">Common Errors</span></span>  
  
### <a name="a-web-service-returns-an-http-404-file-not-found-error"></a><span data-ttu-id="091e1-162">Web サービスから HTTP 404 (ファイルが見つかりません) エラーが返される</span><span class="sxs-lookup"><span data-stu-id="091e1-162">A Web service returns an HTTP 404 (File Not Found) error</span></span>  
  
#### <a name="problem"></a><span data-ttu-id="091e1-163">問題</span><span class="sxs-lookup"><span data-stu-id="091e1-163">Problem</span></span>  
 <span data-ttu-id="091e1-164">Web サービスを呼び出そうとすると、HTTP 404 (ファイルが見つかりません) エラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="091e1-164">Attempts to call a Web service return an HTTP 404 (File Not Found) error.</span></span>  
  
#### <a name="cause"></a><span data-ttu-id="091e1-165">原因</span><span class="sxs-lookup"><span data-stu-id="091e1-165">Cause</span></span>  
 <span data-ttu-id="091e1-166">このエラーは、Web サービスをホストする IIS サーバーに必要な ASP.NET がインストールされていない場合や有効になっていない場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="091e1-166">This error can occur if ASP.NET is not installed and/or enabled on the IIS server that hosts the Web service.</span></span>  
  
#### <a name="resolution"></a><span data-ttu-id="091e1-167">解決策</span><span class="sxs-lookup"><span data-stu-id="091e1-167">Resolution</span></span>  
 <span data-ttu-id="091e1-168">ASP.NET がインストールされ、有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="091e1-168">Ensure that ASP.NET is installed and enabled.</span></span> <span data-ttu-id="091e1-169">.NET Framework がインストールされていない場合はインストールし、IIS サーバーの %WinDir%\Microsoft.NET\Framework\vXXX.XXX\ フォルダー内にある aspnet_regiis.exe プログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="091e1-169">Install the .NET Framework if it is not installed and/or run the aspnet_regiis.exe program located in the %WinDir%\Microsoft.NET\Framework\vXXX.XXX\ folder of the IIS server.</span></span>  
  
### <a name="date-fields-are-removed-from-documents-processed-by-a-web-service-generated-with-the-biztalk-server-web-services-publishing-wizard"></a><span data-ttu-id="091e1-170">BizTalk Server の Web サービス公開ウィザードで生成した Web サービスでドキュメントを処理すると、日付フィールドが削除される</span><span class="sxs-lookup"><span data-stu-id="091e1-170">Date fields are removed from documents processed by a web service generated with the BizTalk Server Web Services Publishing Wizard</span></span>  
  
#### <a name="problem"></a><span data-ttu-id="091e1-171">問題</span><span class="sxs-lookup"><span data-stu-id="091e1-171">Problem</span></span>  
 <span data-ttu-id="091e1-172">BizTalk Server Web サービス公開ウィザードで、フィールドに含まれるデータが生成された web サービスを持つドキュメントを処理する場合、**データ型**の**xs:date**はから削除しますドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="091e1-172">When you process a document with a web service that was generated with the BizTalk Server Web Services Publishing Wizard, any data contained in a field with a **Data Type** of **xs:date** is removed from the document.</span></span>  
  
#### <a name="cause"></a><span data-ttu-id="091e1-173">原因</span><span class="sxs-lookup"><span data-stu-id="091e1-173">Cause</span></span>  
 <span data-ttu-id="091e1-174">この問題は、公開されたオーケストレーションにある 1 つまたは複数のフィールドを持つスキーマが含まれている場合に発生することができます、**データ型**の**xs:date**と**Nillable** のプロパティ**True**します。</span><span class="sxs-lookup"><span data-stu-id="091e1-174">This problem can occur if the published orchestration contains a schema with one or more fields that have a **Data Type** of **xs:date** and a **Nillable** property of **True**.</span></span>  
  
#### <a name="workaround"></a><span data-ttu-id="091e1-175">回避策</span><span class="sxs-lookup"><span data-stu-id="091e1-175">Workaround</span></span>  
 <span data-ttu-id="091e1-176">回避策をこの問題を持つ公開されているスキーマであるフィールドを見つけ、**データ型**の**xs:date**ことを確認します、 **Nillable**これらのフィールドのプロパティに設定**False**します。</span><span class="sxs-lookup"><span data-stu-id="091e1-176">To workaround this problem, locate the fields in the published schema that have a **Data Type** of **xs:date** and verify that the **Nillable** property of these fields is set to **False**.</span></span>  
  
### <a name="a-systemiofilenotfoundexception-error-occurs-when-a-web-service-is-called"></a><span data-ttu-id="091e1-177">Web サービスの呼び出し時に "System.IO.FileNotFoundException" エラーが発生する</span><span class="sxs-lookup"><span data-stu-id="091e1-177">A "System.IO.FileNotFoundException" error occurs when a Web service is called</span></span>  
  
#### <a name="problem"></a><span data-ttu-id="091e1-178">問題</span><span class="sxs-lookup"><span data-stu-id="091e1-178">Problem</span></span>  
 <span data-ttu-id="091e1-179">Microsoft ASP.NET Web アプリケーションで Web サービスを呼び出すときに、次のエラーが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="091e1-179">When you call a Web service in a Microsoft ASP.NET Web application, you may receive the following error:</span></span>  
  
 <span data-ttu-id="091e1-180">System.IO.FileNotFoundException</span><span class="sxs-lookup"><span data-stu-id="091e1-180">System.IO.FileNotFoundException</span></span>  
  
#### <a name="cause"></a><span data-ttu-id="091e1-181">原因</span><span class="sxs-lookup"><span data-stu-id="091e1-181">Cause</span></span>  
 <span data-ttu-id="091e1-182">このエラーは、次のいずれかの条件に該当する場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="091e1-182">This error can occur if either of the following conditions is true:</span></span>  
  
-   <span data-ttu-id="091e1-183">ワーカー プロセスにプロセスの Temp ディレクトリの読み取りアクセス許可がなく、ワーカー プロセスにプロセスの Temp ディレクトリへの書き込みアクセス許可がない。</span><span class="sxs-lookup"><span data-stu-id="091e1-183">The worker process does not have permissions to read to the process Temp directory, and the worker process does not have permissions to write to the process Temp directory.</span></span>  
  
-   <span data-ttu-id="091e1-184">XmlSerializer で生成されたコードにコンパイル エラーがある。</span><span class="sxs-lookup"><span data-stu-id="091e1-184">There are compilation errors in the code that XmlSerializer generated.</span></span>  
  
#### <a name="resolution"></a><span data-ttu-id="091e1-185">解決策</span><span class="sxs-lookup"><span data-stu-id="091e1-185">Resolution</span></span>  
 <span data-ttu-id="091e1-186">このエラーは、マイクロソフト サポート技術情報の記事に記載されている[823196](http://support.microsoft.com/kb/823196)します。</span><span class="sxs-lookup"><span data-stu-id="091e1-186">This error is documented in Microsoft Knowledge Base article [823196](http://support.microsoft.com/kb/823196).</span></span> <span data-ttu-id="091e1-187">このエラーを解決するには、このサポート技術情報の記事の「解決方法」のセクションの手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="091e1-187">Follow the steps in the Resolution section of this Knowledge Base article to resolve this error.</span></span>