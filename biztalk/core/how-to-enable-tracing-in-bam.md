---
title: BAM のトレースを有効にする方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 084eaf8cd4ba1c251b1c196830f76ef9c6a8e33f
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
ms.locfileid: "25971960"
---
# <a name="how-to-enable-tracing-in-bam"></a><span data-ttu-id="17f21-102">BAM のトレースを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="17f21-102">How to Enable Tracing in BAM</span></span>
<span data-ttu-id="17f21-103">BAM のトレースを有効にすると、次の 5 つの BAM コンポーネント内で発生した問題のトラブルシューティングに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="17f21-103">You can enable tracing in BAM to help troubleshoot problems within the following five BAM components:</span></span>  
  
-   <span data-ttu-id="17f21-104">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="17f21-104">BAM Management utility</span></span>  
  
-   <span data-ttu-id="17f21-105">BAM イベント バス</span><span class="sxs-lookup"><span data-stu-id="17f21-105">BAM event bus</span></span>  
  
-   <span data-ttu-id="17f21-106">BAM ポータル</span><span class="sxs-lookup"><span data-stu-id="17f21-106">BAM portal</span></span>  
  
-   <span data-ttu-id="17f21-107">BAM 警告</span><span class="sxs-lookup"><span data-stu-id="17f21-107">BAM alerting</span></span>  
  
-   <span data-ttu-id="17f21-108">BAM WCF インターセプタ</span><span class="sxs-lookup"><span data-stu-id="17f21-108">BAM WCF Interceptor</span></span>  
  
## <a name="enabling-tracing-for-the-bam-management-utility"></a><span data-ttu-id="17f21-109">BAM 管理ユーティリティのトレースの有効化</span><span class="sxs-lookup"><span data-stu-id="17f21-109">Enabling Tracing for the BAM Management Utility</span></span>  
 <span data-ttu-id="17f21-110">BAM 管理ユーティリティのトレースを有効にすることによって、展開エラーに関する情報を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="17f21-110">You can obtain information about deployment failures by enabling tracing for the BAM Management utility.</span></span> <span data-ttu-id="17f21-111">これは、2 つの方法で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="17f21-111">You can do this in two ways.</span></span> <span data-ttu-id="17f21-112">コマンド ラインを使用して特定の BM.exe コマンドのトレースを有効にする方法と、BAM 管理ユーティリティの構成ファイルを変更してすべての BM.exe コマンドのトレースを有効にする方法です。</span><span class="sxs-lookup"><span data-stu-id="17f21-112">You can enable tracing via the command line for specific BM.exe commands, or you can modify the BAM Management utility configuration file to enable tracing for all BM.exe commands.</span></span>  
  
### <a name="using-the-command-line"></a><span data-ttu-id="17f21-113">コマンド ラインの使用</span><span class="sxs-lookup"><span data-stu-id="17f21-113">Using the Command Line</span></span>  
 <span data-ttu-id="17f21-114">BM.exe コマンド ライン トレースをアクティブに使用する、 **-トレース: &#124;オフ** スイッチです。</span><span class="sxs-lookup"><span data-stu-id="17f21-114">BM.exe command line tracing is activated using the **-Trace:on&#124;off** switch.</span></span> <span data-ttu-id="17f21-115">Trace スイッチを使用すると、構成ファイルの設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="17f21-115">Using the Trace switch overrides the settings in the configuration file.</span></span>  
  
 <span data-ttu-id="17f21-116">このスイッチは、通常の BM.exe コマンドと組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="17f21-116">The switch is used in conjunction with any normal BM.exe command.</span></span>  
  
 <span data-ttu-id="17f21-117">例:</span><span class="sxs-lookup"><span data-stu-id="17f21-117">For example:</span></span>  
  
 <span data-ttu-id="17f21-118">**bm.exe deploy-all DefinitionFile:PO.xml – トレース:** </span><span class="sxs-lookup"><span data-stu-id="17f21-118">**bm.exe deploy-all -DefinitionFile:PO.xml –Trace:On**</span></span>  
  
### <a name="using-the-configuration-file"></a><span data-ttu-id="17f21-119">構成ファイルの使用</span><span class="sxs-lookup"><span data-stu-id="17f21-119">Using the Configuration File</span></span>  
 <span data-ttu-id="17f21-120">[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking フォルダーにある BM.exe.config 構成ファイルを変更することによって、トレースを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="17f21-120">You can enable tracing by modifying the BM.exe.config configuration file located in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking folder.</span></span> <span data-ttu-id="17f21-121">このファイルには、 **system.diagnostics** セクション トレース要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="17f21-121">This file contains a **system.diagnostics** section which contains the tracing elements.</span></span> <span data-ttu-id="17f21-122">このセクションのコメントを解除すると、トレースが有効になります。</span><span class="sxs-lookup"><span data-stu-id="17f21-122">Remove the comment to enable tracing.</span></span> <span data-ttu-id="17f21-123">既定では、トレースは無効になっています。</span><span class="sxs-lookup"><span data-stu-id="17f21-123">By default, tracing is not enabled.</span></span>  
  
 `<system.diagnostics>`  
  
 `<!-- To turn on BAM tracing, remove this comment or use the "-trace:on" command-line switch`  
  
 `<switches>`  
  
 `<add name="bm" value="1" />`  
  
 `<add name="Microsoft.BizTalk.Bam.Management" value="1" />`  
  
 `</switches>`  
  
 `-->`  
  
## <a name="enabling-tracing-for-the-bam-event-bus"></a><span data-ttu-id="17f21-124">BAM イベント バスのトレースの有効化</span><span class="sxs-lookup"><span data-stu-id="17f21-124">Enabling Tracing for the BAM Event Bus</span></span>  
 <span data-ttu-id="17f21-125">BAM イベント バスのトレースを有効にすると、2 種類のデータベース ストレージ エラーの診断に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="17f21-125">Enabling tracing for the BAM event bus can help you diagnose two classes of database storage errors:</span></span>  
  
-   <span data-ttu-id="17f21-126">追跡プロファイル エディターの使用時に BizTalk Server サービスのイベントから発生したストレージ エラー</span><span class="sxs-lookup"><span data-stu-id="17f21-126">Storage errors originating from events from the BizTalk Server service when using the Tracking Profile Editor.</span></span>  
  
-   <span data-ttu-id="17f21-127">バッファーに格納されたイベント ストリーム API の使用時に生成されたストレージ エラー</span><span class="sxs-lookup"><span data-stu-id="17f21-127">Storage errors generated when using the buffered event stream APIs.</span></span>  
  
 <span data-ttu-id="17f21-128">BAM イベント バスのトレースを有効にするには、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] フォルダーにある BTSNTSvc.exe.config ファイルで次のセクションを編集または追加します。</span><span class="sxs-lookup"><span data-stu-id="17f21-128">To enable tracing for the BAM event bus, edit or add the following section of the BTSNTSvc.exe.config file located in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] folder.</span></span>  
  
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
  
#### <a name="to-enable-tracing-for-the-bam-event-bus"></a><span data-ttu-id="17f21-129">BAM イベント バスのトレースを有効にするには</span><span class="sxs-lookup"><span data-stu-id="17f21-129">To enable tracing for the BAM Event bus</span></span>  
  
1.  <span data-ttu-id="17f21-130">[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BTSNTSvc.exe.config ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="17f21-130">Edit the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BTSNTSvc.exe.config file.</span></span>  
  
2.  <span data-ttu-id="17f21-131">検索、 \<system.diagnostics\>と\</system.diagnostics\>タグ。</span><span class="sxs-lookup"><span data-stu-id="17f21-131">Locate the \<system.diagnostics\> and \</system.diagnostics\> tag.</span></span> <span data-ttu-id="17f21-132">該当するタグがファイル内に存在しない場合は、上記のコードをコピーして構成ファイルに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="17f21-132">If they are not present in the file, copy the code listed above and paste it into the configuration file.</span></span>  
  
3.  <span data-ttu-id="17f21-133">終了コメント区切り記号を移動することによって、システム診断のセクションのコメントを解除 ('-->') から後、 \</system.diagnostics\>タグを前に、 \<system.diagnostics\>タグ。</span><span class="sxs-lookup"><span data-stu-id="17f21-133">Uncomment the Uncomment the system diagnostics section by moving the end comment delimiter ('-->') from after the \</system.diagnostics\> tag to before the \<system.diagnostics\> tag.</span></span>  
  
4.  <span data-ttu-id="17f21-134">ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="17f21-134">Save the file.</span></span>  
  
## <a name="enabling-tracing-for-the-bam-portal"></a><span data-ttu-id="17f21-135">BAM ポータルのトレースの有効化</span><span class="sxs-lookup"><span data-stu-id="17f21-135">Enabling Tracing for the BAM Portal</span></span>  
 <span data-ttu-id="17f21-136">BAM ポータルのトレースを有効にすると、接続の問題のトラブルシューティングを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="17f21-136">Enabling tracing for the BAM portal allows you to troubleshoot connectivity issues.</span></span>  
  
 <span data-ttu-id="17f21-137">BAM ポータルは ASP.NET アプリケーションであり、トレースの標準プロトコルに準拠しています。</span><span class="sxs-lookup"><span data-stu-id="17f21-137">The BAM portal is an ASP.NET application, and follows the standard protocol for tracing.</span></span> <span data-ttu-id="17f21-138">内で、 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]bamportal \web.config ファイルというセクションがある\<トレース\>有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="17f21-138">Within the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config file, there is a section called \<trace\> which you can enable.</span></span>  
  
#### <a name="to-enable-tracing-for-the-bam-portal"></a><span data-ttu-id="17f21-139">BAM ポータルのトレースを有効にするには</span><span class="sxs-lookup"><span data-stu-id="17f21-139">To enable tracing for the BAM portal</span></span>  
  
1.  <span data-ttu-id="17f21-140">[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="17f21-140">Edit the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config file.</span></span>  
  
2.  <span data-ttu-id="17f21-141">検索、 \<system.diagnostics\>と\</system.diagnostics\>タグ。</span><span class="sxs-lookup"><span data-stu-id="17f21-141">Locate the \<system.diagnostics\> and \</system.diagnostics\> tags.</span></span>  
  
3.  <span data-ttu-id="17f21-142">移動の末尾のコメント デリミター system diagnostics セクションのコメントを解除 ('-->') から後、 \</system.diagnostics\>タグを前に、 \<system.diagnostics\>タグ。</span><span class="sxs-lookup"><span data-stu-id="17f21-142">Uncomment the system diagnostics section by moving end comment delimiter ('-->') from after the \</system.diagnostics\> tag to before the \<system.diagnostics\> tag.</span></span>  
  
4.  <span data-ttu-id="17f21-143">initializeData 属性を変更して、トレース ログの書き込み先を指定します。</span><span class="sxs-lookup"><span data-stu-id="17f21-143">Modify the initializeData attribute to specify the location to write the tracing log.</span></span>  
  
5.  <span data-ttu-id="17f21-144">検索\<system.web\>タグ。</span><span class="sxs-lookup"><span data-stu-id="17f21-144">Locate \<system.web\> tag.</span></span>  
  
6.  <span data-ttu-id="17f21-145">system.web セクションで trace タグを探し、区切り記号 ('-->') を trace タグの後ろから trace タグの前に移動することによって trace コマンドのコメントを解除します。</span><span class="sxs-lookup"><span data-stu-id="17f21-145">In the system.web section locate the trace tag and uncomment the trace command by moving the delimiter ('-->') from after the trace tag to before it.</span></span>  
  
7.  <span data-ttu-id="17f21-146">ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="17f21-146">Save the file.</span></span>  
  
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
  
## <a name="bam-alerting"></a><span data-ttu-id="17f21-147">BAM 警告</span><span class="sxs-lookup"><span data-stu-id="17f21-147">BAM Alerting</span></span>  
 <span data-ttu-id="17f21-148">BAM 警告のトレースを有効にすると、警告配信エラーのトラブルシューティングに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="17f21-148">Enabling tracing for BAM alerting helps you troubleshoot alert delivery failures.</span></span>  
  
 <span data-ttu-id="17f21-149">BAM 警告は、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Notification Services インフラストラクチャを基盤としています。</span><span class="sxs-lookup"><span data-stu-id="17f21-149">BAM alerting is built on the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Notification Services infrastructure.</span></span> <span data-ttu-id="17f21-150">BAM 警告のトレースを有効にするには、トラブルシューティングのトピックで、Notification Services を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=79416](http://go.microsoft.com/fwlink/?LinkId=79416)です。</span><span class="sxs-lookup"><span data-stu-id="17f21-150">To enable tracing on BAM alerting, see the Notification Services troubleshooting topics at [http://go.microsoft.com/fwlink/?LinkId=79416](http://go.microsoft.com/fwlink/?LinkId=79416).</span></span>  
  
## <a name="bam-interceptors"></a><span data-ttu-id="17f21-151">BAM インターセプター</span><span class="sxs-lookup"><span data-stu-id="17f21-151">BAM Interceptors</span></span>  
 <span data-ttu-id="17f21-152">BAM インターセプターのエンド ツー エンド トレースを有効にするには、アプリケーションの構成ファイルを変更するなど、Web ホストされるアプリケーション appname.config 自己ホスト型アプリケーションの場合は Web.config です。</span><span class="sxs-lookup"><span data-stu-id="17f21-152">To enable end-to-end tracing of the BAM interceptors, you modify the application’s configuration file—either Web.config for Web-hosted applications, or Appname.config for self-hosted applications.</span></span> <span data-ttu-id="17f21-153">ファイルの変更方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="17f21-153">The following is an example of how you can modify the file:</span></span>  
  
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
  
 <span data-ttu-id="17f21-154">Windows Workflow Foundation および Windows Communication Foundation 用の BAM インターセプターが、"Microsoft BizTalk Bam Interceptors" という名前のソースに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="17f21-154">BAM Interceptor for Windows Workflow Foundation and Windows Communication Foundation are written to the source named "Microsoft BizTalk Bam Interceptors".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="17f21-155">ソース文字列では大文字と小文字が区別されるため、上記のとおりに記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17f21-155">The source string is case-sensitive and must appear exactly as shown.</span></span> <span data-ttu-id="17f21-156">記述した文字列が上記の文字列と異なっていると、BAM インターセプターからトレース情報を受け取れません。</span><span class="sxs-lookup"><span data-stu-id="17f21-156">If your string is different than the one shown, you will not receive trace information for the BAM interceptors.</span></span>  
  
 <span data-ttu-id="17f21-157">トレース レベルは switchValue の設定によって制御します。</span><span class="sxs-lookup"><span data-stu-id="17f21-157">You control the tracing level by setting switchValue.</span></span> <span data-ttu-id="17f21-158">指定できるトレース レベルを次の表にまとめます。</span><span class="sxs-lookup"><span data-stu-id="17f21-158">The available tracing levels are summarized in the following table.</span></span>  
  
|<span data-ttu-id="17f21-159">トレース レベル</span><span class="sxs-lookup"><span data-stu-id="17f21-159">Trace Level</span></span>|<span data-ttu-id="17f21-160">Description</span><span class="sxs-lookup"><span data-stu-id="17f21-160">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="17f21-161">重大</span><span class="sxs-lookup"><span data-stu-id="17f21-161">Critical</span></span>|<span data-ttu-id="17f21-162">フェールファストとイベント ログのエントリをログに記録し、関連付け情報をトレースします。</span><span class="sxs-lookup"><span data-stu-id="17f21-162">Logs Fail-Fast and Event Log entries, and trace correlation information.</span></span>|  
|<span data-ttu-id="17f21-163">[エラー]</span><span class="sxs-lookup"><span data-stu-id="17f21-163">Error</span></span>|<span data-ttu-id="17f21-164">すべての例外をログに記録します。</span><span class="sxs-lookup"><span data-stu-id="17f21-164">Logs all exceptions.</span></span>|  
|<span data-ttu-id="17f21-165">警告</span><span class="sxs-lookup"><span data-stu-id="17f21-165">Warning</span></span>|<span data-ttu-id="17f21-166">エラーまたは重大なエラーにつながる可能性のある条件が存在します。</span><span class="sxs-lookup"><span data-stu-id="17f21-166">A condition exists that may subsequently result in an error or critical failure.</span></span>|  
|<span data-ttu-id="17f21-167">情報</span><span class="sxs-lookup"><span data-stu-id="17f21-167">Information</span></span>|<span data-ttu-id="17f21-168">システムの状態の監視と診断、パフォーマンスの測定、またはプロファイルに役立つメッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="17f21-168">Messages helpful for monitoring and diagnosing system status, measuring performance, or profiling are generated.</span></span> <span data-ttu-id="17f21-169">このような情報は、容量の計画やパフォーマンス管理に利用できます。</span><span class="sxs-lookup"><span data-stu-id="17f21-169">You can utilize such information for capacity planning and performance management.</span></span>|  
|<span data-ttu-id="17f21-170">Verbose</span><span class="sxs-lookup"><span data-stu-id="17f21-170">Verbose</span></span>|<span data-ttu-id="17f21-171">ユーザー コードとサービスの両方を対象とするデバッグ レベルのトレースです。</span><span class="sxs-lookup"><span data-stu-id="17f21-171">Debug-level tracing for both user code and servicing.</span></span>|  
|<span data-ttu-id="17f21-172">すべて</span><span class="sxs-lookup"><span data-stu-id="17f21-172">All</span></span>|<span data-ttu-id="17f21-173">すべてのメッセージが対象になります。</span><span class="sxs-lookup"><span data-stu-id="17f21-173">All messages.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="17f21-174">トレースはパフォーマンスに影響することがあります。</span><span class="sxs-lookup"><span data-stu-id="17f21-174">Tracing can have an adverse affect on performance.</span></span> <span data-ttu-id="17f21-175">トレースを有効にするのは、トラブルシューティングの操作を実行する場合に限ってください。</span><span class="sxs-lookup"><span data-stu-id="17f21-175">Only enable tracing when you are performing troubleshooting activities.</span></span>  
  
### <a name="viewing-the-wcf-trace-file"></a><span data-ttu-id="17f21-176">WCF トレース ファイルの表示</span><span class="sxs-lookup"><span data-stu-id="17f21-176">Viewing the WCF Trace File</span></span>  
 <span data-ttu-id="17f21-177">WCF トレースを分析するには、WCF Service Trace Viewer ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="17f21-177">To analyze the WCF trace you use the WCF Service Trace Viewer Tool.</span></span> <span data-ttu-id="17f21-178">サービス トレース ビューアー ツールの詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=75218](http://go.microsoft.com/fwlink/?LinkId=75218)です。</span><span class="sxs-lookup"><span data-stu-id="17f21-178">For more information about the Service Trace Viewer Tool, see [http://go.microsoft.com/fwlink/?LinkId=75218](http://go.microsoft.com/fwlink/?LinkId=75218).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17f21-179">参照</span><span class="sxs-lookup"><span data-stu-id="17f21-179">See Also</span></span>  
 [<span data-ttu-id="17f21-180">BAM の管理</span><span class="sxs-lookup"><span data-stu-id="17f21-180">Managing BAM</span></span>](../core/managing-bam.md)