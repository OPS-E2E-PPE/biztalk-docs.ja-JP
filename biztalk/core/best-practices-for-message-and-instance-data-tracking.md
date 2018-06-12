---
title: メッセージとインスタンス データ追跡のベスト プラクティス |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HAT, best practices
- best practices, HAT
ms.assetid: 2ac5c87b-2059-4912-9cec-2ae4eaac56df
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 680958d2950edffeaa56c7c3b8d7f8da40967173
ms.sourcegitcommit: 3371ffd8ceca02e2b3715d53a1e0c0a59045912e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2018
ms.locfileid: "34849018"
---
# <a name="best-practices-for-message-and-instance-data-tracking"></a>メッセージとインスタンス データ追跡のベスト プラクティス
履歴および追跡データを使用するためのベスト プラクティスを次に示します。  
  
-   **履歴および追跡データを使用するセキュリティの考慮事項を確認します。**  
  
    -   履歴および追跡データのセキュリティに関する考慮事項の詳細については、次を参照してください。[メッセージとインスタンス データ追跡のセキュリティに関する考慮事項](../core/security-considerations-for-message-and-instance-data-tracking.md)です。  
  
-   **すべてのメッセージ ボックス データベースで SQL Server エージェント サービスが実行されていることを確認してください。**  
  
    -   SQL Server エージェントは、メッセージ本文を WMI、および履歴データや追跡データで使用できるようにします。 これにより、ジョブを実行してメッセージ ボックス データベースをクリーンアップできます。 SQL Server エージェントの詳細については、SQL Server Books Online を参照してください。  
  
-   **メッセージ本文の追跡を有効にします。**  
  
    -   サービス インスタンスの処理が完了した後にメッセージを保存するには、メッセージ本文の追跡が必要です。  
  
-   **必要に応じて、ビジネス ニーズに追跡を構成します。**  
  
    -   履歴データおよび追跡データを表示するためには、BizTalk Server 管理コンソールを使用して追跡を構成しておく必要があります。 追跡オプションを有効または無効にする場合は、いくつかの注意事項があります。 追跡するデータが多いと、それだけ早く、BizTalk 追跡 (BizTalkDTADb) データベースのサイズが肥大化し、実行時のパフォーマンスに悪影響が生じます。 詳細については、次を参照してください。 [、BizTalk Server 管理コンソールを使用した追跡構成](http://msdn.microsoft.com/49b7f9d3-60b5-41bd-ba8b-029253926bef)です。  
  
-   **適切なトラブルシューティングのための追跡の種類を選択または監査**  
  
    -   開発環境またはステージング/実稼働環境でトラブルシューティングを行う場合は、アイテム イベント、メッセージのプロパティ、メッセージ本文、オーケストレーションのイベントを詳細に確認できるよう、追跡オプションをすべて有効にすることをお勧めします。 これにより、システムの一連のイベントを作成し直したり、アプリケーションをデバッグできるだけの十分な追跡情報を得ることができます。  
  
    -   実稼働レベルの監査を行う場合は、監査対象のイベントを慎重に選びながら、本当に必要なイベントについてのみ追跡を有効にします。 たとえば、多くの企業は、メッセージが入力し、システムを終了したことを証明するためにできるようにします。 そのためには、受信ポートと送信ポートで、それぞれ対応する受信メッセージと送信メッセージの追跡を有効にする必要があります。 必要であれば、メッセージ プロパティやメッセージ本文を追跡することもできます。  
  
    -   主要業績評価指標 (KPI) を評価したり、特定のビジネス マイルストーンの達成度に基づいて進捗状況を評価したりする場合は、ビジネス アクティビティ監視 (BAM) 追跡を使用する必要があります。 BAM 追跡ではメッセージ本文を追跡する機能が限られているため、BAM 追跡が必要な場合は、履歴データと追跡データを組み合わせて使用することをお勧めします。 BAM 追跡の詳細については、次を参照してください。[を使用したビジネス アクティビティ監視](../core/using-business-activity-monitoring.md)です。  
  
-   **アーカイブおよびを定期的に BizTalk 追跡 (BizTalkDTADb) データベースからデータを消去**  
  
    -   追跡を有効にする場合は、データベースのサイズが大きくなりすぎないように、BizTalk 追跡データベースのデータを定期的にアーカイブ/削除する必要があります。これにより、システムのパフォーマンスを最適な状態に維持することができます。 詳細については、次を参照してください。[アーカイブ化および BizTalk 追跡データベースを削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)です。  
  
## <a name="see-also"></a>参照  
 [追跡メッセージおよびインスタンス データの表示](../core/viewing-tracked-message-and-instance-data.md)