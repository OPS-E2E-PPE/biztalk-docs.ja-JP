---
title: BAM イベント バス サービスのインスタンスを作成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 454bdde7-45a6-41ab-9196-f662273f0f2b
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba406ca55a4d317284c450262f96c06412bf8edd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389933"
---
# <a name="creating-instances-of-the-bam-event-bus-service"></a>BAM イベント バス サービスのインスタンスを作成します。
BAM イベント バス サービスは、BizTalk アプリケーション ホスト内で実行されます。 既定のホストを使用して BAM イベント バス サービスをホストするか、新しいホストを作成することができます。 あるホストが BAM イベント バス サービスをホストする場合、そのホスト用に作成する新しいインスタンスも BAM イベント バス サービスをホストします。  
  
 既定のホストについては、次を参照してください。[ホスト](../core/hosts.md)します。  
  
 ホストを作成する方法の詳細については、次を参照してください。[新しいホストを作成する方法](../core/how-to-create-a-new-host.md)します。  
  
 ホスト インスタンスを作成する方法の詳細については、次を参照してください。[ホスト インスタンスを追加する方法](../core/how-to-add-a-host-instance.md)します。  
  
 ホストおよびホスト インスタンス作成および構成については、次を参照してください。 [BizTalk ホストの管理およびホスト インスタンス](../core/managing-biztalk-hosts-and-host-instances.md)します。  
  
### <a name="to-create-the-host-that-hosts-the-bam-event-bus-service"></a>BAM イベント バス サービスをホストするホストを作成するには  
  
1. クリックして**開始**、 をポイント**すべてのプログラム**、 をクリックして**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. BizTalk 管理コンソール ウィンドウで、 **BizTalk Server 管理**ノード、展開、 **Biztalk グループ**ノードを展開し、**プラットフォームの設定**ノード、を右クリックし、**ホスト**ノードの **新規**、 をクリックし、**ホスト**。  
  
3. **ホストのプロパティ** ダイアログ ボックスで、**名前**ボックスに、ホストのわかりやすい名前を入力します。  
  
4. **全般**] タブで、[、**ホストの追跡を許可する**チェック ボックスをオンします。  
  
    新しい子ノードが表示されます、**ホスト**ノードを新しいホストの名前。  
  
5. **Windows グループ**ボックスをクリックして、このホストを割り当てる Windows グループの名前を入力**OK**します。  
  
    新しい子ノードが表示されます、**ホスト**ノードを新しいホストの名前。  
  
### <a name="to-create-a-new-host-instance-of-the-host"></a>ホストの新しいホスト インスタンスを作成するには  
  
1.  右クリックし、**ホスト インスタンス**ノードの [**新規**、] をクリックし、**ホスト インスタンス**。  
  
2.  ホスト インスタンスの実行、および順にクリックしますが、サーバーを選択して**OK**します。  
  
### <a name="to-add-hosting-tracking-to-the-host"></a>ホストの追跡をホストに追加するには  
  
1.  Reconfigure、およびクリックするホストを右クリックして**プロパティ**します。  
  
2.  **全般**] タブで [**ホストの追跡を許可する**、順にクリックします**OK**。  
  
3.  そのホストのすべてのインスタンスを再起動します。  
  
### <a name="to-remove-hosting-tracking-from-the-host"></a>ホストからホストの追跡を削除するには  
  
1.  ホストの追跡を削除するホストを右クリックし、をクリックし、**プロパティ**します。  
  
2.  クリア、**を許可するホストの追跡**チェック ボックスをオンにして**OK**。  
  
3.  そのホストのインスタンスを再起動します。  
  
## <a name="see-also"></a>参照  
 [BAM イベント バス サービスの管理](../core/managing-the-bam-event-bus-service.md)   
 [BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md)   
 [ビジネス アクティビティの監視 (BAM)](../core/business-activity-monitoring-bam.md)