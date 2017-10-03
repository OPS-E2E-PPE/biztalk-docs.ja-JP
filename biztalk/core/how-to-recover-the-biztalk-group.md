---
title: "BizTalk グループを回復する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f1010e55-7e3d-4565-8604-ea652ea4da8c
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23cd2a6550263f707531101db743a6ecdef39e5e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-recover-the-biztalk-group"></a>BizTalk グループを復旧する方法
システムの復旧処理では、BizTalk Server を既存の BizTalk グループに再度加える必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、管理者グループのメンバーとしてログオンする必要があります。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Standard Edition を復旧する場合は、サーバーの復旧を円滑にするスクリプトをダウンロードする必要があります。 ダウンロード[RestoreConfig.vbe](http://go.microsoft.com/fwlink/?LinkID=195799)です。  
  
### <a name="to-recover-the-biztalk-group-standard-edition"></a>BizTalk グループを復旧するには (Standard Edition)  
  
1.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
2.  コマンド プロンプトで、次のように入力します。  
  
     **RestoreConfig.vbe***\<SavedConfigXML >*   
  
     ここで *\<SavedConfigXML >*は完全なパスと保存されている構成ファイルのファイル名。  
  
     上記の操作でエラーが発生することはほとんどありません。  
  
    > [!NOTE]
    >  回復する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実行する必要があります、64 ビット コンピューターで、Standard Edition、 **RestoreConfig.vbe**のため、更新できる 32 ビット レジストリの 32 ビット コマンド プロンプトからです。 32 ビット コマンド プロンプトを開くには、をクリックして**開始**、 をクリックして**実行**、型**c:\windows\syswow64\cmd.exe**、クリックして**ok**です。  
  
    > [!NOTE]
    >  障害が発生したコンピューターの名前は、保存済みの構成ファイルに含まれています。 復旧するコンピューターの名前は、これと同じ名前でなければなりません。 その名前のコンピューター上で、前述のスクリプトを実行する必要があります。 ただし、保存済みの構成ファイルで、障害が発生したコンピューターの名前を変更することはできます。 これにより、別の名前のコンピューター上で前述のスクリプトを実行できます。  
  
### <a name="to-recover-the-biztalk-group-developer-edition-or-enterprise-edition"></a>BizTalk グループを復旧するには (Developer Edition または Enterprise Edition)  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 構成**です。  
  
2.  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、コンソール ツリーでクリックして**グループ**です。  
  
3.  詳細ウィンドウで、次のように選択します。**既存の BizTalk グループに参加**、し、適切なリモート BizTalk 管理 (BizTalkMgmtDb) データベースを指定します。  
  
4.  [**構成の適用**] をクリックします。  
  
5.  をクリックして**ファイル**、クリックして**終了**です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server を実行しているコンピューターの回復](../core/recovering-a-computer-running-biztalk-server.md)