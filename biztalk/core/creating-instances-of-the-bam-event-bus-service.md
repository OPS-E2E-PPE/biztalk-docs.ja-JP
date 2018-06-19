---
title: BAM イベント バス サービスのインスタンスを作成する |Microsoft ドキュメント
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
ms.openlocfilehash: afbe8f2e70baa3a963150991ced54a9d38adba88
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238418"
---
# <a name="creating-instances-of-the-bam-event-bus-service"></a>BAM イベント バス サービスのインスタンスを作成します。
BAM イベント バス サービスは、BizTalk アプリケーション ホスト内で実行されます。 既定のホストを使用して BAM イベント バス サービスをホストするか、新しいホストを作成することができます。 あるホストが BAM イベント バス サービスをホストする場合、そのホスト用に作成する新しいインスタンスも BAM イベント バス サービスをホストします。  
  
 既定のホストについては、次を参照してください。[ホスト](../core/hosts.md)です。  
  
 ホストの作成方法の詳細については、次を参照してください。[を新しいホストを作成する方法](../core/how-to-create-a-new-host.md)です。  
  
 ホスト インスタンスを作成する方法の詳細については、次を参照してください。[ホスト インスタンスを追加する方法](../core/how-to-add-a-host-instance.md)です。  
  
 作成して、ホストとホスト インスタンスの構成については、次を参照してください。[を管理する BizTalk ホストとホスト インスタンス](../core/managing-biztalk-hosts-and-host-instances.md)です。  
  
### <a name="to-create-the-host-that-hosts-the-bam-event-bus-service"></a>BAM イベント バス サービスをホストするホストを作成するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をクリックして**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  BizTalk 管理コンソール ウィンドウで、 **BizTalk Server 管理コンソール** ノードを展開、 **Biztalk グループ**ノードを展開し、**プラットフォームの設定**ノード、を右クリックし、**ホスト**ノードで、選択**新規**、クリックして**ホスト**です。  
  
3.  **ホストのプロパティ** ダイアログ ボックスで、**名前**ボックスには、ホストのわかりやすい名前を入力します。  
  
4.  **全般**] タブで、[、**ホストの追跡を許可する**チェック ボックスをオンします。  
  
     新しい子ノードが表示されます、**ホスト**新しいホストの名前を持つノード。  
  
5.  **Windows グループ**ボックスに、このホストを割り当てるし、をクリックする Windows グループの名前を入力**OK**です。  
  
     新しい子ノードが表示されます、**ホスト**新しいホストの名前を持つノード。  
  
### <a name="to-create-a-new-host-instance-of-the-host"></a>ホストの新しいホスト インスタンスを作成するには  
  
1.  右クリックし、**ホスト インスタンス**ノードで、選択**新規**、クリックして**ホスト インスタンス**です。  
  
2.  サーバーは、ホスト インスタンスの実行、およびをクリックしての位置を選択して**OK**です。  
  
### <a name="to-add-hosting-tracking-to-the-host"></a>ホストの追跡をホストに追加するには  
  
1.  Reconfigure、およびをクリックするホストを右クリックして**プロパティ**です。  
  
2.  **全般**] タブで [**ホストの追跡を許可する**、順にクリック **[ok]** です。  
  
3.  そのホストのすべてのインスタンスを再起動します。  
  
### <a name="to-remove-hosting-tracking-from-the-host"></a>ホストからホストの追跡を削除するには  
  
1.  ホストの追跡を削除するホストを右クリックし、をクリックして**プロパティ**です。  
  
2.  クリア、**を許可するホストの追跡**チェック ボックスをクリックして**OK**です。  
  
3.  そのホストのインスタンスを再起動します。  
  
## <a name="see-also"></a>参照  
 [BAM イベント バス サービスを管理します。](../core/managing-the-bam-event-bus-service.md)   
 [BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md)   
 [ビジネス アクティビティ監視 (BAM)](../core/business-activity-monitoring-bam.md)