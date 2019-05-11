---
title: BizTalk グループの復旧 |Microsoft Docs
ms.custom: ''
ms.date: 01/30/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f1010e55-7e3d-4565-8604-ea652ea4da8c
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e637b974fc49fcfa3b1b6c27452ccc7d036359f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384429"
---
# <a name="how-to-recover-the-biztalk-group"></a>BizTalk グループを復旧する方法
BizTalk Server システム復旧プロセスの一部として既存の BizTalk グループには、再び参加させる必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、管理者グループのメンバーとしてログオンする必要があります。  
  
 回復する場合は[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Standard Edition は、サーバーの回復を容易にするスクリプトをダウンロードする必要があります。 ダウンロード[RestoreConfig.vbe](https://www.microsoft.com/download/details.aspx?id=7462)します。  
  
## <a name="recover-the-biztalk-group-standard-edition"></a>BizTalk グループ (Standard Edition) の復旧します。  
  
1. クリックして**開始**、型**cmd**、し、**コマンド プロンプト**します。  
  
2. コマンド プロンプトで、次のように入力します。  
  
    **RestoreConfig.vbe**  *\<SavedConfigXML\>*  
  
    場所*\<SavedConfigXML\>* は完全なパスと保存されている構成ファイルのファイル名。  
  
    上記の場合、エラーが発生することがなくが終了する必要があります。  
  
   > [!NOTE]
   >  回復する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 ビット コンピューターで Standard Edition を実行する必要がある**RestoreConfig.vbe** 32 ビットのレジストリを更新できるため、32 ビット コマンド プロンプトからです。 32 ビット コマンド プロンプトを開くには、次のようにクリックします。**開始**、 をクリック**実行**、型**c:\windows\syswow64\cmd.exe**、順にクリックします**OK**。  
   > 
   > [!NOTE]
   >  失敗したコンピューターの名前は、保存されている構成ファイルに含まれます。 同じ名前に復元しているコンピューターの名前が必要です。 その名前を持つコンピューターでは、前述のスクリプトを実行する必要があります。 ただし、保存されている構成ファイルで失敗したコンピューターの名前を変更することができます。 これを行う場合は、別の名前でコンピューターには、上記のスクリプトを実行できます。  
  
## <a name="recover-the-biztalk-group-developer-edition-or-enterprise-edition"></a>BizTalk グループ (Developer Edition または Enterprise Edition) の復旧します。  
  
1.  開いている**BizTalk Server 構成**([スタート] メニュー)。
  
2.  BizTalk Server 管理コンソールで次のように選択します。**グループ**します。  
  
3.  詳細] ウィンドウで、[**既存の BizTalk グループに参加**、リモートの BizTalk 管理 (BizTalkMgmtDb) データベースを入力します。  
  
4.  選択**構成の適用**します。  
  
5.  選択**ファイル**、し、**終了**します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server を実行しているコンピューターの復旧](../core/recovering-a-computer-running-biztalk-server.md)
