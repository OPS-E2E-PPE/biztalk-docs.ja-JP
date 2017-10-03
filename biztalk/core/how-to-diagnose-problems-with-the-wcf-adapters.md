---
title: "WCF アダプタに関する問題を診断する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 997a4ecd-6077-45d6-82d3-3f658ca62fd4
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dfa941fb5d19559447740f4f74e00f61b63fdacc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-diagnose-problems-with-the-wcf-adapters"></a><span data-ttu-id="ef5e8-102">WCF アダプタに関する問題の診断方法</span><span class="sxs-lookup"><span data-stu-id="ef5e8-102">How to Diagnose Problems with the WCF Adapters</span></span>
<span data-ttu-id="ef5e8-103">このセクションでは、WCF アダプタに関する問題の診断手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="ef5e8-103">This section contains steps that you can follow to help diagnose problems with the WCF adapters.</span></span>  
  
### <a name="check-the-iis-log-and-httperr-log-of-the-iis-server-for-errors"></a><span data-ttu-id="ef5e8-104">IIS ログおよび HTTPERR ログ、IIS サーバーのエラーを確認します。</span><span class="sxs-lookup"><span data-stu-id="ef5e8-104">Check the IIS log and HTTPERR log of the IIS server for errors</span></span>  
  
-   <span data-ttu-id="ef5e8-105">ソースまたはターゲットの IIS サーバー ログ ファイルには、WCF 分離アダプタに関する問題のトラブルシューティングに役立つ情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ef5e8-105">The source or target IIS server log files can contain information that is helpful for troubleshooting problems with the isolated WCF adapters.</span></span> <span data-ttu-id="ef5e8-106">既定では、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] コンピューターの IIS ログ ファイルは次のディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="ef5e8-106">By default the IIS log files on a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] computer are located in the following directory:</span></span>  
  
     <span data-ttu-id="ef5e8-107">*%Windir%\\*system32\LogFiles\W3SVC1\\</span><span class="sxs-lookup"><span data-stu-id="ef5e8-107">*%WinDir%\\*system32\LogFiles\W3SVC1\\</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ef5e8-108">*%Windir%*の場所のプレース ホルダー、[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]ディレクトリ、IIS サーバーにします。</span><span class="sxs-lookup"><span data-stu-id="ef5e8-108">*%WinDir%* is a placeholder for the location of the [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] directory on the IIS server.</span></span>  
  
     <span data-ttu-id="ef5e8-109">既定では、[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] と [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] ベースのコンピューターの HTTPERR ログ ファイルは次のディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="ef5e8-109">By default the HTTPERR log files on a [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] and [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] based computers are located in the following directory:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ef5e8-110">HTTPERR ログ ファイルは、[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] と [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] ベースのコンピューターでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ef5e8-110">The HTTPERR log file is available only on [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] and [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] based computers.</span></span>  
  
     <span data-ttu-id="ef5e8-111">*%Windir%\\*system32\LogFiles\HTTPERR\\</span><span class="sxs-lookup"><span data-stu-id="ef5e8-111">*%WinDir%\\*system32\LogFiles\HTTPERR\\</span></span>  
  
### <a name="use-wcf-message-logging-for-fault-monitoring-and-diagnosis-of-problems-from-the-wcf-adapters"></a><span data-ttu-id="ef5e8-112">WCF メッセージ ログの記録を WCF アダプタの障害監視と問題の診断に使用する</span><span class="sxs-lookup"><span data-stu-id="ef5e8-112">Use WCF message logging for fault monitoring and diagnosis of problems from the WCF adapters</span></span>  
  
1.  <span data-ttu-id="ef5e8-113">WCF には、受信メッセージと送信メッセージをオフラインで使用するためにログに記録する機能が備わっています。</span><span class="sxs-lookup"><span data-stu-id="ef5e8-113">WCF provides the capability to log incoming and outgoing messages for offline consumption.</span></span> <span data-ttu-id="ef5e8-114">メッセージ ログを記録すると、WCF アダプタを経由して送受信するメッセージを確認できます。</span><span class="sxs-lookup"><span data-stu-id="ef5e8-114">You can use message logging to see what the messages incoming and outgoing through the WCF adapters look like.</span></span> <span data-ttu-id="ef5e8-115">WCF は既定ではメッセージをログに記録しません。</span><span class="sxs-lookup"><span data-stu-id="ef5e8-115">WCF does not log messages by default.</span></span> <span data-ttu-id="ef5e8-116">メッセージ ログの記録をアクティブ化するには、WCF アダプタが使用する構成ファイルを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef5e8-116">To activate message logging, you have to modify the configuration files that the WCF adapters use.</span></span> <span data-ttu-id="ef5e8-117">WCF メッセージ ログの記録の詳細についてを参照してください「ログ メッセージ」 [http://go.microsoft.com/fwlink/?LinkId=89003](http://go.microsoft.com/fwlink/?LinkId=89003)です。</span><span class="sxs-lookup"><span data-stu-id="ef5e8-117">For more information about WCF message logging, see "Message Logging" at [http://go.microsoft.com/fwlink/?LinkId=89003](http://go.microsoft.com/fwlink/?LinkId=89003).</span></span>  
  
2.  <span data-ttu-id="ef5e8-118">インプロセス WCF アダプタの場合、アプリケーション構成ファイルの変更を WCF メッセージ ログの記録を有効にする**BTSNtSvc.exe.config**の**BTSNtSvc.exe**です。</span><span class="sxs-lookup"><span data-stu-id="ef5e8-118">For the in-process WCF adapters, you can enable WCF message logging by modifying the application configuration file, **BTSNtSvc.exe.config**, for **BTSNtSvc.exe**.</span></span> <span data-ttu-id="ef5e8-119">構成ファイルは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のインストール パスに含まれています。</span><span class="sxs-lookup"><span data-stu-id="ef5e8-119">The configuration file can be found in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation path.</span></span> <span data-ttu-id="ef5e8-120">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を既定の場所にインストールした場合、BtsNtSvc.exe はディレクトリ [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] に含まれています。</span><span class="sxs-lookup"><span data-stu-id="ef5e8-120">If you installed [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to the default location, BtsNtSvc.exe will be in the directory [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span></span>  
  
3.  <span data-ttu-id="ef5e8-121">分離 WCF アダプタの場合、変更を WCF メッセージ ログの記録を有効にする、 **Web.config** BizTalk WCF サービス公開ウィザードが Web アプリケーション フォルダに作成されるファイルです。</span><span class="sxs-lookup"><span data-stu-id="ef5e8-121">For the isolated WCF adapters, you can enable WCF message logging by modifying the **Web.config** file that the BizTalk WCF Service Publishing Wizard creates in the Web application folder.</span></span>  
  
4.  <span data-ttu-id="ef5e8-122">変更する**BTSNtSvc.exe.config**または**Web.config**、メモ帳を使用して、構成ファイルを開くおよび次の構成例に示すように、WCF メッセージ ログ記録を構成します。</span><span class="sxs-lookup"><span data-stu-id="ef5e8-122">To modify **BTSNtSvc.exe.config** or **Web.config**, open the configuration file by using Notepad, and then configure WCF message logging, as indicated in the following configuration example:</span></span>  
  
    ```  
    <configuration>  
      <system.serviceModel>  
        <diagnostics>  
          <messageLogging   
               logEntireMessage="true"   
               logMalformedMessages="false"  
               logMessagesAtServiceLevel="true"   
               logMessagesAtTransportLevel="true"  
               maxMessagesToLog="300000"  
               maxSizeOfMessageToLog="200000"   
        />  
        </diagnostics>  
      </system.serviceModel>  
  
      <system.diagnostics>  
        <sources>  
          <source name="System.ServiceModel.MessageLogging">  
            <listeners>  
              <add name="messages"  
              type="System.Diagnostics.XmlWriterTraceListener"  
              initializeData="c:\wcfTrace.e2e" />  
            </listeners>  
          </source>  
        </sources>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
5.  <span data-ttu-id="ef5e8-123">Windows Communication Foundation (WCF) Service Trace Viewer ツールを使用すると、WCF によって記録されたメッセージを分析できます。</span><span class="sxs-lookup"><span data-stu-id="ef5e8-123">You can use the Windows Communication Foundation (WCF) Service Trace Viewer Tool to analyze messages logged by WCF.</span></span> <span data-ttu-id="ef5e8-124">Service Trace Viewer は、Windows Vista の Microsoft Windows ソフトウェア開発キット (SDK) および [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] ランタイム コンポーネントに含まれています。</span><span class="sxs-lookup"><span data-stu-id="ef5e8-124">Service Trace Viewer is included in the Microsoft Windows Software Development Kit (SDK) for Windows Vista and [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] Runtime Components.</span></span> <span data-ttu-id="ef5e8-125">Windows SDK をダウンロードするには、Microsoft ダウンロード センターから[http://go.microsoft.com/fwlink/?LinkID=75636](http://go.microsoft.com/fwlink/?LinkID=75636)です。</span><span class="sxs-lookup"><span data-stu-id="ef5e8-125">You can download the Windows SDK from the Microsoft Download Center at [http://go.microsoft.com/fwlink/?LinkID=75636](http://go.microsoft.com/fwlink/?LinkID=75636).</span></span> <span data-ttu-id="ef5e8-126">詳細については、このツールを使用して、次を参照してください。"サービス トレース ビューアー ツール (SvcTraceViewer.exe)"at [http://go.microsoft.com/fwlink/?LinkId=88991](http://go.microsoft.com/fwlink/?LinkId=88991)です。</span><span class="sxs-lookup"><span data-stu-id="ef5e8-126">For more information about using this tool, see "Service Trace Viewer Tool (SvcTraceViewer.exe)"at [http://go.microsoft.com/fwlink/?LinkId=88991](http://go.microsoft.com/fwlink/?LinkId=88991).</span></span>  
  
### <a name="return-managed-exception-information-to-the-client-in-a-soap-fault-to-ease-debugging"></a><span data-ttu-id="ef5e8-127">マネージ例外情報を SOAP エラーの発生しているクライアントに返してデバッグ処理を軽減する</span><span class="sxs-lookup"><span data-stu-id="ef5e8-127">Return managed exception information to the client in a SOAP fault to ease debugging</span></span>  
  
1.  <span data-ttu-id="ef5e8-128">選択することができます、**例外エラーを含む**オプション標準の WCF 受信場所のデバッグを容易に SOAP エラー内のクライアントにマネージ例外情報を返すにします。</span><span class="sxs-lookup"><span data-stu-id="ef5e8-128">You can select the **Include exception in faults** option for the standard WCF receive location to return managed exception information to the client in SOAP faults to ease debugging.</span></span> <span data-ttu-id="ef5e8-129">次の手順を使用して、**例外エラーを含む**オプション。</span><span class="sxs-lookup"><span data-stu-id="ef5e8-129">Use the following steps to select the **Include exception in faults** option.</span></span>  
  
    1.  <span data-ttu-id="ef5e8-130">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理**、展開**BizTalk グループ**、展開**アプリケーション**、展開**受信場所**標準の WCF アダプターを使用して受信場所を右クリックし、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="ef5e8-130">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Applications**, expand **Receive Locations**, right-click a receive location using a standard WCF adapter, and then click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="ef5e8-131">**受信場所のプロパティ**ダイアログ ボックスで、をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="ef5e8-131">In the **Receive Location Properties** dialog box, click **Configure**.</span></span>  
  
    3.  <span data-ttu-id="ef5e8-132">トランスポートのダイアログ ボックスで、**メッセージ**] タブで、[、**例外エラーを含む**オプション。</span><span class="sxs-lookup"><span data-stu-id="ef5e8-132">In the transport dialog box, on the **Messages** tab, select the **Include exception in faults** option.</span></span>  
  
2.  <span data-ttu-id="ef5e8-133">Wcf-custom または Wcf-customisolated アダプターを使用する場合は、設定、 **IncludeExceptionDetailInFaults**のプロパティ、 [ServiceDebugElement](http://go.microsoft.com/fwlink/?LinkId=89004)にマネージ例外情報を返すため、クライアントです。</span><span class="sxs-lookup"><span data-stu-id="ef5e8-133">If you use the WCF-Custom or the WCF-CustomIsolated adapter, you can set the **IncludeExceptionDetailInFaults** property of the [ServiceDebugElement](http://go.microsoft.com/fwlink/?LinkId=89004) to return managed exception information to the client.</span></span> <span data-ttu-id="ef5e8-134">そのためには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="ef5e8-134">To do so, use the following steps:</span></span>  
  
    1.  <span data-ttu-id="ef5e8-135">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理**、展開**BizTalk グループ**、展開**アプリケーション**、展開**受信場所**Wcf-custom または Wcf-customisolated アダプターを使用して受信場所を右クリックし、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="ef5e8-135">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Applications**, expand **Receive Locations**, right-click a receive location using the WCF-Custom or the WCF-CustomIsolated adapter, and then click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="ef5e8-136">**受信場所のプロパティ**ダイアログ ボックスで、をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="ef5e8-136">In the **Receive Location Properties** dialog box, click **Configure**.</span></span>  
  
    3.  <span data-ttu-id="ef5e8-137">トランスポートのダイアログ ボックスで、**動作** タブで、右クリックし、 **ServiceBehavior**ノードをクリックして**拡張機能を追加**です。</span><span class="sxs-lookup"><span data-stu-id="ef5e8-137">In the transport dialog box, on the **Behavior** tab, right-click the **ServiceBehavior** node, and then click **Add extension**.</span></span>  
  
    4.  <span data-ttu-id="ef5e8-138">**動作拡張機能**ダイアログ ボックスで、 **serviceDebug**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="ef5e8-138">In the **Select Behavior Extension** dialog box, select **serviceDebug**, and then click **OK**.</span></span>  
  
    5.  <span data-ttu-id="ef5e8-139">トランスポートのダイアログ ボックスで、**動作** タブで、をクリックして、 **serviceDebug**ノードをクリックして**True**の**includeexceptiondetail**プロパティに、**構成**ビューを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="ef5e8-139">In the transport dialog box, on the **Behavior** tab, click the **serviceDebug** node, and then select **True** for the **includeExceptionDetail** property in the **Configuration** list view.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ef5e8-140">マネージ例外情報をクライアントに返すと、セキュリティが脅かされるおそれがあります。これは、例外の詳細によって内部サービスの実装に関する情報が公開され、それが未承認のクライアントに利用される場合があるためです。</span><span class="sxs-lookup"><span data-stu-id="ef5e8-140">Returning managed exception information to clients can be a security risk because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef5e8-141">参照</span><span class="sxs-lookup"><span data-stu-id="ef5e8-141">See Also</span></span>  
 <span data-ttu-id="ef5e8-142">[トラブルシューティングで使用するツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span><span class="sxs-lookup"><span data-stu-id="ef5e8-142">[Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span></span>  
 <span data-ttu-id="ef5e8-143">[WCF アダプターのトラブルシューティング](../core/troubleshooting-the-wcf-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="ef5e8-143">[Troubleshooting the WCF Adapters](../core/troubleshooting-the-wcf-adapters.md) </span></span>  
 [<span data-ttu-id="ef5e8-144">BTSNTSvc.exe.config ファイル</span><span class="sxs-lookup"><span data-stu-id="ef5e8-144">BTSNTSvc.exe.config File</span></span>](../core/btsntsvc-exe-config-file.md)