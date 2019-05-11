---
title: BizTalk Server ログ配布のディザスター リカバリーを使用して |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d65015c-de53-4590-b644-5c2f66f763db
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9dc2ab707bb4620fdb4b45db2750514758f21300
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400357"
---
# <a name="using-biztalk-server-log-shipping-for-disaster-recovery"></a>BizTalk Server ログ配布のディザスター リカバリーを使用します。
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 実装は、データベースを使用してスタンバイの機能をデータベース ログ配布します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ログ配布は、バックアップと、スタンバイ サーバー データベースが実稼働データベース サーバーが失敗したことに処理を再開できるように、データベースとトランザクション ログ ファイルの復元を自動化します。  
  
## <a name="how-log-shipping-works"></a>どのログ配布のしくみ  
 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]によって使用されるエージェント ジョブ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]のログ配布は、実稼働環境で使用するソース サーバーと (BizTalk Server のバックアップ ジョブで実行するすべての時刻) を既定で 15 分ごと、スタンバイ状態として使用する移行先サーバーの間でデータを同期します。  
  
## <a name="using-log-shipping-for-disaster-recovery"></a>ディザスター リカバリーのログ配布を使用します。  
 使用する場合、次の操作[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ログ ディザスター リカバリーのための配布。  
  
- トピックの手順に従って[チェックリスト。ディザスター リカバリーによる可用性の向上](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)、運用環境の可用性を向上させる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ディザスター リカバリーを使用して環境。  
  
- ディザスター リカバリー server に運用環境の負荷を処理する能力があることを確認します。  
  
   スタンバイ サーバーに、同じまたは類似した使用可能なリソース (CPU/メモリ/ディスク) として、運用サーバーがあることを確認します。  
  
- ディザスター リカバリ ルーチンの詳細がも記載されていることを確認します。  
  
   障害復旧の準備、実装の詳細の各手順を文書化します。 Strikes 都合の良いときがディザスター リカバリーの手順を実装するために必要な責任は、最初の日の開始されていると仮定ため頻度の低いディザスターは動作し、最初にこれが。  
  
- ディザスター リカバリー サイトに通常のテスト、実際にフェールオーバーの一環として、新しい BizTalk として特にアプリケーションが配置実稼働環境でします。  
  
   通常のテストとスムーズに実行することができますを確認するためのメンテナンスの一部としてテスト フェールオーバーを実行します。  
  
## <a name="see-also"></a>参照  
 [ディザスター リカバリー](../technical-guides/disaster-recovery.md)