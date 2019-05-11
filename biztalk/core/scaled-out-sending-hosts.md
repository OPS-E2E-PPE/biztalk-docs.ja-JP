---
title: スケール アウトされた送信ホスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- hosts, sending
- FTP adapters, high availability
- EDI adapters, high availability
- hosts, high availability
- hosts, availability
- Windows SharePoint Services adapters, high availability
- scaling, hosts
- hosts, clustering
- scaling, adapters
- high availability, hosts
- clustering, hosts
- MSMQ adapters, high availability
- hosts, planning
- hosts, scaling
- adapters, scaling
ms.assetid: a3d79e0b-8c1e-471c-88e2-623600dfd81a
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80fcc73aa4d0f2d65a097bd47d06fc75305abdc3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65309066"
---
# <a name="scaled-out-sending-hosts"></a>スケール アウトされた送信ホスト
スケール アウトされた送信ホストにより、送信機能に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は高可用性。 メッセージを送信するために、ホストを複数のコンピューターを追加する場合は、冗長性と高可用性のための複数の送信元ホスト インスタンスを実行できます。  
  
 次に示します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]展開を送信ホストのインスタンスを実行する 2 台のコンピューターを使用して、送信ホストの高可用性を実現します。 この図では、受信および処理ホストができないこと高可用性に注意してください。  
  
 ![スケール&#45;ホストの送信が](../core/media/tdi-ha-scalesend.gif "TDI_HA_ScaleSend")  
  
## <a name="high-availability-for-sending-hosts"></a>送信ホストの高可用性  
 送信機能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]はどちらもこれらのアクティビティのホストとデータの関連付けが必要であるという意味で処理機能に似ています。 処理ホスト インスタンスでは、メッセージ ボックス データベースからメッセージを取得でき、それらを処理することと同様、送信ホスト インスタンスもはメッセージ ボックス データベースからメッセージを取得し、送ります。 そのため、送信ホストの高可用性を実現するには、処理ホストの高可用性を実現する場合と同じ手法を使用することを意味します。  
  
## <a name="scaling-the-biztalk-server-send-adapters"></a>BizTalk Server 送信アダプターの拡張  
  
### <a name="high-availability-for-the-msmq-send-adapter"></a>送信アダプター、MSMQ 用の高可用性  
 MSMQ サービスをクラスター化、クラスターのクラスター化された MSMQ サービスと同じグループ内の BizTalk ホストおよび構成する必要があります、MSMQ 送信アダプターの高可用性を実現するには、MSMQ の送信ハンドラーをこのクラスター化された BizTalk ホストで実行します。 これは、MSMQ アダプターによって開始されたトランザクションの送信の一貫性を確保する実行する必要があります。 詳細については、次を参照してください。[されたクラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)します。  
  
### <a name="high-availability-for-the-windows-sharepoint-services-send-adapter"></a>送信アダプター、Windows SharePoint Services の高可用性  
 Windows SharePoint Services 送信アダプターの高可用性を実現するには、同じドキュメント ライブラリを参照する各ホスト コンピューター上の送信ポートで送信ホストに複数のコンピューターを追加します。 Windows SharePoint Services アダプターは、SharePoint コンピューターに BizTalk によってインストールされた Windows SharePoint Services web サービスを呼び出すことによって、SharePoint にメッセージを送信します。 BizTalk Server は、SharePoint の NLB 環境を指す HTTP URL を同じメッセージをプッシュする複数のホスト インスタンスで同じ送信ポートを実行することによって、SharePoint 受信アダプターの高可用性を提供します。  
  
## <a name="see-also"></a>参照  
 [BizTalk ホストの高可用性を実現します。](../core/providing-high-availability-for-biztalk-hosts.md)   
 [クラスター化されたホストでのアダプター ハンドラーの実行に関する注意点](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)