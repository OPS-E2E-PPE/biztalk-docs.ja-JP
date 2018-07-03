---
title: BAM のトレースを有効にする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4da99e74-a41d-4ab1-a07d-e3bee6187216
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e116087d0c560822d8a0cc64c0719fe7ba4d6e85
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000811"
---
# <a name="how-to-enable-tracing-in-bam"></a>BAM のトレースを有効にする方法
BAM のトレースを有効にすると、次の 5 つの BAM コンポーネント内で発生した問題のトラブルシューティングに役立ちます。  
  
-   BAM 管理ユーティリティ  
  
-   BAM イベント バス  
  
-   BAM ポータル  
  
-   BAM 警告  
  
-   BAM WCF インターセプタ  
  
## <a name="enabling-tracing-for-the-bam-management-utility"></a>BAM 管理ユーティリティのトレースの有効化  
 BAM 管理ユーティリティのトレースを有効にすることによって、展開エラーに関する情報を取得することができます。 これは、2 つの方法で行うことができます。 コマンド ラインを使用して特定の BM.exe コマンドのトレースを有効にする方法と、BAM 管理ユーティリティの構成ファイルを変更してすべての BM.exe コマンドのトレースを有効にする方法です。  
  
### <a name="using-the-command-line"></a>コマンド ラインの使用  
 BM.exe コマンド ライン トレースをアクティブを使用して、 **-トレース: &#124;オフ**スイッチします。 Trace スイッチを使用すると、構成ファイルの設定がオーバーライドされます。  
  
 このスイッチは、通常の BM.exe コマンドと組み合わせて使用します。  
  
 以下に例を示します。  
  
 **bm.exe deploy-all DefinitionFile:PO.xml – トレース: 上**  
  
### <a name="using-the-configuration-file"></a>構成ファイルの使用  
 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking フォルダーにある BM.exe.config 構成ファイルを変更することによって、トレースを有効にすることができます。 このファイルが含まれています、 **system.diagnostics**セクション トレース要素が含まれます。 このセクションのコメントを解除すると、トレースが有効になります。 既定では、トレースは無効になっています。  
  
 `<system.diagnostics>`  
  
 `<!-- To turn on BAM tracing, remove this comment or use the "-trace:on" command-line switch`  
  
 `<switches>`  
  
 `<add name="bm" value="1" />`  
  
 `<add name="Microsoft.BizTalk.Bam.Management" value="1" />`  
  
 `</switches>`  
  
 `-->`  
  
## <a name="enabling-tracing-for-the-bam-event-bus"></a>BAM イベント バスのトレースの有効化  
 BAM イベント バスのトレースを有効にすると、2 種類のデータベース ストレージ エラーの診断に役立ちます。  
  
- 追跡プロファイル エディターの使用時に BizTalk Server サービスのイベントから発生したストレージ エラー  
  
- バッファーに格納されたイベント ストリーム API の使用時に生成されたストレージ エラー  
  
  BAM イベント バスのトレースを有効にするには、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] フォルダーにある BTSNTSvc.exe.config ファイルで次のセクションを編集または追加します。  
  
  `<system.diagnostics>`  
  
  `<switches>`  
  
  `<add name="Microsoft.BizTalk.Bam.EventBus" value="1" />`  
  
  `</switches>`  
  
  `<trace autoflush="true" indentsize="4">`  
  
  `<listeners>`  
  
  `<add name="Text" type="System.Diagnostics.TextWriterTraceListener" initializeData="c:\tdds.log"/>`  
  
  `</listeners>`  
  
  `</trace>`  
  
  `</system.diagnostics>`  
  
#### <a name="to-enable-tracing-for-the-bam-event-bus"></a>BAM イベント バスのトレースを有効にするには  
  
1. [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BTSNTSvc.exe.config ファイルを編集します。  
  
2. 検索、 \<system.diagnostics\>と\</system.diagnostics\>タグ。 該当するタグがファイル内に存在しない場合は、上記のコードをコピーして構成ファイルに貼り付けます。  
  
3. システム診断セクションの末尾のコメントの区切り記号を移動することによってコメントを解除します ('-->') から後、 \</system.diagnostics\>タグを前に、 \<system.diagnostics\>タグ。  
  
4. ファイルを保存します。  
  
## <a name="enabling-tracing-for-the-bam-portal"></a>BAM ポータルのトレースの有効化  
 BAM ポータルのトレースを有効にすると、接続の問題のトラブルシューティングを行うことができます。  
  
 BAM ポータルは ASP.NET アプリケーションであり、トレースの標準プロトコルに準拠しています。 内で、 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\web.config ファイル、という名前のセクションがある\<トレース\>有効にすることができます。  
  
#### <a name="to-enable-tracing-for-the-bam-portal"></a>BAM ポータルのトレースを有効にするには  
  
1. [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config ファイルを編集します。  
  
2. 検索、 \<system.diagnostics\>と\</system.diagnostics\>タグ。  
  
3. 終了コメントの区切り記号が移動してシステム診断セクションをコメント解除します ('-->') から後、 \</system.diagnostics\>タグを前に、 \<system.diagnostics\>タグ。  
  
4. initializeData 属性を変更して、トレース ログの書き込み先を指定します。  
  
5. 検索\<system.web\>タグ。  
  
6. system.web セクションで trace タグを探し、区切り記号 ('-->') を trace タグの後ろから trace タグの前に移動することによって trace コマンドのコメントを解除します。  
  
7. ファイルを保存します。  
  
   `<!--`  
  
   `TRACING: To turn tracing on:`  
  
   `1) Uncomment this tag and specify a file path for trace output`  
  
   `2) Uncomment the <trace tag> under <system.web>`  
  
   `The trace will be saved to the file pointed to by "initializeData" below.`  
  
   `Ensure that the target directory exists (C:\temp by default).`  
  
   `Make sure that the IIS worker process user account (usually Network Service or ASPNET)`  
  
   `and the BAM Portal user have write permissions for the trace log file directory (C:\temp below).`  
  
   `To turn tracing on, you will need to uncomment the <trace> tag under <system.web>`  
  
   `<system.diagnostics>`  
  
   `<trace autoflush="true" indentsize="2">`  
  
   `<listeners>`  
  
   `<add name="BAMPortalListener"`  
  
   `type="System.Diagnostics.TextWriterTraceListener"`  
  
   `initializeData="C:\temp\BAMPortalTrace.log" />`  
  
   `</listeners>`  
  
   `</trace>`  
  
   `</system.diagnostics>`  
  
   `-->`  
  
   `<!--`  
  
   `TRACING: To turn tracing on:`  
  
   `1) Uncomment this tag`  
  
   `2) Uncomment the <system.diagnostics> tag above and specify a file path for trace output`  
  
   `<trace enabled="true"`  
  
   `requestLimit="40"`  
  
   `pageOutput="false"`  
  
   `traceMode="SortByTime"`  
  
   `localOnly="true"`  
  
   `writeToDiagnosticsTrace="true" />`  
  
   `-->`  
  
## <a name="bam-alerting"></a>BAM 警告  
 BAM 警告のトレースを有効にすると、警告配信エラーのトラブルシューティングに役立ちます。  
  
 BAM 警告は、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Notification Services インフラストラクチャを基盤としています。 BAM 警告のトレースを有効にする、Notification Services がトラブルシューティングのトピックを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=79416](http://go.microsoft.com/fwlink/?LinkId=79416)します。  
  
## <a name="bam-interceptors"></a>BAM インターセプター  
 BAM インターセプターのエンド ツー エンドのトレースを有効にするには、アプリケーションの構成ファイルを変更する — Web でホストされるアプリケーションでは、appname.config 自己ホスト型アプリケーションの場合は Web.config です。 ファイルの変更方法の例を次に示します。  
  
```  
<system.diagnostics>  
  </sources>  
    <source name="Microsoft BizTalk Bam Interceptors" switchValue="All">  
      <listeners>  
  
        <add name="myListener"  
             type="System.Diagnostics.TextWriterTraceListener"  
             initializeData="TextWriterOutput.log" />  
      </listeners>  
    </source>  
  </sources>  
</system.diagnostics>  
```  
  
 Windows Workflow Foundation および Windows Communication Foundation 用の BAM インターセプターが、"Microsoft BizTalk Bam Interceptors" という名前のソースに書き込まれます。  
  
> [!NOTE]
>  ソース文字列では大文字と小文字が区別されるため、上記のとおりに記述する必要があります。 記述した文字列が上記の文字列と異なっていると、BAM インターセプターからトレース情報を受け取れません。  
  
 トレース レベルは switchValue の設定によって制御します。 指定できるトレース レベルを次の表にまとめます。  
  
|トレース レベル|説明|  
|-----------------|-----------------|  
|重大|フェールファストとイベント ログのエントリをログに記録し、関連付け情報をトレースします。|  
|[エラー]|すべての例外をログに記録します。|  
|警告|エラーまたは重大なエラーにつながる可能性のある条件が存在します。|  
|[情報]|システムの状態の監視と診断、パフォーマンスの測定、またはプロファイルに役立つメッセージが生成されます。 このような情報は、容量の計画やパフォーマンス管理に利用できます。|  
|"詳細"|ユーザー コードとサービスの両方を対象とするデバッグ レベルのトレースです。|  
|All|すべてのメッセージが対象になります。|  
  
> [!NOTE]
>  トレースはパフォーマンスに影響することがあります。 トレースを有効にするのは、トラブルシューティングの操作を実行する場合に限ってください。  
  
### <a name="viewing-the-wcf-trace-file"></a>WCF トレース ファイルの表示  
 WCF トレースを分析するには、WCF Service Trace Viewer ツールを使用します。 サービス トレース ビューアー ツールの詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=75218](http://go.microsoft.com/fwlink/?LinkId=75218)します。  
  
## <a name="see-also"></a>参照  
 [BAM の管理](../core/managing-bam.md)