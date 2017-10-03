---
title: "BizTalk Server の構成を回復する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c1d39e50-4296-49c7-bd1e-63b1325af168
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9935c2c565d78d0bc102d4aef86959c2a9066e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-recover-the-biztalk-server-configuration"></a>BizTalk Server 構成を復旧する方法
BizTalk Server を復旧するときには、BizTalk Server をインストールしたときに作成した構成ファイルもインポートする必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、管理者グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-recover-the-biztalk-server-configuration"></a>BizTalk Server 構成を復旧するには  
  
1.  メモ帳を使用して、以前バックアップした BizTalk Server 構成ファイルを編集し、すべての BizTalk Server サービスに対するユーザー アカウントのパスワードを入力します。  
  
2.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 構成**です。  
  
3.  **Microsoft BizTalk Server 構成**をクリックして**構成のインポート**です。  
  
     機能の前に無効のアイコンが表示されていないことを確認します。 構成エラーがある機能が存在する場合は、ここで修正します。  
  
4.  [**構成の適用**] をクリックします。  
  
     すべての BizTalk Server 機能の構成が終了したら、構成ウィンドウを閉じます。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server を実行しているコンピューターの回復](../core/recovering-a-computer-running-biztalk-server.md)   
 [BizTalk Server の構成をバックアップする方法](../core/how-to-back-up-the-biztalk-server-configuration.md)