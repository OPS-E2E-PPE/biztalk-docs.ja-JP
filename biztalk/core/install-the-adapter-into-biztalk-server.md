---
title: "BizTalk Server にアダプターのインストール |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1164468d-75a9-4116-87a6-6055948c198b
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1bc585e0574610a867d3f890ce456930bc936dd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="install-the-adapter-into-biztalk-server"></a>BizTalk Server へのアダプターのインストール
適切な [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] エントリがレジストリに書き込まれた後に、アダプターを BizTalk 管理データベースに追加する必要があります。 アダプターをこのデータベースに追加すると、アクティブに構成されたアダプターになり、正しく構成されている場合はメッセージを処理できます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用してアダプターをデータベースにインストールします。 データベース内のアダプターをインストールした後に、ホスト インスタンスを再起動します。  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで追加した内容を表示できるようにするには、アダプターを HKLM レジストリに正しく登録し、必要なアダプター インターフェイスを実装する必要があります。  
  
### <a name="to-install-the-static-sample-adapter"></a>静的なサンプル アダプターをインストールするには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。  
  
2.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをダブルクリックして、 **BizTalk グループ**ノード。  
  
3.  展開**プラットフォームの設定**選択**アダプター**です。  
  
4.  右クリック**アダプター**をクリックして**新規**、順にクリック**アダプター**です。  
  
5.  **アダプター プロパティ** ダイアログ ボックスで、次の操作です。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |名前|型**静的**です。|  
    |[アダプター]|選択**Static DotNetFile**ドロップダウン リストからです。|  
    |Description|型**静的アダプターのサンプル**です。|  
  
6.  **[OK]**をクリックします。  
  
     これで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールの右ウィンドウにあるアダプターの一覧に静的アダプターが表示されます。  
  
### <a name="to-stop-and-restart-the-host-instance"></a>停止して、ホスト インスタンスを再起動するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**です。  
  
2.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをダブルクリックして、 **BizTalk グループ**ノード。  
  
3.  展開**プラットフォームの設定****ホスト**、し、 **BizTalkServerApplication**結果ウィンドウで、します。  
  
4.  ホスト インスタンス (通常は、コンピューター名) を右クリックし、をクリックして**停止**です。  
  
     ホスト インスタンスの状態に変わる**Stopped**です。  
  
5.  結果ウィンドウで、ホスト インスタンスを右クリックし、をクリックして**開始**です。  
  
     ホスト インスタンスの状態に変わる**開始待ち**です。 クリックする必要があります**更新**、または、ホスト インスタンスを右クリックし、をクリックして**更新**に状態を変更するには、**を実行している**です。