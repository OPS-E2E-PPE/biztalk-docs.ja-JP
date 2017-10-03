---
title: "MQSAgent COM + 構成ウィザードを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.mqsagent.wizard
helpviewer_keywords:
- MQSeries adapters, MQSAgent COM+ Configuration Wizard
- configuring [MQSeries adapters], MQSAgent COM+ Configuration Wizard
- MQSAgent COM+ Configuration Wizard
ms.assetid: f106700a-7f57-4c83-9344-6525fc10544d
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6262b87f304a27b36ed1d7bc6a15b5e681331be3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-mqsagent-com-configuration-wizard"></a>MQSAgent COM + 構成ウィザードの使用
MQSAgent COM+ 構成ウィザードでは、アダプターの COM+ アプリケーション (MQSeries コンポーネント) 部分である MQSAgent を構成します。 このウィザードでは、コンポーネントのアプリケーション ID、およびロール名とそのロールに含めるユーザーを設定します。 MQSAgent COM + 構成ウィザードを使用して作成される MQSAgent COM + コンポーネントの名前は**MQSAgent2**です。  
  
> [!NOTE]
>  MQSAgent COM+ アプリケーションは、64 ビット版の Windows サーバーでサポートされています。 WOW64 の下で 32 ビット プロセスとして実行されます。 64 ビット版の Windows Server で実行されている [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ベースのコンピューターは、MQSAgent がインストールされているリモートの 32 ビット コンピューターと通信できます。  
  
> [!NOTE]
>  MQSeries エージェントと MQSAgent COM + 構成ウィザードの実行可能ファイル**MQSConfigWiz.exe**に BizTalk Server 2009 からアップグレードする場合はインストールされません[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]です。 アップグレードした後[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]から BizTalk Server 2009 のセットアップを再実行、選択、**変更**オプション、およびこれらのコンポーネントをインストールする追加のソフトウェア [MQSeries エージェント] を選択します。  
  
## <a name="to-set-the-application-identity"></a>アプリケーション ID を設定するには  
  
-   使用して、**アプリケーション Id** MQSAgent COM + 構成ウィザードの次のように MQSAgent のアプリケーション id を設定するページ。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**対話型のユーザー**|アプリケーション ID に現在のログオン アカウントを使用する場合にこのオプションを選択します。|  
    |**Local Service**|アプリケーション ID にビルトイン サービス アカウントを設定します。|  
    |**Network Service**|アプリケーション ID にネットワーク アクセス権付きのビルトイン サービス アカウントを設定します。|  
    |**このユーザー**|アプリケーション ID に、指定したユーザー名を設定します。|  
  
> [!NOTE]
>  アプリケーション ID に管理権限を持つアカウントを使用することはお勧めしません。 このアカウントには、MQSeries キューに対する必要最低限の権限 (読み取りと書き込みのアクセス許可) を付与する必要があります。  
  
## <a name="to-name-the-role-and-add-users-to-it"></a>ロールに名前を付けてユーザーを追加するには  
  
-   使用して、**ロールの名前**MQSAgent COM + 構成ウィザードの次のように、役割に、名前とユーザーを割り当てるページ。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**ロールの名前**|ロールの名前を入力します。|  
    |**ユーザー**|ロールに属しているユーザーを表示します。|  
    |**[追加]**|ユーザーをロールに追加します。 これらのユーザーは、アダプターを使用する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サービス アカウントです。|  
  
> [!NOTE]
>  ロールには、アダプターにアクセスする必要のあるアカウントのみを追加してください。  
  
## <a name="to-set-the-msdtc-security-configuration-on-the-windows-server-2008-computer-to-no-authentication-required"></a>Windows Server 2008 コンピューター上の MSDTC のセキュリティ構成を [認証を必要としない] に設定するには  
 MQSAgent COM + アプリケーションがインストールされている場合、[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]コンピューターと、MQSeries アダプター (と共にインストールされる[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]) にインストールされて、[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]または[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]コンピューター、MSDTC セキュリティ構成を[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]または[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]にコンピューターを設定する必要があります**認証を必要としない**です。 MSDTC のセキュリティ構成を [認証を必要としない] に設定するには、次の手順を実行します。  
  
1.  をクリックして**開始**] をクリックし、**コントロール パネルの [**です。  
  
2.  ダブルクリックして**管理ツール**です。  
  
3.  ダブルクリックして**コンポーネント サービス**を起動する、**コンポーネント サービス**管理インターフェイスです。  
  
4.  展開**コンポーネント サービス**、展開**コンピューター**、順に展開**マイ コンピューター**です。  
  
5.  右クリック**マイ コンピューター**  をクリックし、**プロパティ**メニュー項目。  
  
6.  **マイ コンピューター**ダイアログ ボックスで、をクリックして、 **MSDTC**  タブをクリックして**セキュリティ構成**です。  
  
7.  **セキュリティ構成** ダイアログ ボックスで、**トランザクション マネージャー通信**セクションで、**認証を必要としない**です。 ダイアログ ボックスでメッセージが表示されたら、クリックして**はい**MS DTC サービスを再起動します。  
  
8.  MS DTC サービスが再起動した後にをクリックして**OK**  をクリック**ok**を閉じます、**マイ コンピューター**  ダイアログ ボックス。  
  
9. 閉じる、**コンポーネント サービス**管理インターフェイスです。  
  
## <a name="to-configure-the-mqsagent-runtime-components-to-run-under-an-alternative-set-of-credentials"></a>代替資格情報のセットで実行する MQSAgent ランタイム コンポーネントを構成するには  
 MQSAgent COM+ アプリケーションには、管理およびランタイム用のコンポーネントが含まれています。 セキュリティ上の理由でこの機能を異なる COM+ アプリケーションに分割する場合は、MQSAgent COM+ アプリケーションがインストールされているコンピューター上で次の手順を実行してください。  
  
1.  MQSAgent COM+ コンポーネントに変更を加えられるようにします。  
  
    -   をクリックして**開始**] をクリックし、**コントロール パネルの [**です。  
  
    -   ダブルクリックして**管理ツール**です。  
  
    -   ダブルクリックして**コンポーネント サービス**を起動する、**コンポーネント サービス**管理インターフェイスです。  
  
    -   展開**コンポーネント サービス**、展開**マイ コンピューター**、展開**COM + アプリケーション**を右クリックし、 **MQSAgent2** COM + アプリケーションクリックして**プロパティ**です。  
  
    -   クリックして、 **[詳細設定]**タブおよびボックスをオフに**変更を無効にする**です。  
  
    -   **[OK]**をクリックします。  
  
2.  MQSAgent ランタイム コンポーネント用の新しい COM+ アプリケーションを作成します。  
  
    -   右クリック**COM + アプリケーション**をクリックして**新規**、**アプリケーション**を表示する、 **COM + アプリケーション インストール ウィザード** をクリック**次へ**です。  
  
    -   をクリックして**空のアプリケーションを作成する**です。  
  
    -   名前を入力します**MQSAgent2RunTime**の既定のオプションのままにして**サーバー アプリケーション**有効になっており、クリックして**次**です。  
  
    -   オプションを選択**このユーザー**、適切なアカウント情報を入力し、をクリックして**次**です。  
  
        > [!NOTE]
        >  このアカウントが必要**接続**と**put**や**取得**適切な IBM WebSphere MQ キューの Windows のアクセス許可。 このアカウントに対する適切なアクセス許可を設定することができます、 **setmqaut**コマンドを使用して IBM WebSphere MQ とします。 詳細については、 **setmqaut**コマンドは、IBM WebSphere MQ のドキュメントを参照してください。  
  
    -   をクリックして**次**上、**アプリケーション ロールの追加** ダイアログ ボックス。  
  
    -   をクリックして**次へ**上、**ロールにユーザーの追加** ダイアログ ボックス。  
  
    -   **[完了]**をクリックします。  
  
3.  ランタイム コンポーネントを、新しい COM+ アプリケーションに移動します。  
  
    -   展開して、 **MQSAgent2** COM + アプリケーションです。  
  
    -   展開**コンポーネント**です。  
  
    -   右クリックし、 **MQSAgent2.MQSAgent.1**コンポーネントとクリック**移動**を表示する、**コンポーネント (s) の移動** ダイアログ ボックス。  
  
    -   選択**MQSAgent2RunTime** [**の保存先を選択してください**] をクリック**OK**です。  
  
    -   次の手順を繰り返して、 **MQSAgent2.MQSBroker.1**と**MQSAgent2.MQSProxy.1**コンポーネントです。  
  
## <a name="see-also"></a>参照  
 [MQSeries アダプターを構成する方法は、送信し、受信ハンドラー](../core/how-to-configure-mqseries-adapter-send-and-receive-handlers.md)   
 [MQSeries アダプターの構成](../core/configuring-the-mqseries-adapter.md)