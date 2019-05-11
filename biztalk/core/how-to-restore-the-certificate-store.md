---
title: 証明書ストアを復元する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c6f7551-d119-4668-9b52-6013f69a0302
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22a31c1b1fb9c25050202aa4f5f69fcd39af424b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384099"
---
# <a name="how-to-restore-the-certificate-store"></a>証明書ストアを復元する方法
復旧処理の一環として[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、証明書ストアを復元する必要があります。 回復する場合は[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Standard Edition は、証明書ストアを復元するこの手順を使用する必要があります。 その他のすべてのエディションを復旧する場合は、この手順を実行する必要はありません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]回復プロセスは、証明書ストアを自動的に復元されるため、します。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、管理者グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-restore-the-certificate-store-biztalk-server-standard-edition"></a>証明書ストア (BizTalk Server の Standard Edition) を復元するには  
  
1.  クリックして**開始**、 をクリックして**すべてのプログラム**、順にクリックします**Internet Explorer**します。  
  
2.  **ツール** メニューのをクリックして**インターネット オプション**します。  
  
3.  **インターネット オプション**ダイアログ ボックスで、をクリックして、**コンテンツ**タブをクリックし、をクリックし、**証明書**します。  
  
4.  **証明書**ダイアログ ボックスで、をクリックして、**その他のユーザー**タブをクリックし、をクリックし、**インポート**します。  
  
5.  **証明書のインポート ウィザード**、 をクリックして**キャンセル**します。  
  
     これを作成、 **AddressBook**レジストリ ハイブ。  
  
6.  **証明書**ダイアログ ボックスで、をクリックして**閉じる**します。  
  
7.  **インターネット オプション**ダイアログ ボックスで、をクリックして**OK**。  
  
8.  クリックして**ファイル**、順にクリックします**閉じる**を Internet Explorer を終了します。  
  
9. をクリックして**開始**、 をクリックして**実行**、型**regedit**、順にクリックします**OK**します。  
  
10. レジストリ エディターでは、次のレジストリ キーに移動します。  
  
     **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\SystemCertificates**  
  
11. いることを確認、 **AddressBook**ハイブが存在します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server を実行しているコンピューターの復旧](../core/recovering-a-computer-running-biztalk-server.md)