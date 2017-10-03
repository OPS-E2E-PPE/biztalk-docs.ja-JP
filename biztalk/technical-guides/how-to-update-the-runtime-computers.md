---
title: "ランタイム コンピューターを更新する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 576a7065-04b6-436c-acf9-28c8d6e40107
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0fc6423a8918237362636f26322b145a0cbcf26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-update-the-runtime-computers"></a>ランタイム コンピューターを更新する方法
送信先システム[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム コンピューターで構成されます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実稼働環境で実行されている実稼働の BizTalk グループの一部として構成します。 各設定を更新する必要があります、障害回復環境で実稼働の BizTalk グループが復元される場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ことは、災害復旧を指すように、ランタイム コンピューター[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]復元されたに接続しようとしたときのインスタンス運用環境の BizTalk グループです。 送信先システムに、BizTalk グループが復元されると後、に、次の手順を使用して更新、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム コンピューター。  
  
### <a name="to-update-the-biztalk-server-runtime-computers"></a>BizTalk Server ランタイム コンピューターを更新するには  
  
1.  編集した SampleUpdateInfo.xml ファイルを \Program Files\Microsoft にコピー [!INCLUDE[prague](../includes/prague-md.md)]\Schema\Restore ディレクトリすべて 32 ビットの BizTalk サーバーで \Program Files (x86) \microsoft[!INCLUDE[prague](../includes/prague-md.md)]すべての 64 ビットで \Bins32\Schema\Restore ディレクトリ送信先システムに BizTalk server。  
  
2.  各 BizTalk server では、コマンド プロンプトを開きます。 をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
    > [!NOTE]  
    >  64 ビット コンピューターでは、64 ビット コマンド プロンプトを開く必要があります。  
  
3.  コマンド プロンプトで \Program Files\Microsoft に移動[!INCLUDE[prague](../includes/prague-md.md)](32 ビット コンピュータ) の \Schema\Restore または \Program Files (x86) \Microsoft [!INCLUDE[prague](../includes/prague-md.md)]\Bins32\Schema\Restore (64 ビット コンピューター) でこのコマンドを入力します。  
  
    ```  
    cscript UpdateRegistry.vbs SampleUpdateInfo.xml  
    ```  
  
4.  有効にし、送信先システムにすべての BizTalk ホスト インスタンスおよび BizTalk server 上の他のすべての BizTalk サービスを再開します。  
  
5.  送信先システムで、各 BizTalk サーバーで WMI を再起動します。 をクリックして**開始**、 をクリックして**実行**、型**services.msc**、順にクリック**ok**です。 **Services** MMC スナップインで、右クリックして**Windows Management Instrumentation**を選択し、**再起動**です。  
  
6.  各 BizTalk サーバーで開く、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックして**BizTalk グループ**、し、**削除**です。  
  
7.  右クリック**BizTalk Server 2010 管理**[**既存グループに接続**SQL Server データベース インスタンスを選択して、データベースの名前の BizTalk 管理データベースに対応します。クリックして BizTalk グループ]、 **OK**です。  
  
    > [!NOTE]  
    >  更新した後、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム コンピューターでは、する必要がありますも更新、 **SSO サーバー名**に表示されるとおり、**グループのプロパティ** ダイアログ ボックスで使用できる、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 更新する、 **SSO サーバー名**、起動、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをクリックして展開[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理 を右クリックし、 **BizTalk グループ**ノードと選択**プロパティ**を表示する、**全般**のタブ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 その後、、 **SSO サーバー名** ボックスに、アダプターの構成情報にアクセスして このコンピューターが使用するエンタープライズ シングル サインオン サーバーの名前を入力**OK**です。 これは、SSO データベースへの接続に使用する SSO サーバーの名前です。  
  
8.  各 BizTalk ランタイム サーバーで次の Windows サービスを再起動します。  
  
    -   エンタープライズ SSO サービス  
  
    -   ルール エンジン更新サービス  
  
    -   BizTalk ホスト インスタンス  
  
## <a name="see-also"></a>参照  
 [ランタイム コンピューターを回復します。](../technical-guides/recovering-the-runtime-computers.md)