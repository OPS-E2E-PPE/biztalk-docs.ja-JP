---
title: "チェックリスト: メンテナンスを毎日チェックを実行する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1abae6fb-abce-4f23-a07d-b32ba58cd070
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 281f33f0d880fdd217f3cac303526d7cfc0802f7
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="checklist-performing-daily-maintenance-checks"></a>チェックリスト: メンテナンスを毎日チェックを実行します。
このトピックの状態を監視するために日常的に確認する必要があります、項目の説明、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システムです。 一貫してこれらのチェックのほとんどを行うし、結果を最大限に活用する時間の期間にわたってアーカイブする必要があります。 可能な限り、定期的なメンテナンスのチェックを自動化することをお勧めします。  
  
|手順|リファレンス|  
|-----------|---------------|  
|ハードウェア RAID (信頼性チェック) で失敗したディスクを確認します。|[ディスクの管理](http://go.microsoft.com/fwlink/?LinkId=158666)(http://go.microsoft.com/fwlink/?LinkId=158666)。|  
|中断されたメッセージ (信頼性を確認) などの手動による介入を必要とするメッセージを確認します。|手動で中断されたメッセージの確認方法については、次を参照してください。[調査オーケストレーション、ポート、およびメッセージ エラー](http://go.microsoft.com/fwlink/?LinkId=154512) (http://go.microsoft.com/fwlink/?LinkId=154512)。|  
|エラーまたは BizTalk Server では、特にメッセージ ボックス データベースに関連付けられているさまざまなデータベースでの問題を確認します。|BizTalk MsgBoxViewer ツールから利用可能な実行[ここで、ツールの最新バージョンをダウンロード BizTalk MsgBoxViewer -](http://go.microsoft.com/fwlink/?LinkId=151930) (http://go.microsoft.com/fwlink/?LinkId=151930)。 このツールは、BizTalk メッセージ ボックス データベースとその他のデータベースを分析し、存在する場合、警告を含む html 形式のレポートと、データベースに関連するその他の情報を生成します。 **ヒント:**後で使用できるレポートを保存することもできます。 これらのレポートは、BizTalk アプリケーションの問題のトラブルシューティングを行うときに役立ちます可能性があります。 **注:** Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関して保証を行いません。 このプログラムは、ユーザー自身の責任で使用してください。|  
|BizTalk MsgBoxViewer ツールによって、識別された場合は、問題を解決します。|使用可能なターミネータ ツールを実行して[ターミネータ](http://go.microsoft.com/fwlink/?LinkId=151931)(http://go.microsoft.com/fwlink/?LinkId=151931)。 このツールでは、簡単に BizTalk MsgBoxViewer ツールによって識別される問題を解決することができます。 ターミネータ ツールが、BizTalk MsgBoxViewer ツールと統合する方法の詳細については、次を参照してください。 [BizTalk MsgBoxViewer によって特定された問題を解決するには BizTalk のターミネータを使用して](http://go.microsoft.com/fwlink/?LinkId=151932)(http://go.microsoft.com/fwlink/?LinkId=151932)。 **注:** Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関して保証を行いません。 このプログラムは、ユーザー自身の責任で使用してください。|  
|イベント ログでエラーと警告 (管理チェック) を確認してください。|BizTalk Server のエラーと警告イベントは、アプリケーション ログに保存されます。 イベント ソースが"BizTalk Server です"|  
  
## <a name="see-also"></a>参照  
 [信頼性を維持します。](../technical-guides/maintaining-reliability.md)   
 [BizTalk Server2 の監視](../technical-guides/monitoring-biztalk-server2.md)