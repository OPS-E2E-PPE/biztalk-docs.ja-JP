---
title: BAM イベント バス サービスのストアド プロシージャ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- stored procedures, Even Bus Service [BAM]
- Event Bus Service [BAM], stored procedures
ms.assetid: 18a7bd40-50ce-44f2-88ae-45a2e3c8d3f4
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f44dce10113b8a3a85b7c1dd177f637933b582ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230338"
---
# <a name="bam-event-bus-service-stored-procedures"></a>BAM イベント バス サービスのストアド プロシージャ
BAM イベント バス サービスの管理には、次のストアド プロシージャを使用します。  
  
-   BAM イベント バス サービスを一時停止するには、(トランザクションをコミットせずに) トランザクション内で BAM データベースに対して TDDS_BlockTDDS ストアド プロシージャを実行します。 BAM イベント バス サービスを再開するには、TDDS_BlockTDDS トランザクションをコミットします。  
  
-   複数のコンピューターで BAM イベント バス サービスを有効にするには、追跡に使用するホストを特定し、有効にする複数のコンピューターを追跡ホストに参加させます。  
  
-   セッションのタイムアウトと Heartbeat 間隔を設定するには、TDDS_UpdateSettings ストアド プロシージャを使用します。 このストアド プロシージャの実行権限は、BTS_ADMIN_USERS グループのメンバーのみに与えられています。  
  
     TDDS_UpdateSettings ストアド プロシージャには、次のパラメーターがあります。  
  
    -   @RefreshIntervalint です。60 秒を超える値を設定します。  
  
    -   @SqlCommandTimeoutint です。RefreshInterval よりも低くを設定します。  
  
    -   @SessionTimeoutint です。RefreshInterval の 2 倍よりも大きい値に設定します。  
  
    -   @EventLoggingIntervalnvarchar (16)。 60 秒を超える値を設定します。  
  
    -   @RetryCountint です。60 秒より大きい値に設定します。  
  
    -   @ThreadPerSessionint です。このパラメーターは今後使用しません。  
  
## <a name="see-also"></a>参照  
 [BAM の管理](../core/managing-bam.md)