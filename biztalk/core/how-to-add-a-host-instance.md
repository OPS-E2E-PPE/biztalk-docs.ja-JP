---
title: ホスト インスタンスの追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 98ba10a6-c5e7-4dec-98f1-4e6ba44c2851
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c95dc019d1d6ed885d195f0c871fd91178b9a58a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006819"
---
# <a name="add-a-host-instance"></a>ホスト インスタンスを追加します。

## <a name="overview"></a>概要
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールまたは Windows Management Instrumentation (WMI) を使用すると、ホスト インスタンスを追加できます。 しかし、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では一度に 1 つのサーバーにしかホスト インスタンスを追加できません。 ホスト インスタンスの詳細については、[ホスト インスタンス](../core/host-instances.md)を参照してください。 WMI を使用して、ホスト インスタンスを追加する方法については、**MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]を参照してください。
  
 ホスト インスタンスを追加すると、そのホストのインスタンスは BizTalk Server のインスタンスにマップされます。 既存のホスト インスタンスを修復する必要がある場合は、ホスト インスタンスのプロパティを更新できます。 既存のホスト インスタンスを再度追加するには、インスタンスを停止する必要があります。 ホスト インスタンスの停止については、[ホスト インスタンスを停止する方法](../core/how-to-stop-a-host-instance.md)を参照してください。  
  
> [!NOTE]
>  サポート技術情報資料 184802「User32.dll または Kernel32.dll の初期化に失敗」で利用可能な手順が従う必要があります詳細 26 のホスト インスタンスを作成する場合は、 [ http://go.microsoft.com/fwlink/?LinkId=26176](http://go.microsoft.com/fwlink/?LinkId=26176)します。 このサポート技術情報の資料に記載されている内容を反映した後で、ホスト インスタンスを追加する必要がある場合は、BTSNTSvc サービスの各インスタンスに割り当てるメモリ量を減らしてみてください。 メモリ量を減らすことによって、追加のインスタンスを作成するのに必要なメモリを提供できます。  
  
> [!NOTE]
>  サービス アカウントには、ホスト インスタンスのインストール先サーバーに対する "サービスとしてログオン" アクセス許可が自動的に与えられます。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、管理者グループのメンバーおよび BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。  
  
 また、次のデータベースが置かれているサーバーにおいて、db_securityadmin SQL Server データベース ロールおよび securityadmin SQL Server ロールのメンバーであることが必要です。  
  
-   BAM プライマリ インポート (BAMPrimaryImport)  
  
-   BizTalk 管理 (BizTalkMgmtDb)  
  
-   BizTalk メッセージ ボックス (BizTalkMsgBoxDb) (すべて)  
  
-   BizTalk 追跡 (BizTalk DTADb)  
  
-   ルール エンジン (BizTalkRuleEngineDb)  
  
> [!CAUTION]
>  ホスト インスタンスのアカウント情報は、BizTalk Server 管理コンソールまたは Windows Management Instrumentation (WMI) スクリプトを使用して更新することをお勧めします。 これにより、BizTalk Server が BizTalk Server データベースのアカウント情報を更新し、データベースとホスト インスタンス間でセキュリティ構成が同期された状態を維持することができます。  
  
## <a name="steps"></a>手順
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]BizTalk グループを展開し、クリックして**プラットフォームの設定**します。  
  
3. 右クリック**ホスト インスタンス**、 をクリックして**新規**、 をクリックし、**ホスト インスタンス**します。  
  
4. **ホスト インスタンスのプロパティ** ダイアログ ボックスで、次の操作をクリックして**OK**:  
  
   |プロパティ|目的|  
   |--------------|----------------|  
   |**ホスト名**|選択したサーバーに関連付けられているホストの名前を表示します。|  
   |**[サーバー]**|選択したホストに関連付けられているサーバーを表示します。|  
   |**ログオン**|ホスト インスタンスを実行する、新しいサービス アカウントのアカウント名を表示します。|  
   |**構成**|表示するをクリックして、**ログオン資格情報**] ダイアログ ボックスの [アカウント名とホスト インスタンスを実行するアカウントのパスワードを入力できます。|  
   |**ホスト インスタンスの開始を無効にします。**|選択したホストの状態を有効から無効に変更する場合、このチェック ボックスをオンにします。 ホスト インスタンスを開始せずに設定を保持する場合は、インスタンスを無効にすると便利です。|  
  
   ホスト インスタンスをインストールしたら、インスタンスを再起動して、メッセージがメッセージ ボックス データベースにルーティングされるようにする必要があります。 ホスト インスタンスの開始方法の詳細については、[ホスト インスタンスを開始する方法](../core/how-to-start-a-host-instance.md)を参照してください。  
  
## <a name="known-issues"></a>既知の問題  
  
#### <a name="a-biztalk-host-instance-is-created-with-a-status-of-uninstall-failed-if-the-designated-biztalk-server-runtime-computer-is-not-available-during-host-instance-creation"></a>BizTalk ホスト インスタンスの作成時に、指定した BizTalk Server ランタイム コンピューターを利用できない場合、状態が "アンインストールの失敗" のホスト インスタンスが作成される  
  
##### <a name="problem"></a>問題  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイム コンピューターとは別のリモート コンピューター上に BizTalk 管理コンソールがインストールされている場合、このリモート [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターが利用できない状態にあっても、この [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューター上にホスト インスタンスの作成を試みることが可能です。  
  
 利用できない [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューター上に BizTalk ホストのインスタンスを作成しようとすると、次のエラー メッセージを示すダイアログ ボックスが表示されます。  
  
 ホストのインスタンスのインストール\<*ホスト名*\>サーバー \<*サーバー名*\>できませんでした。  
  
 追加情報:  
  
 RPC サーバーを利用できません。 (WinMgmt)。  
  
 [OK] をクリックしてダイアログ ボックスを消すと、次のエラー メッセージを示すダイアログ ボックスが表示されます。  
  
 中止されたホストのインストールをクリーンアップする\<*ホスト名*\>サーバー \<*サーバー名*\>できませんでした。  
  
 追加情報:  
  
 Windows NT サービス BTSSvc を削除するときにエラーが発生しました {*\<GUID\>*}。 (WinMgmt)。  
  
 クリックすると**OK**をこのダイアログ ボックスを閉じるには、BizTalk ホストのインスタンスは、BizTalk 管理コンソールに表示されます、**状態**の**アンインストールに失敗しました**.  
  
##### <a name="cause"></a>原因  
 ホスト インスタンスの作成時には、指定した [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューター上にホスト インスタンスがインストールされる前に、BizTalk 管理データベースにエントリが作成されます。 指定した [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューター上へのホスト インスタンスのインストールに失敗すると、BizTalk 管理プログラムは、そのホスト インスタンスのアンインストールを試みます。しかし、指定した [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターが利用できないため、アンインストールにも失敗します。  
  
##### <a name="resolution"></a>解決策  
 BizTalk ホスト インスタンスが BizTalk 管理コンソールの状態で作成された場合**アンインストールに失敗しました**、ホスト インスタンスを削除し、ホスト インスタンスを再作成後、指定した BizTalk Server コンピューターが使用可能になります。  
  
> [!NOTE]
>  BizTalk 管理コンソールで、BizTalk ホスト インスタンスが作成されたかどうか、**状態**の**アンインストールに失敗しました**ホスト インスタンスは、指定した後でもは機能できません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューターが再び使用可能です。  
  
## <a name="see-also"></a>参照  
 [BizTalk ホストとホスト インスタンスの管理](../core/managing-biztalk-hosts-and-host-instances.md)   
 [ホスト インスタンスを開始します。](../core/how-to-start-a-host-instance.md)   
 [ホスト インスタンスを停止します。](../core/how-to-stop-a-host-instance.md)   
 [ホスト インスタンスを削除します。](../core/how-to-delete-a-host-instance.md)   
 [ホスト インスタンスのプロパティを変更します。](../core/how-to-modify-host-instance-properties.md)