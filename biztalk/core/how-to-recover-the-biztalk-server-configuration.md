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
ms.openlocfilehash: 59910e1af14ff9d21ea196d9ec92202772541876
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335488"
---
# <a name="how-to-recover-the-biztalk-server-configuration"></a>BizTalk Server 構成を復旧する方法
BizTalk サーバーの回復の一部として、BizTalk Server をインストールしたときに作成した構成ファイルをインポートすることも必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、管理者グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-recover-the-biztalk-server-configuration"></a>BizTalk Server 構成を復旧するには  
  
1. メモ帳を使用して、以前バックアップした、BizTalk Server 構成ファイルを編集し、BizTalk Server サービスのすべてのユーザー アカウントのパスワードを入力します。  
  
2. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 構成**します。  
  
3. **Microsoft BizTalk Server 構成**、 をクリックして**構成のインポート**します。  
  
    機能の前に表示される無効のアイコンがないことを確認します。 構成エラーがある機能のいずれかの場合は、それらを修正する時間をようになりました。  
  
4. **[構成の適用]** をクリックします。  
  
    BizTalk Server の機能が構成した後は、すべて、構成ウィンドウを閉じます。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server を実行しているコンピューターの回復](../core/recovering-a-computer-running-biztalk-server.md)   
 [BizTalk Server の構成をバックアップする方法](../core/how-to-back-up-the-biztalk-server-configuration.md)