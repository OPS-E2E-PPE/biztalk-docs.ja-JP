---
title: "BizTalk グループを回復 |Microsoft ドキュメント"
ms.custom: 
ms.date: 01/30/2018
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f1010e55-7e3d-4565-8604-ea652ea4da8c
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3563956daa4848d4d67c1321c23676b21f9e4735
ms.sourcegitcommit: 78376935362715684b451eb6da9f2b1e8c129c2b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="how-to-recover-the-biztalk-group"></a>BizTalk グループを復旧する方法
システムの復旧処理では、BizTalk Server を既存の BizTalk グループに再度加える必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、管理者グループのメンバーとしてログオンする必要があります。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Standard Edition を復旧する場合は、サーバーの復旧を円滑にするスクリプトをダウンロードする必要があります。 ダウンロード[RestoreConfig.vbe](https://www.microsoft.com/download/details.aspx?id=7462)です。  
  
## <a name="recover-the-biztalk-group-standard-edition"></a>BizTalk グループ (Standard Edition) 回復します。  
  
1.  をクリックして**開始**、型**cmd**、し、**コマンド プロンプト**です。  
  
2.  コマンド プロンプトで、次のように入力します。  
  
     **RestoreConfig.vbe**  *\<SavedConfigXML\>*  
  
     ここで *\<SavedConfigXML\>* は完全なパスと保存されている構成ファイルのファイル名。  
  
     上記の操作でエラーが発生することはほとんどありません。  
  
    > [!NOTE]
    >  回復する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実行する必要があります、64 ビット コンピューターで、Standard Edition、 **RestoreConfig.vbe**のため、更新できる 32 ビット レジストリの 32 ビット コマンド プロンプトからです。 32 ビット コマンド プロンプトを開くにはクリックして **開始**, 、 をクリックして **実行**, 、型 **c:\windows\syswow64\cmd.exe**, 、 をクリックし、 **ok**します。  
  
    > [!NOTE]
    >  障害が発生したコンピューターの名前は、保存済みの構成ファイルに含まれています。 復旧するコンピューターの名前は、これと同じ名前でなければなりません。 その名前のコンピューター上で、前述のスクリプトを実行する必要があります。 ただし、保存済みの構成ファイルで、障害が発生したコンピューターの名前を変更することはできます。 これにより、別の名前のコンピューター上で前述のスクリプトを実行できます。  
  
## <a name="recover-the-biztalk-group-developer-edition-or-enterprise-edition"></a>(Developer Edition または Enterprise Edition)、BizTalk グループを回復します。  
  
1.  開いている**BizTalk Server 構成**([スタート] メニュー)。
  
2.  BizTalk Server 管理コンソールで選択**グループ**です。  
  
3.  詳細ウィンドウで、次のように選択します。**既存の BizTalk グループに参加**、し、リモート BizTalk 管理データベース (BizTalkMgmtDb) を入力します。  
  
4.  選択**構成を適用**です。  
  
5.  選択**ファイル**、し、**終了**です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server を実行しているコンピューターの復旧](../core/recovering-a-computer-running-biztalk-server.md)
