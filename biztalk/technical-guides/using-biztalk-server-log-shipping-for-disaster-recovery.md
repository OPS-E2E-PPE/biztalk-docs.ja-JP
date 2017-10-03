---
title: "BizTalk Server のログ配布災害復旧を使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5d65015c-de53-4590-b644-5c2f66f763db
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16f2cf9e1d8b717ff42536ef9c0dba79132b9663
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-biztalk-server-log-shipping-for-disaster-recovery"></a>BizTalk Server のログ配布災害復旧を使用します。
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実装してデータベースのデータベースを使用してスタンバイ機能ログ配布します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ログ配布は、スタンバイ サーバーで実稼働データベース サーバーが失敗した場合に、データベース処理を再開できるように、データベースとトランザクション ログ ファイルの復元とバックアップを自動化します。  
  
## <a name="how-log-shipping-works"></a>どのログ配布のしくみ  
 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]によって使用されるエージェント ジョブ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]のログ配布は、実稼働環境で使用されている移行元サーバーと既定 (BizTalk Server のバックアップ ジョブで実行するすべての時刻) では 15 分ごと、スタンバイ状態として使用する移行先サーバー間でデータを同期します。  
  
## <a name="using-log-shipping-for-disaster-recovery"></a>ログ配布の障害復旧の使用  
 使用する場合、次の操作を[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ログ災害復旧のための配布。  
  
-   トピックの手順に従って[チェックリスト: 可用性と災害復旧を増やす](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)、稼働環境の可用性を向上させる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]災害復旧を使用して環境。  
  
-   障害回復サーバーに実稼働負荷を処理する能力があることを確認します。  
  
     スタンバイ サーバーが、同一または類似した使用可能なリソース (CPU とメモリまたはディスク) として、実稼働サーバーであることを確認します。  
  
-   災害復旧ルーチンの詳細が明確になっていることを確認します。  
  
     障害復旧の準備、実装の詳細のすべてのステップを文書化します。 ストライキ都合の良いときが障害復旧手順を実装する責任者が、最初の曜日を開始するいると仮定ため頻度の低い災害は作業し、初めてこれでは。  
  
-   障害復旧サイトに通常のテスト、プラクティス フェールオーバーの一環として、新しい BizTalk として特にアプリケーションが配置実稼働環境でします。  
  
     正規のテストとスムーズに実行できることができることを確認するためのメンテナンスの一環としてテスト フェールオーバーを実行します。  
  
## <a name="see-also"></a>参照  
 [災害復旧](../technical-guides/disaster-recovery.md)