---
title: "証明書ストアを復元する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0c6f7551-d119-4668-9b52-6013f69a0302
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aaeee6b762cf5af15ca7cba34864abd86682d4df
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-restore-the-certificate-store"></a>証明書ストアを復元する方法
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の復旧処理の一環として、証明書ストアを復元する必要があります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Standard Edition を復旧する場合は、この手順を使用して証明書ストアを復元する必要があります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の他のすべてのエディションを復旧する場合は、復旧処理によって自動的に証明書ストアが復元されるため、この手順を実行する必要はありません。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、管理者グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-restore-the-certificate-store-biztalk-server-standard-edition"></a>証明書ストアを復元するには (BizTalk Server Standard Edition)  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、クリックして**Internet Explorer**です。  
  
2.  **ツール** メニューのをクリックして**インターネット オプション**です。  
  
3.  **インターネット オプション** ダイアログ ボックスをクリックして、**コンテンツ** タブをクリックして**証明書**です。  
  
4.  **証明書** ダイアログ ボックスをクリックして、**ほかの人** タブをクリックして**インポート**です。  
  
5.  **証明書のインポート ウィザード**をクリックして**キャンセル**です。  
  
     これを作成、 **AddressBook**レジストリ ハイブです。  
  
6.  **証明書**ダイアログ ボックスで、をクリックして**閉じる**です。  
  
7.  **インターネット オプション**ダイアログ ボックスで、をクリックして**OK**です。  
  
8.  をクリックして**ファイル**、順にクリック**閉じる**を Internet Explorer を終了します。  
  
9. をクリックして**開始**、 をクリックして**実行**、型**regedit**、順にクリック**ok**です。  
  
10. レジストリ エディターで、次のレジストリ キーに移動します。  
  
     **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\SystemCertificates**  
  
11. いることを確認、 **AddressBook**ハイブが存在します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server を実行しているコンピューターの回復](../core/recovering-a-computer-running-biztalk-server.md)