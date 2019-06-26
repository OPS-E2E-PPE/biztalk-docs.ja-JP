---
title: MQSAgent COM + 構成ウィザードを使用して |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mqsagent.wizard
helpviewer_keywords:
- MQSeries adapters, MQSAgent COM+ Configuration Wizard
- configuring [MQSeries adapters], MQSAgent COM+ Configuration Wizard
- MQSAgent COM+ Configuration Wizard
ms.assetid: f106700a-7f57-4c83-9344-6525fc10544d
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f304039d0d6d68d12bfc7605cba69bb01e22ca7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395990"
---
# <a name="using-the-mqsagent-com-configuration-wizard"></a>MQSAgent COM + 構成ウィザードの使用
MQSAgent COM + 構成ウィザードは、MQSAgent では、アダプターの COM + アプリケーション (MQSeries コンポーネント) 部分を構成します。 ウィザードでは、コンポーネント、およびロールの名前と、ロールに含まれるユーザーのアプリケーション id を設定します。 MQSAgent COM + 構成ウィザードを使用して作成される MQSAgent COM + コンポーネントの名前は**MQSAgent2**します。  

> [!NOTE]
>  MQSAgent COM + アプリケーションは、64 ビットの Windows server でサポートされます。 WOW64 の下で 32 ビット プロセスとして実行されます。 A [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-64 ビット バージョンの Windows Server で実行されているベースのコンピューターを持つ、MQSAgent がインストールされているリモートの 32 ビット コンピューターと通信できます。  
> 
> [!NOTE]
>  MQSeries エージェントと MQSAgent COM + 構成ウィザードの実行可能ファイル**MQSConfigWiz.exe** BizTalk Server 2009 から BizTalk Server までアップグレードする場合はインストールされません。 セットアップを再実行して、BizTalk Server 2009 から BizTalk Server へのアップグレード後は、選択、**変更**オプション、およびこれらのコンポーネントをインストールする追加のソフトウェア MQSeries エージェントを選択します。  

## <a name="to-set-the-application-identity"></a>アプリケーション id を設定するには  

-   使用して、**アプリケーション Id** MQSAgent COM + 構成ウィザードの次のように MQSAgent のアプリケーション id を設定するページ。  

    |プロパティ|目的|  
    |--------------|----------------|  
    |**対話型ユーザー**|アプリケーション id の現在のログオン アカウントを使用するには、このオプションを選択します。|  
    |**Local Service**|組み込みのサービス アカウントには、アプリケーション id を設定します。|  
    |**Network Service**|ネットワーク アクセス権を持つビルトイン アカウントには、アプリケーション id を設定します。|  
    |**このユーザー**|アプリケーション id を指定したユーザー名に設定します。|  

> [!NOTE]
>  アプリケーション id の管理アクセス許可を持つアカウントを使用することは推奨されません。 アカウントは必要な最小限の権限が必要: 読み取りおよび書き込み、MQSeries キューに対する権限。  

## <a name="to-name-the-role-and-add-users-to-it"></a>ロールの名前を指定し、ユーザーを追加するには  

- 使用して、**ロールの名前**MQSAgent COM + 構成ウィザードの次のように、役割に、名前とユーザーを割り当てるページ。  


  |     プロパティ     |                                                                         目的                                                                          |
  |------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|
  | **ロールの名前** |                                                                 ロールの名前を入力します。                                                                  |
  |    **ユーザー**     |                                                         ロールに属しているユーザーを表示します。                                                          |
  |     **[追加]**      | ロールにユーザーを追加します。 これらは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サービス アダプターを使用するアカウント。 |

> [!NOTE]
>  アダプターへのアクセスを必要とするロールの唯一のアカウントを追加します。  

## <a name="to-set-the-msdtc-security-configuration-on-the-windows-server-2008-computer-to-no-authentication-required"></a>認証を必要としないを Windows Server 2008 コンピューターで MSDTC のセキュリティ構成を設定するには  
 MQSAgent COM + アプリケーションがインストールされている場合、[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]でコンピューターと、MQSeries アダプター (これは BizTalk Server と共にインストールされます) がインストールされている、[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]または[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]コンピューター、MSDTC セキュリティ構成を[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]または[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]にコンピューターを設定する必要があります**認証を必要としない**します。 認証を必要としない MSDTC セキュリティ構成を設定する次の手順に従います。  

1.  クリックして**開始**順にクリックします**コントロール パネルの** します。  

2.  **［管理ツール］** をダブルクリックします。  

3.  ダブルクリック**コンポーネント サービス**を起動する、**コンポーネント サービス**管理インターフェイスです。  

4.  展開**コンポーネント サービス**、展開**コンピューター**、順に展開**マイ コンピューター**します。  

5.  右クリックして**マイ コンピューター**  をクリックし、**プロパティ**メニュー項目。  

6.  **マイ コンピューター**ダイアログ ボックスで、をクリックして、 **MSDTC**  タブをクリックして**セキュリティ構成**します。  

7.  **セキュリティ構成** ダイアログ ボックスで、**トランザクション マネージャー通信**セクションで、**認証を必要としない**します。 ダイアログ ボックスが表示されたら、クリックして**はい**MS DTC サービスを再起動します。  

8.  MS DTC サービスが再起動した後にをクリックして**ok**  をクリック**OK**を閉じるためにもう一度、**マイ コンピューター**  ダイアログ ボックス。  

9. 閉じる、**コンポーネント サービス**管理インターフェイスです。  

## <a name="to-configure-the-mqsagent-runtime-components-to-run-under-an-alternative-set-of-credentials"></a>代替の資格情報のセットを使用して実行するように MQSAgent ランタイム コンポーネントを構成するには  
 MQSAgent COM + アプリケーションには、管理とランタイムの両方のコンポーネントが含まれています。 セキュリティのための異なる COM + アプリケーションには、この機能を分離する場合は、次の手順に、MQSAgent COM + アプリケーションがインストールされているコンピューターで。  

1.  MQSAgent COM + コンポーネントの変更を有効にします。  

    -   クリックして**開始**順にクリックします**コントロール パネルの** します。  

    -   **［管理ツール］** をダブルクリックします。  

    -   ダブルクリック**コンポーネント サービス**を起動する、**コンポーネント サービス**管理インターフェイスです。  

    -   展開**コンポーネント サービス**、展開**マイ コンピューター**、展開**COM + アプリケーション**を右クリックし、 **MQSAgent2** COM + アプリケーションクリックして**プロパティ**します。  

    -   をクリックして、 **詳細設定**  タブでオフにし、**変更を無効にする**します。  

    -   **[OK]** をクリックします。  

2.  MQSAgent ランタイム コンポーネントの新しい COM + アプリケーションを作成します。  

    -   右クリックして**COM + アプリケーション**、 をクリックして**新規**、**アプリケーション**を表示する、 **COM + アプリケーション インストール ウィザード**をクリックします。**次へ**します。  

    -   クリックして**空のアプリケーションを作成する**します。  

    -   名前を入力します**MQSAgent2RunTime**の既定のオプションのままに**サーバー アプリケーション**有効になっており、クリックして**次**します。  

    -   オプションを選択**このユーザー**、適切なアカウント情報を入力し、をクリックして**次**します。  

        > [!NOTE]
        >  このアカウントが必要**接続**と**配置**や**取得**適切な IBM WebSphere MQ for Windows キューに対するアクセス許可。 このアカウントに対する適切なアクセス許可を設定することができます、 **setmqaut**コマンドを IBM WebSphere MQ を使用します。 詳細については、 **setmqaut**コマンドは、IBM WebSphere MQ のドキュメントを参照してください。  

    -   をクリックして**次**上、**アプリケーション ロールの追加** ダイアログ ボックス。  

    -   をクリックして**次へ**上、**ロールにユーザーの追加** ダイアログ ボックス。  

    -   **[完了]** をクリックします。  

3.  ランタイム コンポーネントを新しい COM + アプリケーションに移動します。  

    -   展開、 **MQSAgent2** COM + アプリケーション。  

    -   展開**コンポーネント**します。  

    -   右クリックし、 **MQSAgent2.MQSAgent.1**コンポーネントをクリックします**移動**を表示する、**コンポーネント (秒) の移動** ダイアログ ボックス。  

    -   選択**MQSAgent2RunTime** **[変換先を選択してください]** をクリック**OK**。  

    -   次の手順を繰り返して、 **MQSAgent2.MQSBroker.1**と**MQSAgent2.MQSProxy.1**コンポーネント。  

## <a name="see-also"></a>参照  
 [MQSeries アダプターを構成する方法は、送信し、受信ハンドラー](../core/how-to-configure-mqseries-adapter-send-and-receive-handlers.md)   
 [MQSeries アダプターの構成](../core/configuring-the-mqseries-adapter.md)