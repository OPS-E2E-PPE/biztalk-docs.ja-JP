---
title: BAM WCF インターセプタと WF インターセプタに関する既知の問題 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2407809-1f71-41a9-b305-722a7f86af5b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42078eb2b1272072016ded9a117e88ddf4fda038
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262026"
---
# <a name="known-issues-with-the-bam-wcf-and-wf-interceptors"></a><span data-ttu-id="6bc5d-102">BAM WCF インターセプタと WF インターセプタに関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="6bc5d-102">Known Issues with the BAM WCF and WF Interceptors</span></span>
<span data-ttu-id="6bc5d-103">このセクションでは、Windows Workflow Foundation または Windows Communication Foundation の BAM インターセプタを使用する際に発生する可能性がある既知の問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-103">This section provides information about known issues that you may experience when using the BAM interceptors for Windows Workflow Foundation or Windows Communication Foundation.</span></span>  
  
## <a name="intercepting-a-dynamically-generated-wcf-assembly-hosted-in-iis"></a><span data-ttu-id="6bc5d-104">IIS でホストされている WCF アセンブリ (動的に生成されたもの) を受け取る</span><span class="sxs-lookup"><span data-stu-id="6bc5d-104">Intercepting a dynamically generated WCF assembly hosted in IIS</span></span>  
 <span data-ttu-id="6bc5d-105">IIS を使用して埋め込み型の Windows Communication Foundation アプリケーション (たとえば、アセンブリ ソースを指定するサービス ファイルなど) を使用している場合、WCF アセンブリが動的に生成され、任意のファイル名を割り当てられて、asp.net の一時フォルダに配置されます。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-105">When you are using IIS to host an embedded Windows Communication Foundation application (for example, a service file that specifies the assembly source), the WCF assembly will be dynamically generated, assigned an arbitrary file name, and placed in the asp.net temporary folder.</span></span> <span data-ttu-id="6bc5d-106">インターセプター構成ファイルがマニフェスト情報を必要とするため、およびワイルドカード文字や、マニフェストを指定するための他の動的メソッドはインターセプター構成ファイルで使用可能ではないため、する必要があります、サービスを再コンパイルし、し、ビルドインターセプター構成ファイル、または再展開した後、インターセプター構成ファイルにデプロイを含む asp.net web ページのすべての WCF コードに埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-106">Since the interceptor configuration file requires manifest information and since wildcard characters or other dynamic methods for specifying the manifest are not available with interceptor configuration files, you must recompile your service and then build your interceptor configuration file or redeploy your interceptor configuration file after you have deployed all of the asp.net web pages containing embedded WCF code.</span></span>  
  
## <a name="use-of-the-bam-interceptor-for-windows-workflow-foundation-is-not-supported-in-office-and-sharepoint-server"></a><span data-ttu-id="6bc5d-107">Windows Workflow Foundation の BAM インターセプタが Office および Sharepoint Server でサポートされない</span><span class="sxs-lookup"><span data-stu-id="6bc5d-107">Use of the BAM interceptor for Windows Workflow Foundation is not supported in Office and Sharepoint Server</span></span>  
 <span data-ttu-id="6bc5d-108">Office と Windows Sharepoint Server はいずれも、WF ランタイムを初期化するときにアプリケーション構成ファイルを読み込みません。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-108">Both office and Windows Sharepoint Server do not read from the application configuration file when initializing the WF runtime.</span></span> <span data-ttu-id="6bc5d-109">WF の BAM インターセプタはアプリケーション用に構成されますが、これらの環境でホストされるときにワークフロー ランタイムに読み込まれません。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-109">As a result, the BAM interceptor for WF may be configured for an application but it will not be loaded into the workflow runtime when hosted within these environments.</span></span>  
  
## <a name="client-service-locks-when-intiating-a-distributed-transaction"></a><span data-ttu-id="6bc5d-110">分散トランザクションの開始時にクライアント サービスがロックする</span><span class="sxs-lookup"><span data-stu-id="6bc5d-110">Client service locks when intiating a distributed transaction</span></span>  
 <span data-ttu-id="6bc5d-111">クライアントによって開始されたトランザクションにサービス操作が参加しておらず、クライアントがこのサービスをトランザクション スコープのコンテキストから開始したときは、デッドロックが発生することがあります。特に、送信 - 要求の前にクライアントから収集されたデータと、同じアクティビティに関する受信 - 要求によってサービスから収集されたデータが存在する場合は、デッドロックが発生する確率が高くなります。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-111">If the service operation will not be participating in the transaction initiated by the client and the client is invoking the service from the context of a transaction scope, a deadlock could result, especially if there is data being collected from the client before the send request and from the service by the receive request for the same activity.</span></span>  
  
 <span data-ttu-id="6bc5d-112">このような状況を回避するには、クライアントがトランザクションに参加しないように指定します。これを行うには、次に示すように、クライアントの app.config ファイルで BAM 動作拡張機能に関するクライアントの `ConnectionString` 属性で "Enlist = false" を宣言します。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-112">To avoid this situation, you should specify that the client does not participate in the transaction by declaring "Enlist = false" in the client `ConnectionString` attribute for the BAM behavior extension in the client's app.config file as demonstrated below.</span></span>  
  
```  
<behavior name="bamClientBehavior">  
  <bamClientBehaviorExtension ConnectionString="Integrated Security=SSPI;Initial Catalog=BAMPrimaryImport;Data Source=.;  Enlist=false"  PollingIntervalSec="1500" />  
</behavior>  
```  
  
## <a name="open-wcf-channel-before-sending-a-message-when-bam-interceptors-are-used"></a><span data-ttu-id="6bc5d-113">BAM インターセプターを使用するとメッセージの送信前に WCF チャネルが開く</span><span class="sxs-lookup"><span data-stu-id="6bc5d-113">Open WCF Channel Before Sending a Message when BAM Interceptors are used</span></span>  
 <span data-ttu-id="6bc5d-114">BasicHttp バインドを適用した WCF で BAM インターセプターを有効にすると、プロキシにより proxy.Open() が呼び出され、チャネルが明示的に開きます。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-114">When BAM interceptor is enabled for WCF with BasicHttp binding, proxy should call proxy.Open() to explicitly open the channel.</span></span> <span data-ttu-id="6bc5d-115">チャネルが明示的に開かない場合、BAM インターセプションに失敗し、例外が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-115">If the channel is not opened explicitly, BAM interception can fail with an exception.</span></span>