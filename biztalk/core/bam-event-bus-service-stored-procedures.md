---
title: BAM イベント バス サービスのストアド プロシージャ |Microsoft Docs
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
ms.openlocfilehash: 138ca26becc8b35207219dd050e13c8557066301
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358523"
---
# <a name="bam-event-bus-service-stored-procedures"></a>BAM イベント バス サービスのストアド プロシージャ
BAM イベント バス サービスを管理するのにには、次のストアド プロシージャを使用します。  
  
-   BAM イベント バス サービスを一時停止するには、BAM データベースで (トランザクションのコミット) なしのトランザクション内でに対して TDDS_BlockTDDS ストアド プロシージャを実行します。 BAM イベント バス サービスを再開するには、TDDS_BlockTDDS トランザクションをコミットします。  
  
-   複数のコンピューターで BAM イベント バス サービスを有効にするには、追跡に使用するホストを特定し、追跡ホストにこれらのコンピューターを参加します。  
  
-   セッション タイムアウトと heartbeat 間隔を設定するには、TDDS_UpdateSettings ストアド プロシージャを使用します。 BTS_ADMIN_USERS グループのメンバーだけでは、このストアド プロシージャを実行する権限があります。  
  
     TDDS_UpdateSettings ストアド プロシージャでは、次のパラメーターがあります。  
  
    -   @RefreshInterval int です。60 秒以上に設定します。  
  
    -   @SqlCommandTimeout int です。RefreshInterval よりも小さくを設定します。  
  
    -   @SessionTimeout int です。RefreshInterval の 2 倍よりも大きい値に設定します。  
  
    -   @EventLoggingInterval nvarchar (16)。 60 秒以上に設定します。  
  
    -   @RetryCount int です。60 秒以上に設定します。  
  
    -   @ThreadPerSession int です。このパラメーターは廃止されています。  
  
## <a name="see-also"></a>参照  
 [BAM の管理](../core/managing-bam.md)