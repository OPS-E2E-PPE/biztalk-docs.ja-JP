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
# <a name="troubleshooting-web-services"></a>Web サービスのトラブルシューティング
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には Web サービスが広く採用され、SOAP アダプターで使用したり、オーケストレーションを Web サービスとして公開したりできるようになっています。 このトピックでは、Web サービスだけでなく Web サービスの一般的な問題とそれらの問題を解決する方法のトラブルシューティングに利用できるいくつかの手順を説明します。  
  
## <a name="use-net-framework-tracing-to-capture-and-log-errors-in-a-web-service"></a>.NET Framework のトレースを使用してキャプチャし、Web サービスでエラーのログ  
 .NET Framework **System.Diagnostics.Trace**をキャプチャしてテキスト ファイルにエラーを書き込むクラスを使用できます。  
  
#### <a name="to-use-the-systemdiagnosticstrace-class-to-capture-and-write-errors-to-a-text-file"></a>System.Diagnostics.Trace クラスでエラーをキャプチャしてテキスト ファイルに書き込むには  
  
1. 設定する Web サービスの web.config ファイルを更新、**トレース**コンパイラ ディレクティブを**true**を追加し、 **TraceSwitch**値。  
  
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
   >  場合、**トレース**コンパイラ ディレクティブに設定されていない**true**トレース出力は生成されません。 **TraceSwitch**値は、呼び出し元のクラスで設定することもできますが、便宜上、web.config ファイルで設定しています。 設定、 **TraceSwitch**開発のための適切なレベルを値し、開発が削減またはトレース出力を抑制する完了した後、値を変更します。  
  
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
               Trace.WriteLineIf(WebSvcTraceSwitch.Level = TraceLevel.Warning, "Exception caught: " + e.Message);  
               //Writes to the trace file if specified TraceLevel switch value (in web.config) >= 2  
               TestTracer.Dispose();  
               return "An error occurred in the Web service, please contact the web server administrator.";  
           }  
       }  
   }  
   ```  
  
   > [!NOTE]
   >  このコードは、新規に作成するときに生成される HelloWorld Web サービスの既定の修正バージョン**ASP.Net Web サービス**microsoft プロジェクト[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。  
   > 
   > [!NOTE]
   >  Windows Vista では、ルート フォルダーにトレース出力ファイルを書き込むためには、管理者特権が必要です。  
  
3. Web サービス プロジェクトをリビルドします。 ここでエラーが発生した場合、**お試しください**ステートメントで、例外が処理、**キャッチ**ステートメントと、エラーがトレース出力ファイルに書き込まれます。  
  
## <a name="known-issues"></a>既知の問題  
  
#### <a name="a-web-service-returns-an-http-404-file-not-found-error"></a>Web サービスから HTTP 404 (ファイルが見つかりません) エラーが返される  
  
##### <a name="problem"></a>問題  
 Web サービスを呼び出そうとすると、HTTP 404 (ファイルが見つかりません) エラーが返されます。  
  
##### <a name="cause"></a>原因  
 このエラーは、Web サービスをホストする IIS サーバーに必要な ASP.NET がインストールされていない場合や有効になっていない場合に発生する可能性があります。  
  
##### <a name="resolution"></a>解決策  
 ASP.NET がインストールされ、有効になっていることを確認します。 インストール、[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]がインストールされているやを実行しない場合は、 **aspnet_regiis.exe**プログラムの配置では、%WinDir%\Microsoft.NET\Framework\\*vXXX.XXX*\ IIS サーバーのフォルダー。  
  
#### <a name="a-systemiofilenotfoundexception-error-occurs-when-a-web-service-is-called"></a>Web サービスの呼び出し時に "System.IO.FileNotFoundException" エラーが発生する  
  
##### <a name="problem"></a>問題  
 Microsoft ASP.NET Web アプリケーションで Web サービスを呼び出すときに、次のエラーが発生することがあります。  
  
 **System.IO.FileNotFoundException**  
  
##### <a name="cause"></a>原因  
 このエラーは、次のいずれかの条件に該当する場合に発生する可能性があります。  
  
-   ワーカー プロセスにプロセスの Temp ディレクトリの読み取りアクセス許可がなく、ワーカー プロセスにプロセスの Temp ディレクトリへの書き込みアクセス許可がない。  
  
-   XmlSerializer で生成されたコードにコンパイル エラーがある。  
  
##### <a name="resolution"></a>解決策  
 このエラーは、マイクロソフト サポート技術情報の資料 823196、記載されて[PRB:クライアント アプリケーションが Web サービスを呼び出すと"System.IO.FileNotFoundException"エラーが発生する](http://go.microsoft.com/fwlink/?LinkID=84694)"。 このエラーを解決するには、このサポート技術情報の記事の「解決方法」のセクションの手順に従ってください。  
  
#### <a name="date-fields-are-removed-from-documents-processed-by-a-web-service-generated-with-the-biztalk-server-web-services-publishing-wizard"></a>BizTalk Server の Web サービス公開ウィザードで生成した Web サービスでドキュメントを処理すると、日付フィールドが削除される  
  
##### <a name="problem"></a>問題  
 BizTalk Server Web サービス公開ウィザードで、フィールドに含まれるデータが生成された web サービスを持つドキュメントを処理する場合、**データ型**の**xs:date**と**Nillable**プロパティの**True**ドキュメントから削除されます。  
  
##### <a name="cause"></a>原因  
 この問題は、Microsoft .NET Framework クラス ライブラリの名前空間 System.Xml.Serialization で提供されている XmlSerializer クラスを使用して既知の問題により発生します。  
  
##### <a name="resolution"></a>解決策  
 この問題を解決するには、Microsoft サポート技術情報の資料 925272 に記載されている .NET Framework 2.0 修正プログラムのインストール"[修正します。XML シリアル化は、.NET Framework 2.0 の XSD スキーマの一部の省略可能な要素を失う可能性があります](http://go.microsoft.com/fwlink/?LinkId=84696)"。  
  
## <a name="see-also"></a>参照  
 [IIS のアクセス許可の問題を解決するためのガイドライン](../core/guidelines-for-resolving-iis-permissions-problems.md)   
 [Web サービスのアクセス許可の問題を解決するためのガイドライン](../core/guidelines-for-resolving-web-services-permissions-problems.md)