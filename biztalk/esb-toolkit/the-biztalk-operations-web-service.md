---
title: BizTalk 操作 Web サービス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af38815f-f643-4598-9148-6499071d12e4
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b9a78dddbbd76566c5c97b1e571e5ad80073d4a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997971"
---
# <a name="the-biztalk-operations-web-service"></a>BizTalk 操作 Web サービス
Microsoft BizTalk 操作 Web サービスは、オブジェクトおよび BizTalk Server のメッセージに関する情報を公開します。 サービス名が**ESB.BizTalkOperationsService**とサービスがさまざまなホスト、オーケストレーション、アプリケーション、および BizTalk アプリケーションの状態の一覧などの項目を返すメソッドを公開します。  
  
 次の方法があります。  
  
-   **アプリケーション**します。 このメソッドは、パラメーターをとらないしのコレクションとしてインストールされているすべての BizTalk アプリケーションの説明と名前を返します**BTApplication**オブジェクト。  
  
-   **ApplicationStatus**します。 このメソッドは、パラメーターとして、アプリケーション名、およびとして指定した BizTalk アプリケーションについての情報が返されます、 **BTSysStatus**インスタンス。 この情報には、オーケストレーション、送信ポート、受信場所、ホストの詳細。  
  
-   **GetLiveMessageBody**します。 このメソッドは、メッセージ ID とインスタンス ID をパラメーターとして受け取ります、として実際の環境からそのメッセージの本文を返します、 **BTMsgBody**インスタンス。  
  
-   **GetMessageInstances**します。 このメソッドは、パラメーターとして、メッセージの種類と一致するすべてのメッセージのコレクションとして返します**BTMsgInstance**オブジェクト。  
  
-   **GetOrchestrationInstances**します。 このメソッドはパラメーターとして、オーケストレーションの名前のコレクションを返します**BTOrchestrationInstance**一致するオーケストレーションの詳細が含まれているオブジェクト。  
  
-   **GetTrackedMessageBody**します。 このメソッドは、パラメーターとしてメッセージの GUID、および、としては、そのメッセージの本文を返します、 **BTMsgBody** BizTalk で処理された後のインスタンスします。  
  
-   **ホスト**します。 このメソッドは、パラメーターとして、ホストの名前のコレクションとして指定したホスト インスタンスに関する情報が返されます**BTHost**インスタンス。 すべてのホスト インスタンスに関する情報を返すには、空の文字列のホスト名のパラメーターを使用します。  
  
-   **MessageFlowTree**します。 このメソッドは、パラメーターとして、インスタンス ID ととしては、そのメッセージのメッセージ フローの詳細を返しますが、 **RouteTreeNode**インスタンス。  
  
-   **オーケストレーション**します。 このメソッドは、パラメーターとして、オーケストレーションの名前ととしてそのオーケストレーションのすべての情報が返されます、 **BTSysStatus**インスタンス。 オーケストレーションの name パラメーターに空の文字列を使用して、すべてのオーケストレーションに関する情報を返します。  
  
-   **ReceiveLocations**します。 このメソッドは、パラメーターとして、受信場所の名前と場所にも一致するすべての情報が返されます、 **BTSysStatus**インスタンス。 すべての場所に関する情報を返すには、受信場所の name パラメーターに空の文字列を使用します。  
  
-   **ReceiveLocationsByDescription**します。 このメソッドは、パラメーターとして、受信場所の説明と場所にも一致するすべての情報が返されます、 **BTSysStatus**インスタンス。 説明パラメーターに空の文字列を使用して、すべての場所に関する情報を返します。  
  
-   **SendPorts**します。 このメソッドは、パラメーターとして、送信ポートの名前とポートと一致するすべての情報が返されます、 **BTSysStatus**インスタンス。 送信ポートの name パラメーターに空の文字列を使用して、すべてのポートに関する情報を返します。  
  
-   **SendPortsByDescription**します。 このメソッドは、パラメーターとして、送信ポートの説明と、ポートと一致するすべての情報が返されます、 **BTSysStatus**インスタンス。 説明パラメーターに空の文字列を使用して、すべてのポートに関する情報を返します。  
  
-   **メイル**します。 このメソッドは、パラメーターとしてタイムスタンプ、およびとして、指定したタイムスタンプ以降に変更 (ポート、ホスト、およびオーケストレーション) などの BizTalk オブジェクトの詳細を返しますが、 **BTSysStatus**インスタンス。  
  
-   **SystemStatus**します。 このメソッドは、パラメーターをとらないし、BizTalk システムの状態の完全な詳細情報を返します、 **BTSysStatus**インスタンス。  
  
-   **UpdateReceiveLocationDescription**します。 このメソッドは、アプリケーション名、受信ポート名、受信場所の名前、および受信場所の説明が含まれているパラメーター値を使用して、指定した受信場所の説明を更新します。 操作の結果を示す文字列を返します。 テスト用クライアント アプリケーションが、App.config ファイルからこの情報を読み取ることに注意してください。  
  
-   **UpdateSendPortDescription**します。 このメソッドは、送信ポートの名前と送信ポートの説明が含まれているパラメーター値を使用して、指定された送信ポートの説明を更新します。 操作の結果を示す文字列を返します。 テスト用クライアント アプリケーションが、App.config ファイルからこの情報を読み取ることに注意してください。  
  
## <a name="configuring-the-biztalk-operations-web-service"></a>BizTalk 操作 Web サービスの構成  
 BizTalk 操作 Web サービスが Windows Management Instrumentation (WMI) を使用して、BizTalk Server 管理データベースと直接通信するか、または必要な情報の取得に BizTalk 操作およびエクスプ ローラーの API を使用します。 そのため、システムが、次の条件を満たしていると、次のセキュリティ アクセス許可の設定を構成することを確認しておく必要があります。  
  
- 設定、 **allowOverride**をコンピューター レベルの Web.config ファイルで属性**false**を開発者がアプリケーションの信頼レベルを変更することはできないかどうかを確認します。  
  
- 既定では、BizTalk 操作 Web サービスはセキュリティで保護の Sockets Layer (SSL) クライアントがアクセスするときに要求するように構成されていません。 クライアント アクセスの SSL が要求されるように、サービスを構成し、インターネット インフォメーション サービス (IIS) Web サービスのホスト コンピューターと、BizTalkMgmtDb データベースを使用してホストする SQL Server を実行しているコンピューター間の接続を保護する必要があります。ネットワーク レベルの IPSec と適切なファイル レベルのアクセス制御リスト (ACL) アクセス許可。  
  
- BizTalk 操作 Web サービスにアクセスするユーザーは、いくつかのメソッドの既定の BizTalk Server 管理者グループのメンバーとその他のメソッドの既定の BizTalk Application Users グループのメンバーである必要があります。  
  
- BizTalk 操作 Web サービスが無効になっている匿名のアクセス権を持つ ESB.BizTalkOperationsService という名前の IIS 仮想ディレクトリに格納されていることを確認する必要があります。  
  
- ユーザーがいる必要があります**選択**BizTalkMgmtDb データベースと BizTalkMsgBoxDb データベース内にある複数のテーブルの SQL Server のアクセス許可。 次のアクセス許可を設定するのにには、SQL Server Management Studio を使用します。  
  
  -   BizTalkMgmtDb データベース内の BTS_ADMIN_USERS データベース ロールを構成する**選択**次のテーブルに対する権限。  
  
      -   adm_Server2HostMapping  
  
      -   adm_Server  
  
      -   adm_hostInstance  
  
  -   BizTalkMsgBoxDb データベース内の構成を持つ BTS_ADMIN_USER データベース ロール**選択**ProcessHeartbeats テーブルに対する権限。  
  
  SQL Server Management studio では、必要なアクセス許可を構成できます。 これを行うには、展開**セキュリティ**オブジェクト エクスプ ローラーの左側のウィンドウのツリー ビューで展開**ロール**、展開**DatabaseRoles**、BTS_ADMIN_USERS ロールを選択し、編集、図 1 に示すように、このロールのプロパティです。  
  
  ![SQL Server 管理 Studio](../esb-toolkit/media/ch4-sqlservermgmtstudio.gif "Ch4 SQLServerMgmtStudio")  
  
  **図 1**  
  
  **Microsoft SQL Server Management Studio での BTS_ADMIN_USERS データベース ロールの編集アクセス許可**  
  
> [!NOTE]
>  Windows 統合セキュリティを使用し、組み込みの NETWORK SERVICE アカウントで実行するには、このサービスを構成する必要があります。 必要がありますも Kerberos 認証を有効に、IIS Web サーバー ヘッダーを送信できるように**Negotiate、NTLM**クライアントにします。 詳細については、次を参照してください。[ネットワーク認証のため、Kerberos プロトコルと NTLM プロトコルの両方をサポートするために IIS を構成する方法](http://go.microsoft.com/fwlink/?LinkId=186430)([http://go.microsoft.com/fwlink/?LinkId=186430](http://go.microsoft.com/fwlink/?LinkId=186430))。  
>   
>  既定では、BizTalk 操作 Web サービスはクライアントによってアクセスされたときに SSL を要求するように構成されていません。 クライアント アクセス用の SSL が要求されるようにサービスを構成し、IIS Web サービスのホスト コンピューターとネットワーク レベルの IPSec と適切なファイル レベルの ACL アクセス許可を使用して UDDI サービスをホストするサーバー間の接続を保護する必要があります。