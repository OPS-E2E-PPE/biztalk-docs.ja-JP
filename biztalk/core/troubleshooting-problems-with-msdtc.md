---
title: MSDTC の問題のトラブルシューティング |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f39cde52-da8f-4cc1-bdc5-e4b828891a79
caps.latest.revision: 36
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c244ec27cd3e584f7fb22a34effeaf0033c3e78a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22280506"
---
# <a name="troubleshooting-problems-with-msdtc"></a>MSDTC を使用した問題のトラブルシューティング
多くの BizTalk Server ランタイム操作では、トランザクション上でランタイム操作の一貫性を維持するために、Microsoft 分散トランザクション コーディネーター (MSDTC) のサポートが必要です。 MSDTC のトランザクション サポートを使用できないと、それに関連付けられた BizTalk Server ランタイム操作を続行できません。 MSDTC トランザクション サポートが正しく構成されていない場合に一般的に影響を受ける BizTalk のコンポーネントには、シングル サインオン サービス、BizTalk ホスト インスタンス、および BizTalk Server に接続されているすべての SQL Server のインスタンスが含まれますが、これに限定されません。 このセクションには、MSDTC に関連するエラーと、MSDTC の問題を診断および解決するために従う手順について説明する情報が含まれています。  
  
## <a name="errors-that-can-occur-if-msdtc-transaction-support-is-not-configured-correctly"></a>MSDTC トランザクション サポートが正しく構成されていない場合に発生する可能性があるエラー  
 BizTalk 環境のコンピューターで MSDTC トランザクション サポートが正しく構成されていない場合、BizTalk Server で次のようなエラーが発生する可能性があります。  
  
-   "A Microsoft Distributed Transaction Coordinator problem prevented connection to the Configuration database. The transaction manager has disabled its support for remote/network transactions."  
  
-   "A Microsoft Distributed Transaction Coordinator problem prevented connection to the Configuration database. The transaction has already been implicitly or explicitly committed or aborted".  
  
-   "Error Code: 0x8004d00a, New transaction cannot enlist in the specified transaction coordinator".  
  
-   "構成ストアからの受信場所 'MySample ReceiveLocation' に対して、トランスポートの種類のデータを取得できませんでした。 プライマリ SSO サーバー 'MyServer' が失敗しました。 The RPC server is unavailable."  
  
-   "Error Code: 0x8004d025, The partner transaction manager has disabled its support for remote/network transactions".  
  
-   "Error Code: 0xc0002a24, Could not import a DTC transaction. Please check that MSDTC is configured correctly for remote operation."  
  
-   "0x8004d01c  
  
     [0x1705] 内部作業項目の作成時にエラーが発生しました。  
  
     SQL Server が実行されているか確認してください。"  
  
 MSDTC の構成エラーを解決するには、次の手順に従います。  
  
## <a name="ensure-netbios-name-resolution-between-the-biztalk-server-and-remote-servers-is-successful"></a>BizTalk Server とリモート サーバーの間で NetBIOS 名前解決が正常に行われたことを確認する  
 コンピューター間で MSDTC トランザクションを正常に実行するには、クライアント コンピューターでサーバー コンピューターの NetBIOS 名を正しい IP アドレスに解決できること、およびサーバー コンピューターでクライアント コンピューターの NetBIOS 名を正しい IP アドレスに解決できることが必要です。 双方向 (クライアントからサーバーに対して、およびサーバーからクライアントに対して) で NetBIOS 名前解決が機能することを確認するには、次の手順を実行します。  
  
> [!NOTE]
>  NetBIOS 名も一般に呼ば、**ネットワーク**名。  
  
1.  各コンピューターの NetBIOS 名を特定します。  
  
    1.  右クリック**マイ コンピューター**を表示する、**システム プロパティ**ダイアログとクリック、**コンピューター名**タブに表示、**フル コンピューター名**、コンピューターに割り当てられます。  
  
    2.  NetBIOS 名が、として指定した名前の最初の部分、**フル コンピューター名**たとえば場合、**フル コンピューター名**myserver.company.domain.com 後の NetBIOS 名と表示されている、コンピューターが**myserver**です。  
  
2.  次のようにして、IP アドレスまたは各コンピューターに関連付けられたアドレスを特定します。  
  
    1.  クライアント コンピューターでコマンド プロンプトを起動して次のコマンドを入力し、Enter キーを押します。  
  
        ```  
        ipconfig /all  
        ```  
  
    2.  IP アドレスまたはコンピューターに関連付けられたアドレスがコマンド プロンプト ウィンドウに表示されます。  
  
    3.  サーバー コンピューターでコマンド プロンプトを起動して次のコマンドを入力し、Enter キーを押します。  
  
        ```  
        ipconfig /all  
        ```  
  
    4.  IP アドレスまたはサーバー コンピューターに関連付けられたアドレスがコマンド プロンプト ウィンドウに表示されます。  
  
3.  各コンピューターの NetBIOS 名が、コンピューターに関連付けられている IP アドレスのいずれかに解決されることを確認します。  
  
    1.  クライアント コンピューターでコマンド プロンプトを起動して次のコマンドを入力し、Enter キーを押します。  
  
        ```  
        ping <NetBIOS name of server computer>  
        ```  
  
         ping コマンドの結果として、サーバー コンピューターに関連付けられた IP アドレスが返されます。  
  
    2.  サーバー コンピューターでコマンド プロンプトを起動して次のコマンドを入力し、Enter キーを押します。  
  
        ```  
        ping <NetBIOS name of client computer>  
        ```  
  
         ping コマンドの結果として、クライアント コンピューターに関連付けられた IP アドレスが返されます。  
  
4.  各コンピューターの NetBIOS 名に関連付けられている IP アドレスの逆引き名前参照が正しいコンピューター名に解決されることを確認します。  
  
    1.  クライアント コンピューターでコマンド プロンプトを起動して次のコマンドを入力し、Enter キーを押します。  
  
        ```  
        ping -a <IP Address associated with client computer NetBIOS name>  
        ```  
  
         ping コマンドの結果として、NetBIOS 名または手順 3a. で使用した NetBIOS 名に対応する完全修飾ドメイン名が返されます。 返された名前が手順 3a. で使用した NetBIOS 名に一致しないか対応しない場合は、IP アドレスの逆引き参照は失敗し、その結果、MSDTC トランザクションがエラーになります。  
  
    2.  サーバー コンピューターでコマンド プロンプトを起動して次のコマンドを入力し、Enter キーを押します。  
  
        ```  
        ping -a <IP Address associated with server computer NetBIOS name>  
        ```  
  
         ping コマンドの結果として、NetBIOS 名または手順 3b. で使用した NetBIOS 名に対応する完全修飾ドメイン名が返されます。 返された名前が手順 3b. で使用した NetBIOS 名に一致しないか対応しない場合は、IP アドレスの逆引き参照は失敗し、その結果、MSDTC トランザクションがエラーになります。  
  
 NetBIOS 名前解決がいずれかの方向で失敗するか、逆引き名前参照が失敗する場合、DNS サーバー、NetBIOS ネーム サーバー、HOSTS ファイル、または LMHOSTS ファイルに適切なエントリを作成して問題を解決します。  
  
> [!NOTE]
>  コンピューターで使用される名前解決の方法は、コンピューターの NetBIOS ノードの型によって異なります。 NetBIOS ノードの種類の詳細については、次を参照してください。 [NetBIOS 名前解決](http://go.microsoft.com/fwlink/?LinkId=201638)です。  
  
## <a name="ensure-that-a-firewall-between-the-biztalk-server-and-remote-servers-is-not-blocking-ports-required-for-rpc-dynamic-port-allocation"></a>BizTalk Server とリモート サーバー間のファイアウォールによって、RPC 動的ポート割り当てに必要なポートがブロックされていないことを確認する  
 ネットワーク経由の MSDTC 機能は、ネットワーク経由の RPC 機能に依存します。 ファイアウォールを介した RPC 機能では、RPC の動的ポート割り当てに対応するために特定のポートが開かれていることが必要です。 BizTalk Server とリモート サーバーの間にファイアウォールがある場合の手順に従います[ファイアウォールで動作する RPC 動的ポート割り当てを構成する方法](http://go.microsoft.com/fwlink/?LinkId=66831)RPC 動的ポート割り当てに合わせてです。  
  
## <a name="set-the-appropriate-msdtc-security-configuration-options"></a>適切な MSDTC セキュリティ構成オプションの設定  
 Windows のセキュリティ強化により、ネットワーク経由での MSDTC へのアクセス方法を制御できるようになりました。 MSDTC のセキュリティ設定を変更することにより、MSDTC とリモート コンピューター間のネットワーク経由の通信を制御できます。 次の表に、MSDTC のセキュリティ設定の構成時に使用できるオプションの推奨値を示します。  
  
|構成オプション|既定値|推奨値|  
|--------------------------|-------------------|-----------------------|  
|ネットワーク DTC アクセス|Disabled|有効|  
|**クライアントと管理**|||  
|リモート クライアントを許可する|Disabled|Disabled|  
|リモート管理を許可する|Disabled|Disabled|  
|**トランザクション マネージャー通信**|||  
|受信を許可する|Disabled|有効|  
|送信を許可する|Disabled|有効|  
|相互認証を必要とする|有効|すべてのリモート コンピューターで Windows Server 2003 SP1 または Windows XP SP2 以降が実行され、"相互認証を必要とする" を指定して構成されている場合は有効|  
|着信呼び出し側には認証を必要とする|Disabled|クラスター上で MSDTC を実行している場合は、有効|  
|認証を必要としない|Disabled|リモート コンピューターで Windows Server 2003 SP1 または XP SP2 より前の OS を実行している場合は、有効|  
|トランザクション インターネット プロトコル (TIP) を有効にする|Disabled|BAM ポータルを実行している場合に有効になります。|  
|XA トランザクションを有効にする|Disabled|MQSeries アダプターを使用して IBM WebSphere MQ と通信する場合など、XA ベースのトランザクション システムと通信する場合に有効になります。|  
  
 これらの変更を適用した後で、MSDTC サービスが再起動されます。  
  
 MSDTC セキュリティ構成オプションにアクセスするには、次の手順を実行します。  
  
1.  をクリックして**開始**、 をクリックして**実行**、および種類**dcomcnfg**を起動する、**コンポーネント サービス**管理コンソールです。  
  
2.  クリックして展開**コンポーネント サービス**をクリックして展開**コンピューター**です。  
  
3.  クリックして展開**マイ コンピューター**をクリックして展開**分散トランザクション コーディネーター**を右クリックして**ローカル DTC**、 をクリック**プロパティ**.  
  
4.  クリックして、**セキュリティ**のタブ、**ローカル DTC のプロパティ**ダイアログ。  
  
> [!NOTE]
>  変更内容によっては、変更を反映するためにコンピューターの再起動が必要となる場合があります。 変更を適用して MSDTC サービスを再起動しても問題が解消しない場合は、変更を行ったコンピューターを再起動して、確実に変更が有効になるようにします。  
  
 どちらの場合、**相互認証を必要**または**着信呼び出し側には認証を必要**構成オプションが有効にし、クライアント コンピューターのアカウントを付与する必要があります、 **ネットワークからこのコンピューターにアクセス**ユーザー権限。 クライアント コンピューターのコンピューター アカウントが許可されていないかどうか、**ネットワークからこのコンピューターにアクセス**ユーザー権利をかに含まれて、**ネットワークからこのコンピューターへのアクセスを拒否**ユーザー権利をし、DTCクライアントとサーバーのコンピューター間の通信は失敗します。  
  
 既定の設定は、Everyone グループに与えるには、**ネットワークからこのコンピューターにアクセス**ユーザー権限。 したがって、既定の設定が変更されていない限り、このユーザー権限を変更する必要はありません。 場合、**認証を必要としない**構成オプションが有効になっている、**ネットワークからこのコンピューターにアクセス**ユーザー権利は、クライアント コンピューターのアカウントには適用されません。  
  
 "ネットワーク経由でコンピューターへアクセス" ユーザー権限を付与されるユーザーまたはグループを変更するには、次の手順を実行します。  
  
1.  をクリックして**開始**、 をクリックして**実行**、型**Gpedit.msc**、順にクリック**ok**です。  
  
2.  ローカル コンピューターのポリシー一覧で次の項目を展開します。  
  
    -   コンピューターの構成  
  
    -   Windows の設定  
  
    -   セキュリティ設定  
  
    -   ローカル ポリシー  
  
3.  をクリックして**ユーザー権利の割り当て**です。  
  
4.  ダブルクリックして**ネットワークからこのコンピューターにアクセス**、クリックして**ユーザーまたはグループ**です。  
  
5.  をクリックして**オブジェクトの種類**を選択**コンピューター**  をクリック**OK**です。  
  
6.  コンピューター名またはグループ名を追加、**を選択するオブジェクト名の入力**領域。  
  
7.  をクリックして**名前の確認**エントリを確認します。  
  
8.  **[OK]** を 2 回クリックします。  
  
 ユーザーまたはグループに含まれている変更を**ネットワークからこのコンピューターへのアクセスを拒否**ユーザー権利をこれらの手順に従います。  
  
1.  ローカル コンピューターのポリシー一覧で次の項目を展開します。  
  
    -   コンピューターの構成  
  
    -   Windows の設定  
  
    -   セキュリティ設定  
  
    -   ローカル ポリシー  
  
2.  をクリックして**ユーザー権利の割り当て**です。  
  
3.  ダブルクリックして **、ネットワーク経由でコンピューターのアクセスを拒否**コンピューター名またはこのユーザー権限から削除するグループを選択し をクリックします。  
  
4.  をクリックして**削除** をクリックし、 **OK**です。  
  
## <a name="set-the-appropriate-values-for-the-enableauthepresolution-and-restrictremoteclients-options"></a>EnableAuthEpResolution オプションと RestrictRemoteClients オプションに、適切な値を設定します。  
 Windows のセキュリティ強化により、RPC インターフェイスへは必ず認証された呼び出しを行う必要があります。 この機能は、使用して構成できます、 **EnableAuthEpResolution**と**RestrictRemoteClients**レジストリ キー。 リモート コンピューターが RPC インターフェイスにアクセスできるように、次の手順を実行します。  
  
> [!WARNING]
>  レジストリ エディターの不適切な使用により問題が発生し、オペレーティング システムの再インストールが必要となることがあります。 レジストリ エディターは、ご自身の責任で使用してください。 バックアップ、復元、およびレジストリを変更する方法の詳細についてで Microsoft サポート技術情報の資料「Microsoft Windows レジストリの説明」を参照してください。 [Microsoft Windows レジストリの説明](http://go.microsoft.com/fwlink/?LinkId=62729)です。  
  
1.  をクリックして**開始**、 をクリックして**実行**、型**regedit.exe**、順にクリック**ok**レジストリ エディターを起動します。  
  
     移動**\software\policies\microsoft\windows NT**  
  
2.  下にある、 **RPC**キーを指定された値を使用して、次の DWORD エントリを作成します。 場合、 **RPC**キーが存在しないし、作成する必要があります。  
  
    |DWORD エントリ|既定値|推奨値|  
    |-----------------|-------------------|-----------------------|  
    |EnableAuthEpResolution|0 (無効)|1|  
    |RestrictRemoteClients|1 (有効)|0|  
  
3.  レジストリ エディターを閉じます。  
  
4.  MSDTC サービスを再起動します。  
  
> [!NOTE]
>  変更内容によっては、変更を反映するためにコンピューターの再起動が必要となる場合があります。 変更を適用して MSDTC サービスを再起動しても問題が解消しない場合は、変更を行ったコンピューターを再起動して、確実に変更が有効になるようにします。  
  
## <a name="if-windows-firewall-is-running-add-an-exception-for-the-msdtc-service"></a>Windows ファイアウォールが実行中の場合は、MSDTC サービスの例外を追加します。  
 Windows ファイアウォール サービスが、コンピューター間の MSDTC 通信をブロックする場合があります。 Windows ファイアウォールが稼働している場合にコンピューター間で MSDTC 通信がブロックされないようにするには、Windows ファイアウォールの例外リストに msdtc.exe を追加します。  
  
1.  をクリックして**開始**、 をクリックして**実行**、型**firewall.cpl**、順にクリック**ok**を表示する、 **Windows ファイアウォール**  ダイアログ ボックス。  
  
2.  をクリックして**Windows ファイアウォールによるプログラムの許可**を表示する、 **Windows ファイアウォールの設定** ダイアログ ボックス。  
  
3.  クリックして、**例外**のタブ、 **Windows ファイアウォールの設定** ダイアログ ボックス。  
  
4.  をクリックして**プログラムの追加**を表示する、**プログラムの追加** ダイアログ ボックス。  
  
5.  をクリックして**参照**に移動して *%system32*\msdtc.exe です。  
  
    > [!NOTE]
    >  コマンド プロンプト ウィンドウで「を起動して**echo system32%** とキーを押します**Enter**このコンピューター上の \System32 ディレクトリの場所を決定します。  
  
6.  クリックして選択**msdtc.exe**  をクリック**開く**です。  
  
7.  をクリックして**スコープを変更する**MSDTC の通信を許可するをクリックしてコンピューターのセットを指定する**OK**です。  
  
8.  をクリックして**OK**で、**プログラムの追加** ダイアログ ボックスをクリック**ok**で、 **Windows ファイアウォールの設定** ダイアログ ボックス。  
  
9. 閉じる、 **Windows ファイアウォール** ダイアログ ボックス。  
  
10. 分散トランザクション コーディネーター サービスを停止して再起動します。  
  
    -   コマンド プロンプト ウィンドウで「を起動して**net stop msdtc**とキーを押します**Enter**です。  
  
    -   分散トランザクション コーディネーター サービスが停止したら、入力**net msdtc を開始する**とキーを押します**Enter**です。  
  
## <a name="use-dtctester-or-dtcping-to-verify-msdtc-functionality-over-the-network"></a>DTCTester または DTCPing を使用して、ネットワーク上で MSDTC 機能を確認する  
 2 台のコンピューターのうちの 1 台に SQL Server がインストールされている場合は、DTCTester ユーティリティを使用してそれらのコンピューター間のトランザクション サポートを確認します。 DTCTester ユーティリティでは、ODBC を使用して SQL Server データベースのトランザクション サポートを確認します。 DTCTester の詳細については、次を参照してください。 [DTCTester ツールを使用する方法](http://go.microsoft.com/fwlink/?LinkId=66232)です。  
  
 2 台のコンピューターのどちらにも SQL Server がインストールされていない場合は、DTCPing を使用してそれらのコンピューター間のトランザクション サポートを確認します。 DTCPing ツールは、クライアント コンピューターとサーバー コンピューターの両方で実行する必要があります。いずれのコンピューターにも SQL Server がインストールされていない場合は、DTCTester ユーティリティの適切な代替手段になります。 DTCPing の詳細については、次を参照してください。 [MS DTC ファイアウォールの問題のトラブルシューティング方法](http://go.microsoft.com/fwlink/?LinkId=61915)です。  
  
> [!IMPORTANT]
>  DTCPing が、警告を返す場合を"警告: 両方のテスト コンピューターの CID 値が同じ"し、セクションの手順に従います**MSDTC に一意の CID 値が割り当てられるように**間で MSDTC が正しく機能に合わせてテスト マシン。  
  
## <a name="ensure-that-msdtc-is-assigned-a-unique-cid-value"></a>MSDTC に一意の CID 値が割り当てられていることを確認する  
 Windows オペレーティング システムの MSDTC 機能がコンピューター間で正しく動作するには、一意の CID 値が必要です。 Windows インストールのディスクの重複イメージには一意の CID 値が必要です。この値がないと、MSDTC 機能が損なわれる可能性があります。 この状況は、仮想ハード ディスクを使用して仮想マシンにオペレーティング システムを配置した場合に発生します。  
  
 Windows オペレーティング システムを実行しているコンピューターの MSDTC CID 値が一意かどうかを判定するには、両方のコンピューター上で、HKEY_CLASSES_ROOT\CID レジストリ キーの下のエントリの値を調べます。 これらの値が各コンピューターに対して一意でない場合の手順を実行しに従う**他のトラブルシューティングの手順に失敗した場合、分散トランザクション コーディネーター サービスを再インストールを検討してください**を 1 つで MSDTC を再インストールするにはコンピューターをそのコンピューターの一意の MSDTC CID 値を生成し、MSDTC が正しく動作に対応します。  
  
## <a name="error-new-transaction-cannot-enlist-in-the-specified-transaction-coordinator-0x8004d00a-occurs-if-the-msdtc-connection-between-a-client-computer-and-a-server-computer-is-closed"></a>"New transaction cannot enlist in the specified transaction coordinator (0x8004d00a)" というエラーの発生 (クライアント コンピューターとサーバー コンピューターの間の MSDTC 接続が閉じられた場合)  
 特定のシナリオでは、クライアントとサーバー間の既存の MSDTC 接続が閉じられると、後続のこの接続を使用すると、次のエラー メッセージ。  
新しいトランザクションが、指定されたトランザクション コーディネーター (0x8004d00a) に参加できませんでした。  
詳細については、次を参照してください。 [MS DTC でトランザクションを開始しようとすると、エラー メッセージ:"新しい transaction cannot enlist in the specified transaction coordinator"](http://support.microsoft.com/kb/922430)です。  
  
## <a name="consider-reinstalling-the-distributed-transaction-coordinator-service-if-other-troubleshooting-steps-are-not-successful"></a>その他のトラブルシューティングの手順が正常に実行されない場合は、分散トランザクション コーディネーター サービスの再インストールを検討してください。  
 MSDTC を使用したトラブルシューティングで問題が解決されなかった場合は、MSDTC のアンインストールおよび再インストールを検討してください。 MSDTC のアンインストールおよび再インストールを行うには、次の手順に従います。  
  
1.  管理者としてコマンド プロンプトを開きます。  
  
2.  コマンド プロンプトで、分散トランザクション コーディネーター サービスをアンインストールするには、次を入力します。  
    `msdtc -uninstall`  
  
3.  コマンド プロンプトで、分散トランザクション コーディネーター サービスをインストールするのには、次を入力します。  
    `msdtc –install`  
  
> [!IMPORTANT]
>  MSDTC を再インストールすると、分散トランザクション コーディネーター サービスの既定の動作が変更する可能性があります。 MSDTC の再インストール後に、以下の手順に従って、分散トランザクション コーディネーター サービスが正しく動作することを確認してください。  
>   
>  -   MSDTC を再インストールすると、MSDTC セキュリティ構成オプションが既定値にリセットされることがあります。 MSDTC の再インストール後に、MSDTC セキュリティ構成オプションが適切な値に設定されていることを確認してください。  
> -   MSDTC の再インストールを変更することがあります、**スタートアップの種類**分散トランザクション コーディネーター サービスの値。 いることを確認、**スタートアップの種類**値に設定されている分散トランザクション コーディネータ サービスの**自動**MSDTC を再インストール後にします。  
> -   MSDTC を再インストールするには、コンピューターを再起動する必要がある場合があります。 分散トランザクション コーディネーター サービスを正しく動作させるには、MSDTC の再インストール後にコンピューターを再起動してください。  
  
## <a name="see-also"></a>参照  
 [トラブルシューティングで使用するツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md)   
 [Windows Server クラスターのトラブルシューティング](../core/troubleshooting-a-windows-server-cluster.md)