---
title: BizTalk Server の構成を回復する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1d39e50-4296-49c7-bd1e-63b1325af168
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 179ff0690c7c07dcf58bf2d7fd92a885435509cc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980339"
---
# <a name="how-to-recover-the-biztalk-server-configuration"></a>BizTalk Server 構成を復旧する方法
BizTalk Server を復旧するときには、BizTalk Server をインストールしたときに作成した構成ファイルもインポートする必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、管理者グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-recover-the-biztalk-server-configuration"></a>BizTalk Server 構成を復旧するには  
  
1. メモ帳を使用して、以前バックアップした BizTalk Server 構成ファイルを編集し、すべての BizTalk Server サービスに対するユーザー アカウントのパスワードを入力します。  
  
2. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 構成**します。  
  
3. **Microsoft BizTalk Server 構成**、 をクリックして**構成のインポート**します。  
  
    機能の前に無効のアイコンが表示されていないことを確認します。 構成エラーがある機能が存在する場合は、ここで修正します。  
  
4. **[構成の適用]** をクリックします。  
  
    すべての BizTalk Server 機能の構成が終了したら、構成ウィンドウを閉じます。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server を実行しているコンピューターの回復](../core/recovering-a-computer-running-biztalk-server.md)   
 [BizTalk Server の構成をバックアップする方法](../core/how-to-back-up-the-biztalk-server-configuration.md)