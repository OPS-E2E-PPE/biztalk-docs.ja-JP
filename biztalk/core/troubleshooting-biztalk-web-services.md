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
# <a name="troubleshooting-biztalk-web-services"></a>BizTalk Web サービスのトラブルシューティング
このセクションでは、Web サービスの一般的な問題を特定し、解決するためのヒントについて説明します。  
  
## <a name="general-troubleshooting"></a>一般的なトラブルシューティング  
  
### <a name="enabling-web-services-publishing-wizard-tracing"></a>Web サービス公開ウィザードのトレースを有効にする  
 コメントを解除して、BizTalk Web サービス公開ウィザードをデバッグするトレースを有効にした、\<追加\>BTSWebSvcWiz.exe.config ファイル内のノード。 Web サービス公開ウィザードからトレース情報の取得の詳細については、[BTSWebSvcWiz.exe.config を変更する方法](../core/how-to-modify-btswebsvcwiz-exe-config.md)を参照してください。  
  
### <a name="enabling-soap-message-tracing"></a>SOAP メッセージ トレースを有効にする  
 SOAP メッセージ トレースを有効にすることにより、SOAP 拡張を使用して Web サービス公開アプリケーションをデバッグできます。 SOAP 拡張機能の詳細については、[方法: SOAP 拡張機能を実装](http://go.microsoft.com/fwlink/?LinkId=62314)を参照してください。  
  
### <a name="using-the-throwdetailederror-switch"></a>ThrowDetailedError スイッチの使用  
 Web クライアントが受け取るジェネリックでエラーが発生する場合**SoapException**します。  
  
 公開済みの Web サービスをデバッグするには、web.config ファイルにスイッチを追加して、公開済みの Web サービスから返される例外の詳細レベルを制御します。 スイッチが**ThrowDetailedError**に設定すると、 **True**サーバー プロキシは、公開された Web サービスをデバッグできるように、Web クライアントに内部例外情報を返します。  
  
 次の XML コードは、 **ThrowDetailedError**スイッチで web.config ファイルに表示される、 \<appSettings\>ノード。  
  
```  
<appSettings>  
  <add key="ThrowDetailedError" value="False" />  
<appSettings/>  
```  
  
> [!WARNING]
>  内部例外には、機密情報が含まれていることがあります。 デバッグするには、後に設定する必要があります、 **ThrowDetailedError**に切り替える**False**します。  
  
### <a name="using-net-framework-tracing-to-capture-and-log-errors-in-the-web-service"></a>.NET Framework のトレース機能を使用して Web サービスのエラーをキャプチャしログに記録する  
 .NET Framework **System.Diagnostics.Trace**をキャプチャしてテキスト ファイルにエラーを書き込むクラスを使用できます。  
  
##### <a name="to-use-the-systemdiagnosticstrace-class-to-capture-and-write-errors-to-a-text-file"></a>System.Diagnostics.Trace クラスでエラーをキャプチャしてテキスト ファイルに書き込むには  
  
1. TRACE コンパイラ ディレクティブに設定する Web サービスの web.config ファイルを更新**true**を追加し、 **TraceSwitch**値。  
  
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
   >  TRACE コンパイラ ディレクティブに設定されていない場合**true**トレース出力は生成されません。 **TraceSwitch**値は、呼び出し元のクラスで設定することもできますが、便宜上、web.config ファイルで設定しています。 設定、 **TraceSwitch**開発のための適切なレベルを値し、開発が削減またはトレース出力を抑制する完了した後、値を変更します。  
  
2. インスタンスを作成、 **TraceSwitch**と**TextWriterTraceListener**クラスとを使用して、 **try… catch** Web サービス [WebMethod] 呼び出しでにエラーをトラップして書き込むブロックトレース出力ファイル。 たとえば、次のコードは、整数型の変数 s2 をオブジェクト変数 o2 の NULL インスタンスに設定しようとしたときに生成されるエラーをトラップします。  
  
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
   >  このコードは、新規に作成するときに、既定で生成される HelloWorld Web サービスの修正バージョン**ASP.Net Web サービス**プロジェクト[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。  
   > 
   > [!NOTE]
   >  Windows Vista では、ルート フォルダーにトレース出力ファイルを書き込むためには、管理者特権が必要です。  
  
3. Web サービス プロジェクトをリビルドします。 ここでエラーが発生した場合、**お試しください**ステートメントで、例外が処理、**キャッチ**ステートメントと、エラーがトレース出力ファイルに書き込まれます。  
  
## <a name="general-troubleshooting-questions-and-answers"></a>一般的なトラブルシューティングに関する質問と回答  
 このセクションでは、Web サービスで発生する問題を解決するのに役立つ質問と回答を示します。  
  
### <a name="i-am-receiving-errors-when-consuming-a-web-service-how-can-i-avoid-them"></a>Web サービスを使用しているときにエラーが発生しますが、どうすればエラーを避けることができますか。  
 Web サービスを使用するとき、多数の事項を考慮する必要があります。その主なものは次のとおりです。  
  
- パラメーター名で 2 つのアンダースコア文字を使用しない。  
  
- 使用、**任意**要素、または**anyAttribute**属性は Web メソッドではサポートされていません。  
  
- XLANG/s キーワードを Web サービス名または Web メソッド名として使用しない。  
  
- XLANG/s でサポートされていない Web メソッド パラメーター型を使用しない。  
  
- C# のキーワードである要素名または C# の識別子としては無効とされる要素名をスキーマ内で使用しない。  
  
- Web サービス記述言語 (WSDL) ファイルで複数のサービスまたはポート タイプ定義を使用しない。  
  
- Web メソッドのパラメーターは XML シリアル化が可能である必要がある。  
  
- 使用する Web サービスに複数ルートのスキーマが含まれている場合は、その Web サービスを参照しないようにする。  
  
- NULL 許容パラメーターなどのジェネリック パラメーターを想定した Web メソッドを持つ Web サービスは参照しない。  
  
- WSDL のインポート要素はサポートされない。  
  
  これらの詳細については、関連する考慮事項を参照してくださいと[に関する考慮事項と Web サービスの利用](../core/considerations-when-consuming-web-services.md)します。  
  
### <a name="why-am-i-getting-errors-publishing-my-schema-that-uses-the-include-element"></a>なぜエラーを使用したスキーマを公開、\<含める\>要素でしょうか。  
 循環参照が含まれる場合、スキーマをパブリッシュできません (インクルードされるスキーマが、**含める**をインクルードするスキーマの要素) または未解決**schemaLocation**属性。  
  
 制限の詳細については、**含める**要素を参照してください[Include 要素のバインディング サポート](http://go.microsoft.com/fwlink/?LinkId=62312)します。 Web サービス公開ウィザードでは、.NET Framework 2.0 の XSD.exe と同じ制限詳細については、[Import 要素のバインディング サポート](http://go.microsoft.com/fwlink/?LinkId=119606)を参照してください。  
  
### <a name="why-do-i-receive-errors-when-publishing-my-envelope-schema"></a>エンベロープ スキーマを公開するときにエラーになるのはなぜですか。  
 Web サービスとして公開するエンベロープ スキーマがある場合、生成された Web プロジェクトを手動で変更する必要があります。  
  
##### <a name="to-modify-the-generated-web-project-for-envelope-schemas"></a>エンベロープ スキーマの生成された Web プロジェクトを変更するには  
  
1.  開く、  *\<myWebService\>*。 ある asmx.cs ファイル。  
  
2.  ファイルで `bodyTypeAssemblyQualifiedName = <dll.name.version>``bodyTypeAssemblyQualifiedName = null` を  に変更します。  
  
> [!NOTE]
>  以前の .dll ファイルが ASP.NET のワーカー プロセス内にまだ存在する場合は、インターネット インフォメーション サービス (IIS) をリセットする必要がある場合があります。  
  
### <a name="clients-of-published-web-services-may-not-receive-server-script-time-out-errors"></a>公開済み Web サービスのクライアントがサーバー スクリプトのタイムアウト エラーを受信しない  
 .NET Framework を使用する Web クライアントが、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Web サービス公開ウィザードを使用して生成された Web サービスを呼び出している場合、既定では先にクライアント要求タイムアウトが発生するため、クライアントがサーバー スクリプト タイムアウト エラーを受信できないことがあります。 この問題を解決するには、次のいずれかの操作を実行します。  
  
-   値を増やすことで、サーバー スクリプト タイムアウトよりも大きい値にクライアント要求タイムアウトを増やす、 **HttpWebRequest.Timeout**クライアントのプロパティ。  
  
-   値を減らすことで、クライアント要求タイムアウトよりも小さい値に、サーバー スクリプト タイムアウトを減らす、 **HttpServerUtility.ScriptTimeout**サーバーのプロパティ。  
  
## <a name="common-errors"></a>一般的なエラー  
  
### <a name="a-web-service-returns-an-http-404-file-not-found-error"></a>Web サービスから HTTP 404 (ファイルが見つかりません) エラーが返される  
  
#### <a name="problem"></a>問題  
 Web サービスを呼び出そうとすると、HTTP 404 (ファイルが見つかりません) エラーが返されます。  
  
#### <a name="cause"></a>原因  
 このエラーは、Web サービスをホストする IIS サーバーに必要な ASP.NET がインストールされていない場合や有効になっていない場合に発生する可能性があります。  
  
#### <a name="resolution"></a>解決策  
 ASP.NET がインストールされ、有効になっていることを確認します。 .NET Framework がインストールされていない場合はインストールし、IIS サーバーの %WinDir%\Microsoft.NET\Framework\vXXX.XXX\ フォルダー内にある aspnet_regiis.exe プログラムを実行します。  
  
### <a name="date-fields-are-removed-from-documents-processed-by-a-web-service-generated-with-the-biztalk-server-web-services-publishing-wizard"></a>BizTalk Server の Web サービス公開ウィザードで生成した Web サービスでドキュメントを処理すると、日付フィールドが削除される  
  
#### <a name="problem"></a>問題  
 BizTalk Server Web サービス公開ウィザードで、フィールドに含まれるデータが生成された web サービスを持つドキュメントを処理する場合、**データ型**の**xs:date**はから削除しますドキュメントです。  
  
#### <a name="cause"></a>原因  
 この問題は、公開されたオーケストレーションにある 1 つまたは複数のフィールドを持つスキーマが含まれている場合に発生することができます、**データ型**の**xs:date**と**Nillable** のプロパティ**True**します。  
  
#### <a name="workaround"></a>回避策  
 回避策をこの問題を持つ公開されているスキーマであるフィールドを見つけ、**データ型**の**xs:date**ことを確認します、 **Nillable**これらのフィールドのプロパティに設定**False**します。  
  
### <a name="a-systemiofilenotfoundexception-error-occurs-when-a-web-service-is-called"></a>Web サービスの呼び出し時に "System.IO.FileNotFoundException" エラーが発生する  
  
#### <a name="problem"></a>問題  
 Microsoft ASP.NET Web アプリケーションで Web サービスを呼び出すときに、次のエラーが発生することがあります。  
  
 System.IO.FileNotFoundException  
  
#### <a name="cause"></a>原因  
 このエラーは、次のいずれかの条件に該当する場合に発生する可能性があります。  
  
-   ワーカー プロセスにプロセスの Temp ディレクトリの読み取りアクセス許可がなく、ワーカー プロセスにプロセスの Temp ディレクトリへの書き込みアクセス許可がない。  
  
-   XmlSerializer で生成されたコードにコンパイル エラーがある。  
  
#### <a name="resolution"></a>解決策  
 このエラーは、マイクロソフト サポート技術情報の記事に記載されている[823196](http://support.microsoft.com/kb/823196)します。 このエラーを解決するには、このサポート技術情報の記事の「解決方法」のセクションの手順に従ってください。