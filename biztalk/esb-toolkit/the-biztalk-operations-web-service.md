---
title: "Web サービスの BizTalk 操作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: af38815f-f643-4598-9148-6499071d12e4
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d09fb2cdcca83e8a9f2e4e7704178d40a915065
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-biztalk-operations-web-service"></a>操作で BizTalk Web サービス
Microsoft BizTalk Operations Web サービスでは、オブジェクトおよび BizTalk Server でメッセージに関する情報を公開します。 サービス名は**ESB.BizTalkOperationsService**、し、サービスは、さまざまなホスト、オーケストレーション、アプリケーション、および BizTalk アプリケーションの状態のリストなどの項目を返すメソッドを公開します。  
  
 次の方法があります。  
  
-   **アプリケーション**です。 このメソッドは、パラメーターをとらないし、のコレクションとしてインストールされているすべての BizTalk アプリケーションの説明と名前を返します**BTApplication**オブジェクト。  
  
-   **ApplicationStatus**です。 このメソッドは、パラメーターとして、アプリケーション名、およびとして指定した BizTalk アプリケーションについての情報を返します、 **BTSysStatus**インスタンス。 この情報には、オーケストレーション、送信ポート、受信場所、およびホストの詳細。  
  
-   **GetLiveMessageBody**です。 このメソッドは、パラメーターとして、メッセージ ID とインスタンス ID、およびとして実際の環境からそのメッセージの本文を返します、 **BTMsgBody**インスタンス。  
  
-   **GetMessageInstances**です。 このメソッドは、パラメーターとして、メッセージの種類と一致するすべてのメッセージのコレクションとして返します**BTMsgInstance**オブジェクト。  
  
-   **GetOrchestrationInstances**です。 このメソッドは、パラメーターとして、オーケストレーションの名前のコレクションを返します**BTOrchestrationInstance**一致するオーケストレーションの詳細が含まれているオブジェクト。  
  
-   **GetTrackedMessageBody**です。 このメソッドは、パラメーターとしてメッセージの GUID、および」というメッセージの本文が返されます、 **BTMsgBody** BizTalk で処理された後のインスタンスします。  
  
-   **ホスト**です。 このメソッドは、パラメーターとして、ホストの名前と、指定したホスト インスタンスに関する情報のコレクションとして返します**BTHost**インスタンス。 すべてのホスト インスタンスに関する情報を返すには、ホスト名のパラメーターに空の文字列を使用します。  
  
-   **MessageFlowTree**です。 このメソッドは、パラメーターとしてインスタンス ID、および」というメッセージのメッセージ フローの詳細を返します、 **RouteTreeNode**インスタンス。  
  
-   **オーケストレーション**です。 このメソッドは、パラメーターとして、オーケストレーションの名前とそのオーケストレーションとしてのすべての情報を返します、 **BTSysStatus**インスタンス。 すべてのオーケストレーションに関する情報を返すには、オーケストレーションの name パラメーターに空の文字列を使用します。  
  
-   **ReceiveLocations**です。 このメソッドは、パラメーターとして、受信場所の名前と一致するように場所のすべての情報を返します、 **BTSysStatus**インスタンス。 すべての場所に関する情報を返すには、受信場所の name パラメーターに空の文字列を使用します。  
  
-   **ReceiveLocationsByDescription**です。 このメソッドは、パラメーターとして、受信場所の説明と一致するように場所のすべての情報を返します、 **BTSysStatus**インスタンス。 すべての場所に関する情報を返す description パラメーターに空の文字列を使用します。  
  
-   **SendPorts**です。 このメソッドは、パラメーターとして、送信ポートの名前とポートを照合するすべての情報を返します、 **BTSysStatus**インスタンス。 すべてのポートに関する情報を返すには、送信ポートの name パラメーターに空の文字列を使用します。  
  
-   **SendPortsByDescription**です。 このメソッドは、パラメーターとして、送信ポートの説明ととしてポートを一致させるためのすべての情報を返します、 **BTSysStatus**インスタンス。 すべてのポートに関する情報を返す description パラメーターに空の文字列を使用します。  
  
-   **メイル**です。 このメソッドは、パラメーターとしてタイムスタンプ、およびとして指定したタイムスタンプ以降に変更 (ポート、ホスト、およびオーケストレーション) などの BizTalk オブジェクトの詳細を返します、 **BTSysStatus**インスタンス。  
  
-   **SystemStatus**です。 このメソッドは、パラメーターをとらないし、BizTalk システムの状態の完全な詳細情報を返します、 **BTSysStatus**インスタンス。  
  
-   **UpdateReceiveLocationDescription**です。 このメソッドは、アプリケーション名、受信ポート名、受信場所の名前、および受信場所の説明が含まれているパラメーター値を使用して、指定した受信場所の説明を更新します。 操作の結果を示す文字列を返します。 クライアント テスト アプリケーションが、App.config ファイルからこの情報を読み取ることに注意してください。  
  
-   **UpdateSendPortDescription**です。 このメソッドは、送信ポートの名前と送信ポートの説明が含まれているパラメーター値を使用して、指定された送信ポートの説明を更新します。 操作の結果を示す文字列を返します。 クライアント テスト アプリケーションが、App.config ファイルからこの情報を読み取ることに注意してください。  
  
## <a name="configuring-the-biztalk-operations-web-service"></a>操作で BizTalk Web サービスを構成します。  
 BizTalk Operations Web サービスが Windows Management Instrumentation (WMI) を使用して、BizTalk Server 管理データベースと直接通信するか、または必要な情報を取得する BizTalk 操作およびエクスプ ローラー API を使用します。 そのため、システムが、次の条件を満たしていると、次のセキュリティ アクセス許可の設定を構成することを確認する必要があります。  
  
-   設定、 **allowOverride**をコンピューター レベルの Web.config ファイルで属性**false**開発者は各自のアプリケーションの信頼レベルを変更できないかどうかを確認します。  
  
-   既定では、BizTalk Operations Web サービスは (SSL) クライアントによってアクセスされたときに要求するように構成されていません。 クライアント アクセス用の SSL が要求されるようにサービスを構成し、インターネット インフォメーション サービス (IIS) Web サービスのホスト コンピューターと、BizTalkMgmtDb を使用してデータベースをホストする SQL Server を実行しているコンピューター間の接続を保護する必要があります。ネットワーク レベルの IPSec および適切なファイル レベルのアクセス制御リスト (ACL) のアクセス許可。  
  
-   BizTalk Operations Web サービスにアクセスするユーザーは、いくつかのメソッドの既定の BizTalk Server 管理者グループのメンバーとその他のメソッドの既定の BizTalk Application Users グループのメンバーにする必要があります。  
  
-   BizTalk Operations Web サービスが無効になっている匿名のアクセス権を持つ ESB.BizTalkOperationsService をという名前の IIS 仮想ディレクトリに格納されていることを確認する必要があります。  
  
-   ユーザーがいる必要があります**選択**BizTalkMgmtDb データベースと、BizTalkMsgBoxDb データベースに複数のテーブルの SQL Server のアクセス許可があります。 SQL Server Management Studio を使用すると、次のアクセス許可を設定します。  
  
    -   BizTalkMgmtDb データベース内の BTS_ADMIN_USERS データベース ロールを構成する**選択**次のテーブルに対する権限。  
  
        -   adm_Server2HostMapping  
  
        -   adm_Server  
  
        -   adm_hostInstance  
  
    -   BizTalkMsgBoxDb データベースの構成を持つ BTS_ADMIN_USER データベース ロール**選択**ProcessHeartbeats テーブルに対する権限。  
  
 SQL Server Management Studio では、必要なアクセス許可を構成できます。 これを行うには、次のように展開します**セキュリティ**、左側のウィンドウのツリー ビューでオブジェクト エクスプ ローラー、展開**ロール**、展開**DatabaseRoles**、BTS_ADMIN_USERS ロールを選択し、編集、。図 1 に示すように、このロールのプロパティです。  
  
 ![SQL Server 管理 Studio](../esb-toolkit/media/ch4-sqlservermgmtstudio.gif "Ch4 SQLServerMgmtStudio")  
  
 **図 1**  
  
 **Microsoft SQL Server Management Studio での BTS_ADMIN_USERS データベース ロールの権限の編集**  
  
> [!NOTE]
>  Windows 統合セキュリティを使用して組み込みの NETWORK SERVICE アカウントで実行するには、このサービスを構成する必要があります。 必要がありますも有効にする Kerberos 認証、IIS Web サーバーでヘッダーを送信できるように**ネゴシエート、NTLM**クライアントにします。 詳細については、次を参照してください。[ネットワークの認証に Kerberos プロトコルと NTLM プロトコルの両方をサポートするために IIS を構成する方法](http://go.microsoft.com/fwlink/?LinkId=186430)([http://go.microsoft.com/fwlink/?LinkId=186430](http://go.microsoft.com/fwlink/?LinkId=186430))。  
>   
>  既定では、BizTalk Operations Web サービスはクライアントからアクセス時に SSL を要求するように構成されていません。 クライアント アクセス用の SSL が要求されるようにサービスを構成し、IIS Web サービスのホスト コンピューターとネットワーク レベルの IPSec およびファイル レベル ACL の適切なアクセス許可を使用して、UDDI サービスをホストするサーバー間の接続を保護する必要があります。