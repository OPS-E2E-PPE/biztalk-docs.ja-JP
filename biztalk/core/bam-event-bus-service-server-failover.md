---
title: BAM イベント バス サービス サーバーのフェールオーバー |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f12378c8-09bb-45c1-ade1-d9b20131461f
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c1fafc3e97d9905a6efd0de8ff0f389c2a389bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230642"
---
# <a name="bam-event-bus-service-server-failover"></a>BAM イベント バス サービス サーバーのフェールオーバー
BAM イベント バス サービスには、予期しない障害が発生した場合にデータを失わずに復旧して再起動するためのフォールト トレランス ロジックが含まれています。  
  
 複数のコンピューター上で BAM イベント バス サービスが有効になっている状態でサービスが失敗した場合、フェールオーバーのロジックでは BAM イベント バス サービスが停止したことが検出され、BAM イベント バス サービスの新しいインスタンスが自動的に別のコンピューター上で開始されます。  
  
 BAM イベント バスが単純な負荷分散によってコンピューターまたはネットワークの障害を処理する方法を、次の図に示します。 BAM イベント バス サービスの開始前には、2 つの送信元と 1 つの送信先が構成されています。  
  
 ![](../core/media/ebiz-bam-admin-evntbuspoolfail.gif "ebiz_bam_admin_evntbuspoolfail")  
BAM イベント バス サービスによる負荷分散の方法  
  
 BAM イベント バス サービスによる負荷分散は、次のようにして行われます。  
  
-   **A: Server1 は 2 つのソース (セッション) からイベント データを処理**です。 BAM イベント バス サービスのインスタンスがサーバー 2 で作成される前に、BAM イベント バス オーケストレーション インスタンスがサーバー 1 で作成されます。 サーバーは他に利用できるサービスがないことを検出し、Src1 および Src2 の両方のセッションを取得します。  
  
-   **B: Server2 がオンラインになり、BAM イベント バス プールに参加**です。 BAM イベント バス サービスがサーバー 2 で作成された後、サーバー 1 が 1 つの BAM イベント バス サービス セッションをドロップし、サーバー 2 がそれを取得します。  
  
-   **C: Server1 失敗**です。 サーバー 2 が BAE イベント バス プールに参加した後、サーバー 1 が失敗します。  
  
-   **D: server2 という 2 つのソース (セッション) からのイベント データを処理する**です。 サーバー 2 が、Src1 および Src2 の両方のセッションを取得します。  
  
## <a name="see-also"></a>参照  
 [BAM イベント バス サービスを管理します。](../core/managing-the-bam-event-bus-service.md)   
 [BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md)   
 [ビジネス アクティビティ監視 (BAM)](../core/business-activity-monitoring-bam.md)