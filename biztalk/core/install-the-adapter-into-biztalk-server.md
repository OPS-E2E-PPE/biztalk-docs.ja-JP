---
title: BizTalk Server にアダプターのインストール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1164468d-75a9-4116-87a6-6055948c198b
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8d6093776f0359e79731a3ba273e319e7cd3765
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332020"
---
# <a name="install-the-adapter-into-biztalk-server"></a>BizTalk Server にアダプターをインストールします。
適切な後[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アダプターは BizTalk 管理データベースに追加する必要があります、レジストリに書き込まれたエントリ。 アダプターがこのデータベースに追加された後アダプターがアクティブに構成されているが正しく構成されている場合、メッセージを処理できます。 使用して、データベースにアダプターをインストールする、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 データベースにアダプターをインストールした後、ホスト インスタンスを再起動します。  

> [!NOTE]
>  追加するために表示される、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、アダプターが、HKLM レジストリに正しく登録されている必要があり、必要なアダプター インターフェイスを実装する必要があります。  

### <a name="to-install-the-static-sample-adapter"></a>サンプルの静的アダプターをインストールするには  

1. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。  

2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、ダブルクリックして、 **BizTalk グループ**ノード。  

3. 展開**プラットフォームの設定**選択**アダプター**します。  

4. 右クリック**アダプター**、 をクリックして**新規**、 をクリックし、**アダプター**します。  

5. **アダプター プロパティ** ダイアログ ボックスで、次の操作を行います。  


   |  プロパティ   |                      目的                       |
   |-------------|-------------------------------------------------------|
   |    名前     |                   型**静的**します。                    |
   |   [アダプター]   | 選択**Static dotnetfile**ドロップダウン リストから。 |
   | 説明 |            型**静的アダプターのサンプル**します。            |


6. **[OK]** をクリックします。  

    静的アダプターの右側のウィンドウにあるアダプターの一覧が表示されます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  

### <a name="to-stop-and-restart-the-host-instance"></a>停止して、ホスト インスタンスを再起動するには  

1. クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**します。  

2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、ダブルクリックして、 **BizTalk グループ**ノード。  

3. 展開**プラットフォームの設定**を選択します**ホスト**、し、 **BizTalkServerApplication**結果ウィンドウでします。  

4. ホスト インスタンス (通常は、コンピューター名) を右クリックし、をクリックし、**停止**します。  

    ホスト インスタンスの状態に変わる**Stopped**します。  

5. 結果ウィンドウで、ホスト インスタンスを右クリックし をクリックし、**開始**します。  

    ホスト インスタンスの状態に変わる**開始待ち**します。 クリックする必要があります**更新**、またはホスト インスタンスを右クリックし、をクリックし、**更新**に状態を変更するには、**を実行している**します。