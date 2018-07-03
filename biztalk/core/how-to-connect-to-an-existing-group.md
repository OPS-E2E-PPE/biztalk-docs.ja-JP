---
title: 既存のグループに接続する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.admin.procedure.connecttogroup
helpviewer_keywords:
- groups, existing
- groups, connecting
- managing [groups], connecting
ms.assetid: 1eedbcd5-f3f1-4da5-b91c-67377131f889
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e29b57f39ab1cb86e34a9e744063ff248d12ad1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994355"
---
# <a name="how-to-connect-to-an-existing-group"></a>既存のグループに接続する方法
使用することができます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]これらのグループは、同じドメイン内または信頼されたドメイン内のコンピューターにある限り、企業内の 1 つまたは複数の BizTalk Server グループをリモートで管理する、企業内のコンピューターの管理コンソール。  
  
 BizTalk Server 管理コンソールで、BizTalk Server 管理ノードは、最上位レベルのノードのすべての BizTalk グループであり、BizTalk Server 管理コンソールに既存の BizTalk Server グループを追加するときに使用するレベルです。 グループを追加するときに、接続先の既存のサーバーおよび BizTalk 管理データベースを指定する必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、BizTalk Server Operators グループのメンバーまたは BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-connect-to-an-existing-group"></a>既存のグループに接続するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、右クリック**BizTalk Server 管理**、 をクリックし、**既存グループへの接続**します。  
  
3. **既存の BizTalk Server 構成データベースへの接続** ダイアログ ボックスで、 **SQL Server 名**ドロップダウン リスト ボックスで、BizTalk をホストする Microsoft SQL Server インスタンスの名前を選択します。管理のデータベース (構成データベースとも呼ばれます)。 SQL Server のインスタンスを選択すると、BizTalk Server によって自動的にそのコンピューター上の BizTalk Server データベースが検出されます。  
  
4. **データベース名**ドロップダウン リスト ボックスで、BizTalk Server 管理データベースを選択します (**BizTalkMgmtDb**) クリックして、接続先**OK**します。  
  
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
   >  このエラーは、フェールオーバー中に BizTalk 管理データベースが使用できないことが原因で発生することがあります。 回避策にこの問題は、SQL Server のクラスター化されたインスタンスまでの待機はオンライン BizTalk Server 管理コンソールを使用して接続する前にです。  
  
## <a name="see-also"></a>参照  
 [グループの管理](../core/managing-groups.md)   
 [BizTalk グループ](../core/biztalk-groups.md)