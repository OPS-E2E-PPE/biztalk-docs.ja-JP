---
title: サービスを再起動またはシャット ダウンする手順 |Microsoft Docs
description: 開始、停止、一時停止、再開、または BizTalk Server の再起動のサービスまたは BizTalk Server コンピューターをシャット ダウン
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d6449ba-2892-49c6-a697-847608d10ec5
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85e8c353e4a8fa157352aa62238b107a07831465
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333987"
---
# <a name="restart-biztalk-services-or-shut-down-the-biztalk-server"></a>、BizTalk サービスを再起動またはシャット ダウン、BizTalk Server

次の表に、ユーザーが開始、停止、一時停止、再開、または再起動できる BizTalk Server サービスを示します。  
  
|名前|説明|スタートアップの種類|依存関係|  
|----------|-----------------|------------------|------------------|  
|BizTalk Service BizTalk Group:*\<BizTalkServerApplication\>*|BizTalk Server アプリケーション サービスを提供します。|自動|エンタープライズ シングル サインオン (SSO) サービス<br />イベント ログ<br />-リモート プロシージャ コール (RPC)|  
|エンタープライズ シングル サインオン サービス|エンタープライズ アプリケーションにシングル サインオン サービスを提供します。|自動|ローカルにインストールされる SQL Server の場合<br /><br /> -COM + システム アプリケーション<br />-リモート プロシージャ コール (RPC)<br />SQL Server (MSSQLSERVER)<br /><br /> リモートにインストールされる SQL Server の場合<br /><br /> -COM + システム アプリケーション<br />-リモート プロシージャ コール (RPC) なし|  
|ルール エンジン更新サービス|ポリシーの展開または展開解除について、ユーザーに通知します。|Automatic|なし|  
  
 
## <a name="start-stop-pause-resume-or-restart-a-biztalk-server-service"></a>開始、停止、一時停止、再開、または BizTalk Server サービスを再起動します。  
 ことができます開始、停止、一時停止、再開、または Services.msc、またはコマンド プロンプトを使用して、BizTalk Server サービスを再起動します。

### <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、ローカル コンピューターの Administrators グループに属しているか、適切な権限を委任されている必要があります。 コンピューターがドメインに参加している場合は、Domain Admins グループのメンバーがここで示す手順を実行できます。 セキュリティを高めるために、実行時アカウントを使用することを検討してください。 
  
### <a name="use-services-in-control-panel"></a>コントロール パネルの サービスを使用します。  
  
1.  [サービス] を開きます。 をクリックして**開始**、 をクリックして**実行**、し、入力**services.msc**です。  
  
2.  適切な BizTalk Server サービスを右クリックし、をクリックし、**開始**、**停止**、**一時停止**、**再開**、または**再起動**します。  
  
### <a name="use-a-command-prompt"></a>コマンド プロンプトを使用します。  
  
1.  [スタート] メニューを右クリックして**コマンド プロンプト**を選択します**詳細**、選び**管理者として実行**
  
2.  次のいずれかを入力、 *ServiceName*開始、停止、一時停止、または再開する BizTalk Server サービスの名前を指定します。  
  
    -   サービスを開始するには、次のように入力します。  
  
         **net start** *ServiceName*  
  
    -   サービスを停止するには、次のように入力します。  
  
         **net stop** *ServiceName*  
  
    -   サービスを一時停止するには、次のように入力します。  
  
         **net pause** *ServiceName*  
  
    -   サービスを再開するには、次のように入力します。  
  
         **net 続行** *ServiceName*  

    |BizTalk サービス|ServiceName|  
    |---|---|  
    |BizTalk Service BizTalk Group:BizTalkServerApplication|btssvc$biztalkserverapplication|  
    |エンタープライズ シングル サインオン サービス|Entsso|  
    |ルール エンジン更新サービス|ruleengineupdateservice|
  
## <a name="shut-down-biztalk-server"></a>BizTalk Server をシャット ダウンします。  

### <a name="prerequisites"></a>前提条件  
-   シャット ダウンする BizTalk server のローカルの administrators グループのメンバーであるアカウントでサインインします。 これはサービスを停止するために必要です。  
-   BizTalk Server 管理者グループまたは BizTalk Server Operators グループのメンバーであるアカウントでサインインします。 

### <a name="task-overview"></a>タスクの概要
1. 受信場所を無効にし、アクティブな各アプリケーションの部分停止を実行することによってオーケストレーションと送信ポートを停止します。 アプリケーションの削除または再展開を行う場合は、完全停止を実行する必要があります。 詳細については、次を参照してください。 [BizTalk アプリケーション開始および停止方法](../core/how-to-start-and-stop-a-biztalk-application.md)します。  
  
2. ホスト インスタンスを停止します。 詳細については、次を参照してください。[ホスト インスタンスを停止する方法](../core/how-to-stop-a-host-instance.md)します。  
  
3. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サービスをシャットダウンします。 参照してください**開始、停止、一時停止、再開、または BizTalk Server サービスを再起動する方法**(」を参照)。
  
4. インターネット インフォメーション サービス (IIS) をシャットダウンするか、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーション プールと Web サイトを停止します。 サーバーを完全にシャットダウンする場合は、この手順を省略できます。 メンテナンスまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーションの展開または再展開のために [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を停止する場合は、この手順を実行する必要があります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に関連付けられた Web サイトおよびアプリケーション プールのみを停止した場合、他の IIS 関連プロセスは引き続き実行されます。  
  
    この手順の進め方は、使用している IIS のバージョンにより若干異なります。 IIS 6 では、アプリケーション プールと Web サイトを停止できます。 IIS 6 では、IIS Admin Service を停止して、アプリケーション プールと Web サイトを含むすべての IIS アクティビティをシャットダウンすることもできます。 IIS 7.0 は IIS 6.0 よりもモジュール化が進んでおり、1 つのスイッチですべての IIS 7.0 アクティビティを停止することはできないので、Web サイトとアプリケーション プールを個別に停止する必要があります。  
  
    アプリケーション プールおよび仮想アプリケーション (Web サイトおよび Web サービス) BizTalk Server で使用されるの一覧は、次を参照してください。 [BizTalk Server の構成](../install-and-config-guides/configure-biztalk-server.md)します。  
  
   開始して、IIS アプリケーション プールを停止しています。 詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkID=140513](http://go.microsoft.com/fwlink/?LinkID=140513)します。  
  
   開始して、IIS で Web サーバーを停止する方法については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=140695](http://go.microsoft.com/fwlink/?LinkId=140695)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk アプリケーション開始および停止する方法](../core/how-to-start-and-stop-a-biztalk-application.md)   
 [ホスト インスタンスを停止する方法](../core/how-to-stop-a-host-instance.md)   