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
ms.openlocfilehash: ea2b32ef67ad219d09e50824be5d83880c929c76
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385763"
---
# <a name="how-to-connect-to-an-existing-group"></a>既存のグループに接続する方法
使用することができます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]これらのグループは、同じドメイン内または信頼されたドメイン内のコンピューターにある限り、企業内の 1 つまたは複数の BizTalk Server グループをリモートで管理する、企業内のコンピューターの管理コンソール。  
  
 BizTalk Server 管理コンソールで、BizTalk Server 管理ノードは、最上位レベルのノードのすべての BizTalk グループであり、BizTalk Server 管理コンソールに既存の BizTalk Server グループを追加するときに使用するレベルです。 グループを追加するときに接続する、既存のサーバーと BizTalk 管理データベースを指定する必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行するには、必要がありますまたはログインする BizTalk Server Operators グループのメンバーとして、BizTalk Server 管理者グループのメンバーとして。  
  
### <a name="to-connect-to-an-existing-group"></a>既存のグループに接続するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、右クリック**BizTalk Server 管理**、 をクリックし、**既存グループへの接続**します。  
  
3. **既存の BizTalk Server 構成データベースへの接続** ダイアログ ボックスで、 **SQL Server 名**ドロップダウン リスト ボックスで、BizTalk をホストする Microsoft SQL Server インスタンスの名前を選択します。管理のデータベース (構成データベースとも呼ばれます)。 SQL Server のインスタンスを選択すると、BizTalk Server はそのコンピューター上の BizTalk Server データベースを検出するために自動的に試行します。  
  
4. **データベース名**ドロップダウン リスト ボックスで、BizTalk Server 管理データベースを選択します (**BizTalkMgmtDb**) クリックして、接続先**OK**します。  
  
    BizTalk Server 管理コンソールでは、コンソール ツリーに BizTalk Server グループを追加します。  
  
   > [!NOTE]
   >  場合は、BizTalk Server 管理データベースが SQL Server クラスターに格納されているし、クラスターがフェールオーバー中では、管理データベースに接続しようとしたときに、次のようなエラーを受け取る可能性があります。  
   >   
   >  グループの読み込みに失敗しました [\<servername\>:\<管理データベース\>] データ プロバイダー。  
   >   
   >  And  
   >   
   >  追加情報:  
   >   
   >  WMI クラスのインスタンスが見つかりませんでした。 (WinMgmt)。  
   >   
   >  BizTalk データベースがフェールオーバーされるときに利用できないために、このエラーが発生することができます。 回避策にこの問題は、SQL Server のクラスター化されたインスタンスまでの待機はオンライン BizTalk Server 管理コンソールを使用して接続する前にです。  
  
## <a name="see-also"></a>参照  
 [グループの管理](../core/managing-groups.md)   
 [BizTalk グループ](../core/biztalk-groups.md)