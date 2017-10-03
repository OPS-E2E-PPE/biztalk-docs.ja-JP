---
title: "HTTP の受信場所用に IIS を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 64-bit support, HTTP adapters
- HTTP adapters, IIS
- configuring [HTTP adapters], IIS
- receive locations, IIS
- IIS, receive locations
- HTTP adapters, 64-bit support
- IIS, HTTP adapters
ms.assetid: 1c420f46-01f1-4c9c-9144-d8d2acc8b0c4
caps.latest.revision: "26"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1daa535c546bef0b390f0f7f84c45d546ac0005
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-iis-for-an-http-receive-location"></a>HTTP の受信場所用に IIS を構成する方法
使用中の Microsoft Windows のバージョンによって、HTTP アダプター受信場所を使用するための Microsoft インターネット インフォメーション サービス (IIS) の構成方法は異なります。  
  
 使用中のオペレーティング システムが [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] または [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] の場合、IIS 7.0 では、Web アプリケーションを保護するために 2 種類のアプリケーション分離モードが提供されています。 既定のモードは、ワーカー プロセス分離モードです。 HTTP アダプター受信場所は、どちらのモードでも動作するように構成できますが、セキュリティを強化するため、ワーカー プロセス分離モードを使用することをお勧めします。  
  
> [!NOTE]
>  オペレーティング システムが x64 エディションの[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]または[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]、64 ビット版の HTTP 受信アダプターがインストール、 *\<ドライブ >***\Program Files (x86) \Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **\HttpReceive64**のディレクトリ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]既定です。 64 ビット版の HTTP 受信アダプターを 64 ビットのネイティブ モードで実行するには、コマンド ラインから次のスクリプトを実行する必要があります。  
>   
>  `cscript %SystemDrive%\inetpub\AdminScripts\adsutil.vbs set w3svc/AppPools/Enable32bitAppOnWin64 0`  
>   
>  `C:\WINDOWS\Microsoft.NET\Framework64\vX.X.XXXXX>aspnet_regiis.exe -i`  
  
> [!NOTE]
>  同一プロセスを共有する SOAP と HTTP を使用する IIS 構成は無効です。 プロセスごとに 1 つの分離受信場所のみを指定できます。  
  
### <a name="to-configure-the-iis-70-worker-process-isolation-mode-to-work-with-the-http-adapter-receive-location"></a>HTTP アダプターを使用する IIS 7.0 ワーカー プロセス分離モードの受信場所を構成するには  
  
1.  をクリックして**開始**、] をポイント**設定**、順にクリック**コントロール パネルの [**です。  
  
2.  コントロール パネルで、ダブルクリック**管理ツール**です。  
  
3.  [管理ツール] をダブルクリック**インターネット インフォメーション サービス**です。  
  
4.  インターネット インフォメーション サービスでルート Web サーバーのエントリを選択します。 **機能ビュー**をダブルクリックして**ハンドラー マッピング**、[操作] ウィンドウで、クリックして**スクリプト マップの追加**です。  
  
    > [!NOTE]
    >  Web サーバー レベルでスクリプトのマッピングを構成すると、すべての子 Web サイトにこのマッピングが適用されます。 マッピングを特定の Web サイトまたは仮想フォルダーに制限する場合は、Web サーバーではなくターゲット サイトまたはターゲット フォルダーを選択します。  
  
5.  **スクリプト マップの追加** ダイアログ ボックスで、**要求パス**フィールドに「`BtsHttpReceive.dll`です。  
  
6.  **実行可能ファイル**フィールドで、省略記号ボタン (**.**) ボタンをクリックしを参照[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive です。 選択**BtsHttpReceive.dll**  をクリックし、 **OK**です。  
  
7.  **名前**フィールドに「 `BizTalk HTTP Receive`、クリックしてして**要求の制限**です。  
  
8.  **要求の制限** ダイアログ ボックスをクリックして、**動詞**タブをクリックし**次の動詞のいずれかの**です。 入力`POST`動詞として。  
  
9. **アクセス**] タブで [**スクリプト**、クリックして**[ok]**です。  
  
10. ISAPI 拡張機能を許可するように求めるメッセージが表示されたら、 **[はい]**をクリックします。  
  
11. 右クリック**アプリケーション プール**、 をポイント**新規**、クリックして**アプリケーション プール**です。  
  
12. **アプリケーション プールの追加** ダイアログ ボックスで、**名前**ボックスで、アプリケーション プールの名前を入力します。 選択**NET Framework v4.0.30319**  をクリックし、 **OK**です。  
  
    > [!NOTE]
    >  バージョン番号は、コンピューターにインストールされている .NET Framework のバージョンによって異なります。  
  
     新しいアプリケーション プールの一覧に含ま**アプリケーション プール**です。  
  
13. **アプリケーション プール**の**機能ビュー**、新しいアプリケーション プールを選択して、をクリックして**詳細設定**[操作] ウィンドウ。  
  
14. **詳細設定** ダイアログ ボックスで、**プロセス モデル**セクションで、 **Identity**フィールドで省略記号ボタンをクリックして (**.**) ボタンをクリックします。  
  
15. **アプリケーション プール Id**ダイアログ ボックスで、**カスタム アカウント**、クリックして**設定**です。 **[OK]** をクリックして **[詳細設定]** ダイアログ ボックスを閉じます。  
  
16. IIS マネージャーで、開く、**サイト**フォルダーです。 右クリックし、 **Default Web Site**  をクリックし、**アプリケーションの追加**です。  
  
17. **アプリケーションの追加**ダイアログ ボックスで、**エイリアス**、クリックして、アプリケーションに関連付けるエイリアスを入力して**選択**です。  
  
18. **アプリケーション プールの選択**ダイアログ ボックスで、先ほど作成した新しいアプリケーション プールを選択し、をクリックして**OK**です。  
  
19. 省略記号ボタン (**.**) ボタンをクリックしを参照[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive、**物理パス**です。  
  
20. をクリックして**接続として**を入力し、**ユーザー名**と**パスワード**Administrators グループのメンバーであるし、ユーザー アカウントの**ok**.  
  
21. をクリックして**テストの設定**でエラーが表示されていないことを確認し、**接続のテスト** ダイアログ ボックス。 **[閉じる]**をクリックし、 **[OK]**をクリックします。  
  
22. 新しいアプリケーションの一覧に表示**既定の Web サイト**インターネット インフォメーション サービス (IIS) マネージャーでします。  
  
## <a name="see-also"></a>参照  
 [HTTP 受信場所を構成する方法](../core/how-to-configure-an-http-receive-location.md)