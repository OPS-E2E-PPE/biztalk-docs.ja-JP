---
title: WCF アダプターに関する問題を診断する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 997a4ecd-6077-45d6-82d3-3f658ca62fd4
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9bcb513704753363e054d689d2409925ffcd483
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995387"
---
# <a name="how-to-diagnose-problems-with-the-wcf-adapters"></a>WCF アダプタに関する問題の診断方法
このセクションでは、WCF アダプタに関する問題の診断手順について説明します。  
  
### <a name="check-the-iis-log-and-httperr-log-of-the-iis-server-for-errors"></a>IIS ログと IIS サーバーのエラーの HTTPERR ログを確認してください。  
  
- ソースまたはターゲットの IIS サーバー ログ ファイルには、WCF 分離アダプタに関する問題のトラブルシューティングに役立つ情報が含まれています。 既定では、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] コンピューターの IIS ログ ファイルは次のディレクトリにあります。  
  
   <em>%Windir%\\</em>system32\LogFiles\W3SVC1\  
  
  > [!NOTE]
  >  *%Windir%* の場所のプレース ホルダー、[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]ディレクトリ、IIS サーバーにします。  
  
   既定では、[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] と [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] ベースのコンピューターの HTTPERR ログ ファイルは次のディレクトリにあります。  
  
  > [!NOTE]
  >  HTTPERR ログ ファイルは、[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] と [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] ベースのコンピューターでのみ使用できます。  
  
   <em>%Windir%\\</em>system32\LogFiles\HTTPERR\  
  
### <a name="use-wcf-message-logging-for-fault-monitoring-and-diagnosis-of-problems-from-the-wcf-adapters"></a>WCF メッセージ ログの記録を WCF アダプタの障害監視と問題の診断に使用する  
  
1. WCF には、受信メッセージと送信メッセージをオフラインで使用するためにログに記録する機能が備わっています。 メッセージ ログを記録すると、WCF アダプタを経由して送受信するメッセージを確認できます。 WCF は既定ではメッセージをログに記録しません。 メッセージ ログの記録をアクティブ化するには、WCF アダプタが使用する構成ファイルを変更する必要があります。 WCF メッセージ ログの詳細についてを参照してください「Message Logging」 [ http://go.microsoft.com/fwlink/?LinkId=89003](http://go.microsoft.com/fwlink/?LinkId=89003)します。  
  
2. インプロセス WCF アダプタでは、アプリケーション構成ファイルを変更することで WCF メッセージ ログをさせることができます**BTSNtSvc.exe.config**の**BTSNtSvc.exe**します。 構成ファイルは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のインストール パスに含まれています。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を既定の場所にインストールした場合、BtsNtSvc.exe はディレクトリ [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] に含まれています。  
  
3. 分離 WCF アダプタでは、変更することで WCF メッセージ ログをさせることができます、 **Web.config** Web アプリケーション フォルダーで、BizTalk WCF サービス公開ウィザードで作成されるファイル。  
  
4. 変更する**BTSNtSvc.exe.config**または**Web.config**メモ帳を使用して、構成ファイルを開き、次の構成例に示すとおり、WCF メッセージ ログ記録を構成します。  
  
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
  
5. Windows Communication Foundation (WCF) Service Trace Viewer ツールを使用すると、WCF によって記録されたメッセージを分析できます。 Service Trace Viewer は、Windows Vista の Microsoft Windows ソフトウェア開発キット (SDK) および [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] ランタイム コンポーネントに含まれています。 Windows SDK をダウンロードするには、Microsoft ダウンロード センターから[ http://go.microsoft.com/fwlink/?LinkID=75636](http://go.microsoft.com/fwlink/?LinkID=75636)します。 詳細については、このツールを使用して、"Service Trace Viewer Tool (SvcTraceViewer.exe)"at [ http://go.microsoft.com/fwlink/?LinkId=88991](http://go.microsoft.com/fwlink/?LinkId=88991)を参照してください。  
  
### <a name="return-managed-exception-information-to-the-client-in-a-soap-fault-to-ease-debugging"></a>マネージド例外情報を SOAP エラーの発生しているクライアントに返してデバッグ処理を軽減する  
  
1. 選択することができます、**例外をエラーに含める**オプションの標準の WCF 受信場所でデバッグを容易にするクライアントに SOAP エラー マネージ例外情報を返すします。 次の手順を使用して、**例外をエラーに含める**オプション。  
  
   1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理**、展開**BizTalk グループ**、展開**アプリケーション**、展開**受信場所**標準の WCF アダプターを使用して受信場所を右クリックし、クリックして**プロパティ**します。  
  
   2. **受信場所のプロパティ**ダイアログ ボックスで、をクリックして**構成**します。  
  
   3. トランスポートのダイアログ ボックスで、上、**メッセージ**] タブで、[、**例外をエラーに含める**オプション。  
  
2. 設定することができます、Wcf-custom または Wcf-customisolated アダプターを使用する場合、 **IncludeExceptionDetailInFaults**のプロパティ、 [ServiceDebugElement](http://go.microsoft.com/fwlink/?LinkId=89004)にマネージ例外情報を返す、クライアント。 そのためには、次の手順に従います。  
  
   1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理**、展開**BizTalk グループ**、展開**アプリケーション**、展開**受信場所**Wcf-custom または Wcf-customisolated アダプターを使用して受信場所を右クリックし、クリックして**プロパティ**します。  
  
   2. **受信場所のプロパティ**ダイアログ ボックスで、をクリックして**構成**します。  
  
   3. トランスポートのダイアログ ボックスでの**動作** タブで、右クリックし、 **ServiceBehavior**ノードをクリック**拡張機能の追加**。  
  
   4. **動作拡張機能の選択**ダイアログ ボックスで、 **serviceDebug**、順にクリックします**OK**します。  
  
   5. トランスポートのダイアログ ボックスでの**動作**タブをクリックし、 **serviceDebug**ノード、および選択し**True**の **[includeexceptiondetail]** プロパティ、**構成**ビューを一覧表示します。  
  
   > [!NOTE]
   >  マネージド例外情報をクライアントに返すと、セキュリティが脅かされるおそれがあります。これは、例外の詳細によって内部サービスの実装に関する情報が公開され、それが未承認のクライアントに利用される場合があるためです。  
  
## <a name="see-also"></a>参照  
 [トラブルシューティングで使用するツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md)   
 [WCF アダプターのトラブルシューティング](../core/troubleshooting-the-wcf-adapters.md)   
 [BTSNTSvc.exe.config ファイル](../core/btsntsvc-exe-config-file.md)