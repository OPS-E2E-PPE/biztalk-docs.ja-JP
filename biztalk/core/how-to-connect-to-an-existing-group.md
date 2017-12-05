---
title: "既存のグループに接続する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.admin.procedure.connecttogroup
helpviewer_keywords:
- groups, existing
- groups, connecting
- managing [groups], connecting
ms.assetid: 1eedbcd5-f3f1-4da5-b91c-67377131f889
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 942093faa4a556f31d090de97b3feff4eb7a9a45
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-connect-to-an-existing-group"></a>既存のグループに接続する方法
使用することができます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]これらのグループは、同じドメイン内または信頼されたドメイン内のコンピューターにある限り、企業内で 1 つまたは複数の BizTalk Server グループをリモートで管理する、企業内のコンピューターの管理コンソールです。  
  
 BizTalk Server 管理コンソールで [BizTalk Server 管理] ノードは、すべての BizTalk グループの上位レベルのノードで、既存の BizTalk Server グループを BizTalk Server 管理コンソールに追加するときに使用するレベルです。 グループを追加するときに、接続先の既存のサーバーおよび BizTalk 管理データベースを指定する必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、BizTalk Server Operators グループのメンバーまたは BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-connect-to-an-existing-group"></a>既存のグループに接続するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーを右クリックして**BizTalk Server 管理コンソール**、クリックして**既存グループに接続**です。  
  
3.  **既存の BizTalk Server 構成データベースへの接続** ダイアログ ボックスで、 **SQL Server 名**ドロップダウン リスト ボックスで、BizTalk をホストする Microsoft SQL Server インスタンスの名前を選択管理のデータベース (構成データベースとも呼ばれます)。 SQL Server のインスタンスを選択すると、BizTalk Server によって自動的にそのコンピューター上の BizTalk Server データベースが検出されます。  
  
4.  **データベース名**ドロップダウン リスト ボックスで、BizTalk Server 管理データベースを選択 (**BizTalkMgmtDb**) 接続し、をクリックするとなる**OK**です。  
  
     BizTalk Server 管理コンソールでは、コンソール ツリーに BizTalk Server グループを追加します。  
  
    > [!NOTE]
    >  BizTalk Server 管理データベースが SQL Server クラスターに格納されていて、そのクラスターがフェールオーバー プロセスを実行中の場合、BizTalk Server 管理データベースに接続しようとすると次のようなエラーが表示されることがあります。  
    >   
    >  グループの読み込みに失敗しました [\<servername\>:\<管理データベース\>] データ プロバイダー。  
    >   
    >  And  
    >   
    >  追加情報:  
    >   
    >  WMI クラスのインスタンスが見つかりません  (WinMgmt)。  
    >   
    >  このエラーは、フェールオーバー中に BizTalk 管理データベースが使用できないことが原因で発生することがあります。 回避策をこの問題は、SQL Server のクラスター化されたインスタンスの後にするまで待機はオンライン BizTalk Server 管理コンソールを使用して接続する前にです。  
  
## <a name="see-also"></a>参照  
 [グループを管理します。](../core/managing-groups.md)   
 [BizTalk グループ](../core/biztalk-groups.md)