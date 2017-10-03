---
title: "スケール アウトされた送信ホスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1fb8ac3fe3752702ed3e1aa2795e521d7173618
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="scaled-out-sending-hosts"></a>送信ホストのスケールアウト
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の送信機能に高い可用性を確保するには、送信ホストをスケールアウトします。 メッセージを送信するためのホストにコンピューターを追加し、複数の送信ホスト インスタンスを実行することによって冗長性と可用性を高めることができます。  
  
 次の図は、送信ホストのインスタンスを実行する 2 台のコンピューターを使用して、送信ホストの高可用性を実現した [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境を示しています。 この図に示されている受信ホストおよび処理ホストの可用性は高くないことに注意してください。  
  
 ![スケーリング &#45; ホストの送信が](../core/media/tdi-ha-scalesend.gif "TDI_HA_ScaleSend")  
  
## <a name="high-availability-for-sending-hosts"></a>送信ホストの高可用性  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の送信機能は、ホストとデータを完全に切り離して捉えることができるという意味で処理機能に似ています。 処理の対象となるメッセージをメッセージ ボックス データベースから取得する処理ホスト インスタンスと同様に、送信ホスト インスタンスも、送信するメッセージをメッセージ ボックス データベースから取得します。 したがって、送信ホストの高可用性を実現する際は、処理ホストの高可用性を実現するときと同じ手法を使用できることになります。  
  
## <a name="scaling-the-biztalk-server-send-adapters"></a>BizTalk Server 送信アダプターの拡張  
  
### <a name="high-availability-for-the-msmq-send-adapter"></a>MSMQ 送信アダプターの高可用性  
 MSMQ 送信アダプターの高可用性を確保するためには、MSMQ サービスをクラスター化し、このクラスター化した MSMQ サービスと同じグループとなるように BizTalk ホストをクラスター化して構成します。さらに、MSMQ 送信ハンドラーが、このクラスター化された BizTalk ホストで実行されるように構成する必要があります。 MSMQ アダプターによって開始されたトランザクションの送信の一貫性を確保するは、これを行う必要があります。 詳細については、次を参照してください。[化されたクラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)です。  
  
### <a name="high-availability-for-the-windows-sharepoint-services-send-adapter"></a>Windows SharePoint Services 送信アダプターの高可用性  
 Windows SharePoint Services 送信アダプターに高可用性を確保するには、送信ホストに複数のコンピューターを追加し、各ホスト コンピューターの送信ポートで、同じドキュメント ライブラリが参照されるように構成します。 Windows SharePoint Services アダプターは、SharePoint コンピューターに BizTalk がインストールされている Windows SharePoint Services web サービスを呼び出すことによって SharePoint にメッセージを送信します。 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]SharePoint の NLB 環境を指す HTTP URL に同じメッセージをプッシュする複数のホスト インスタンスで、同じ送信ポートを実行することによって、SharePoint 受信アダプターの高可用性を提供します。  
  
## <a name="see-also"></a>参照  
 [BizTalk ホストの高可用性を実現します。](../core/providing-high-availability-for-biztalk-hosts.md)   
 [クラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)