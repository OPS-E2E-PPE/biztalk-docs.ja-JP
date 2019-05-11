---
title: チェックリスト:毎日のメンテナンス チェックの実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1abae6fb-abce-4f23-a07d-b32ba58cd070
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d72fdb8a52d24129c695287334af248bf3e015d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242674"
---
# <a name="checklist-performing-daily-maintenance-checks"></a>チェックリスト:毎日のメンテナンス チェックの実行
このトピックでは、いくつかの項目の状態を監視するために日常的に確認する必要がありますをについて説明します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システム。 これらのチェックの大部分を継続的に実行して、結果を最大限に活用する時間の期間にわたってアーカイブする必要があります。 可能な限りの日常的なメンテナンス チェックを自動化することをお勧めします。  
  
|手順|リファレンス|  
|-----------|---------------|  
|ハードウェア RAID (信頼性の確認) で失敗したディスクを確認します。|[ディスクの管理](http://go.microsoft.com/fwlink/?LinkId=158666)(http://go.microsoft.com/fwlink/?LinkId=158666)します。|  
|中断されたメッセージ (信頼性の確認) などの手動の介入を必要とするメッセージを確認します。|手動で中断されたメッセージのチェック方法の詳細については、次を参照してください。[調査オーケストレーション、ポート、およびメッセージ エラー](http://go.microsoft.com/fwlink/?LinkId=154512) (http://go.microsoft.com/fwlink/?LinkId=154512)します。|  
|エラーや BizTalk Server では、特にメッセージ ボックス データベースに関連付けられているさまざまなデータベースでの問題をチェックします。|使用可能な BizTalk MsgBoxViewer ツールを実行して[BizTalk MsgBoxViewer - ダウンロード、ツールの最新バージョンではここで](http://go.microsoft.com/fwlink/?LinkId=151930)(http://go.microsoft.com/fwlink/?LinkId=151930)します。 このツールは、BizTalk メッセージ ボックス データベースとその他のデータベースを分析し、html 形式のレポートが存在する場合、警告を格納していると、データベースに関連するその他の情報を生成します。 **ヒント:** 後で使用できるレポートを保存することもできます。 これらのレポートは、BizTalk アプリケーションの問題のトラブルシューティングを行う便利な可能性があります。 **注:**、Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関する保証をいたしません。 このプログラムは、ユーザー自身の責任で使用してください。|  
|BizTalk MsgBoxViewer ツールによって、識別された場合は、問題を解決します。|使用可能なターミネータ ツールを実行して[ターミネータ](http://go.microsoft.com/fwlink/?LinkId=151931)(http://go.microsoft.com/fwlink/?LinkId=151931)します。 このツールでは、簡単に BizTalk MsgBoxViewer ツールによって特定された問題を解決することができます。 BizTalk MsgBoxViewer ツールを使用して、終端記号のツールを統合する方法の詳細については、次を参照してください。 [BizTalk MsgBoxViewer によって特定された問題を解決するには BizTalk 終端記号のを使用して](http://go.microsoft.com/fwlink/?LinkId=151932)(http://go.microsoft.com/fwlink/?LinkId=151932)します。 **注:**、Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関する保証をいたしません。 このプログラムは、ユーザー自身の責任で使用してください。|  
|イベント ログでエラーと警告 (管理のチェック) を確認します。|BizTalk Server のエラーと警告イベントは、アプリケーション ログに保存されます。 イベント ソースが"BizTalk Server です"|  
  
## <a name="see-also"></a>参照  
 [信頼性の維持](../technical-guides/maintaining-reliability.md)   
 [BizTalk Server2 の監視](../technical-guides/monitoring-biztalk-server2.md)