---
title: BAM WCF インターセプターと WF インターセプターに関する既知の問題 |Microsoft Docs
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
ms.openlocfilehash: b938dff130ae08e75f54fc1b619fad109515a5d4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330066"
---
# <a name="known-issues-with-the-bam-wcf-and-wf-interceptors"></a><span data-ttu-id="22a9c-102">BAM WCF インターセプタと WF インターセプタに関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="22a9c-102">Known Issues with the BAM WCF and WF Interceptors</span></span>
<span data-ttu-id="22a9c-103">このセクションでは、Windows Workflow Foundation または Windows Communication Foundation の BAM インターセプタを使用する場合に発生する可能性がある既知の問題に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="22a9c-103">This section provides information about known issues that you may experience when using the BAM interceptors for Windows Workflow Foundation or Windows Communication Foundation.</span></span>  
  
## <a name="intercepting-a-dynamically-generated-wcf-assembly-hosted-in-iis"></a><span data-ttu-id="22a9c-104">IIS でホストされる動的に生成された WCF アセンブリをインターセプト</span><span class="sxs-lookup"><span data-stu-id="22a9c-104">Intercepting a dynamically generated WCF assembly hosted in IIS</span></span>  
 <span data-ttu-id="22a9c-105">IIS を使用して、埋め込みの Windows Communication Foundation アプリケーション (たとえば、アセンブリのソースを指定するサービス ファイル) をホストする場合は、WCF アセンブリが動的に生成、任意のファイル名、および asp.net で配置された割り当てられています。一時フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="22a9c-105">When you are using IIS to host an embedded Windows Communication Foundation application (for example, a service file that specifies the assembly source), the WCF assembly will be dynamically generated, assigned an arbitrary file name, and placed in the asp.net temporary folder.</span></span> <span data-ttu-id="22a9c-106">サービスを再コンパイルし、ビルドする必要があります、インターセプタ構成ファイルには、マニフェスト情報が必要なため、およびワイルドカード文字またはマニフェストを指定するための他の動的メソッドはインターセプター構成ファイルで使用できないため、すべてを含む asp.net web ページの展開した後、インターセプタ構成ファイル、インターセプター構成ファイルや再デプロイには、WCF コードが埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="22a9c-106">Since the interceptor configuration file requires manifest information and since wildcard characters or other dynamic methods for specifying the manifest are not available with interceptor configuration files, you must recompile your service and then build your interceptor configuration file or redeploy your interceptor configuration file after you have deployed all of the asp.net web pages containing embedded WCF code.</span></span>  
  
## <a name="use-of-the-bam-interceptor-for-windows-workflow-foundation-is-not-supported-in-office-and-sharepoint-server"></a><span data-ttu-id="22a9c-107">Office および Sharepoint Server for Windows Workflow Foundation BAM インターセプターの使用はサポートされていません</span><span class="sxs-lookup"><span data-stu-id="22a9c-107">Use of the BAM interceptor for Windows Workflow Foundation is not supported in Office and Sharepoint Server</span></span>  
 <span data-ttu-id="22a9c-108">Office と Windows Sharepoint のサーバーの両方から読み取りませんアプリケーション構成ファイル、WF ランタイムを初期化するときにします。</span><span class="sxs-lookup"><span data-stu-id="22a9c-108">Both office and Windows Sharepoint Server do not read from the application configuration file when initializing the WF runtime.</span></span> <span data-ttu-id="22a9c-109">その結果、アプリケーションの WF の BAM インターセプタを構成することがありますが、これらの環境でホストされている場合は、ワークフロー ランタイムに読み込まれません。</span><span class="sxs-lookup"><span data-stu-id="22a9c-109">As a result, the BAM interceptor for WF may be configured for an application but it will not be loaded into the workflow runtime when hosted within these environments.</span></span>  
  
## <a name="client-service-locks-when-intiating-a-distributed-transaction"></a><span data-ttu-id="22a9c-110">クライアント サービスがロックする分散トランザクションの開始時</span><span class="sxs-lookup"><span data-stu-id="22a9c-110">Client service locks when intiating a distributed transaction</span></span>  
 <span data-ttu-id="22a9c-111">サービス操作がクライアントによって開始されたトランザクションに参加していませんが、クライアントがトランザクション スコープのコンテキストからサービスを呼び出す場合は、デッドロックが発生し、前に、クライアントから収集されるデータがある場合は特に、要求を送信し、同じアクティビティに関する受信-要求によってサービスから。</span><span class="sxs-lookup"><span data-stu-id="22a9c-111">If the service operation will not be participating in the transaction initiated by the client and the client is invoking the service from the context of a transaction scope, a deadlock could result, especially if there is data being collected from the client before the send request and from the service by the receive request for the same activity.</span></span>  
  
 <span data-ttu-id="22a9c-112">このような状況を避けるためには、クライアントが宣言することでのトランザクションに参加しないことを指定する必要があります"Enlist = false"、クライアントで`ConnectionString`次に示すように、クライアントの app.config ファイルで BAM 動作拡張機能の属性します。</span><span class="sxs-lookup"><span data-stu-id="22a9c-112">To avoid this situation, you should specify that the client does not participate in the transaction by declaring "Enlist = false" in the client `ConnectionString` attribute for the BAM behavior extension in the client's app.config file as demonstrated below.</span></span>  
  
```  
<behavior name="bamClientBehavior">  
  <bamClientBehaviorExtension ConnectionString="Integrated Security=SSPI;Initial Catalog=BAMPrimaryImport;Data Source=.;  Enlist=false"  PollingIntervalSec="1500" />  
</behavior>  
```  
  
## <a name="open-wcf-channel-before-sending-a-message-when-bam-interceptors-are-used"></a><span data-ttu-id="22a9c-113">BAM インターセプタを使用する場合、WCF チャネルの送信前に、メッセージを開く</span><span class="sxs-lookup"><span data-stu-id="22a9c-113">Open WCF Channel Before Sending a Message when BAM Interceptors are used</span></span>  
 <span data-ttu-id="22a9c-114">BasicHttp のバインディングでの WCF に BAM インターセプターが有効な場合、プロキシは、プロキシを呼び出す必要があります。Open() を明示的にチャネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="22a9c-114">When BAM interceptor is enabled for WCF with BasicHttp binding, proxy should call proxy.Open() to explicitly open the channel.</span></span> <span data-ttu-id="22a9c-115">チャネルが明示的に開かれていない、BAM インターセプションは例外で失敗します。</span><span class="sxs-lookup"><span data-stu-id="22a9c-115">If the channel is not opened explicitly, BAM interception can fail with an exception.</span></span>