---
title: BAM イベント バス サービス サーバーのフェールオーバー |Microsoft Docs
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
ms.openlocfilehash: ca99e507e5f0344f7991a6e6b3c7798fb309dad4
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530596"
---
# <a name="bam-event-bus-service-server-failover"></a>BAM イベント バス サービス サーバーのフェールオーバー
BAM イベント バス サービスには、予期しない障害が発生した場合にデータを失わずに復旧して再起動するためのフォールト トレランス ロジックが含まれています。  
  
 複数のコンピューターで BAM イベント バス サービスを有効にするし、サービスが失敗した場合、フェールオーバーのロジックは、BAM イベント バス サービスが終了すると、そのロジックでは、別のコンピューターで、BAM イベント バス サービスの新しいインスタンスを自動的に開始に検出されます。  
  
 次の図は、BAM イベント バスがコンピューターでどのように処理する方法を示します。 またはネットワーク障害によって、単純な負荷を分散します。 2 つのソースと変換先の 1 つは、BAM イベント バス サービスの開始前に構成されました。  
  
 ![](../core/media/ebiz-bam-admin-evntbuspoolfail.gif "ebiz_bam_admin_evntbuspoolfail")  
BAM イベント バス サービスの負荷を分散する方法  
  
 BAM イベント バス サービスの負荷は、次を実行することによって残高します。  
  
-   **A:2 つのソース (セッション) からイベント データを処理する Server1**します。 Server2 で BAM イベント バス サービスのインスタンスを作成すると、前に、BAM イベント バス オーケストレーション インスタンスはサーバー 1 で作成します。 サーバーが検出されるその他のサーバー、およびそのため Src1 および Src2 の両方のセッションを取得します。  
  
-   **B:Server2 がオンラインになり、BAM イベント バス プールに参加**します。 Server2 で BAM イベント バス サービスのインスタンスが作成されると、Server1 は、1 つの BAM イベント バス サービス セッションを削除し、Server2 ピックアップします。  
  
-   **C:サーバー 1 が失敗**します。 Server1 は、Server2 BAM イベント バス プールに参加した後に失敗します。  
  
-   **D:Server2 という 2 つのソース (セッション) からイベント データを処理する**します。 Server2 では、Src1 および Src2 の両方のセッションを取得します。  
  
## <a name="see-also"></a>参照  
 [BAM イベント バス サービスの管理](../core/managing-the-bam-event-bus-service.md)   
 [BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md)   
 [ビジネス アクティビティの監視 (BAM)](../core/business-activity-monitoring-bam.md)