---
title: MQSeries アダプターの高可用性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance, MQSeries adapters
- MQSeries adapters, availability
- MQSeries adapters, performance
- high availability, MQSeries adapters
ms.assetid: 4339b10b-b35d-47c0-b78a-c60207e06c8e
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96fb7eb3ef5d126656d3cc456206ae56feba4c23
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323755"
---
# <a name="mqseries-adapter-high-availability"></a>MQSeries アダプターの高可用性
アダプタを使用する場合は、次の方法で可用性を改善できます。  
  
- フォールト トレランスのホスティング環境のセットアップ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
- Windows は、IBM WebSphere MQ のクラスタ リングを使用します。  
  
  フォールト トレランスについては、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[BizTalk Server のサンプル アーキテクチャ](../core/sample-biztalk-server-architectures.md)と[フォールト トレランスのためのプラットフォームの計画](../core/planning-your-platform-for-fault-tolerance.md)で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。  
  
  いることを確認する、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MQSeries アダプターが MQSAgent コンポーネントのリモート インストールとの通信をネットワーク COM + アクセスを有効にしたことを確認するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と IBM WebSphere MQ がインストールされているサーバー。 ネットワーク COM + アクセスを有効にする方法の詳細については、マイクロソフト サポート技術情報の資料 817065 を参照してください。"Windows Server 2003 でネットワーク COM + アクセスを有効にする方法」でご利用いただけます[ http://go.microsoft.com/fwlink/?LinkId=196580](http://go.microsoft.com/fwlink/?LinkId=196580)します。  
  
  使用される MQSAgent (MQSAgent2) COM + アプリケーションをクラスター化する必要はありません、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MQSeries アダプター。 このコンポーネントの高可用性を実現するには、各クラスター ノードにコンポーネントをインストールします。 COM + アプリケーションが停止した場合、クライアントから次の呼び出しによって開始されます。  
  
## <a name="see-also"></a>参照  
 [MQSeries アダプターの使用](../core/using-the-mqseries-adapter.md)