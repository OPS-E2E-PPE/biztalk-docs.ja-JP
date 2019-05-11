---
title: メッセージとインスタンス データ追跡のベスト プラクティス |Microsoft Docs
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
ms.openlocfilehash: 8415547ec5f4300a89d8a96ffc3ee78325c7c57d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358195"
---
# <a name="best-practices-for-message-and-instance-data-tracking"></a>メッセージとインスタンス データ追跡のベスト プラクティス
履歴および追跡データを使用するための次のベスト プラクティスを確認します。  
  
-   **履歴および追跡データを使用するセキュリティの考慮事項を確認してください。**  
  
    -   履歴および追跡データのセキュリティに関する考慮事項の詳細については、次を参照してください。[メッセージとインスタンス データ追跡のセキュリティに関する考慮事項](../core/security-considerations-for-message-and-instance-data-tracking.md)します。  
  
-   **すべてのメッセージ ボックス データベースで SQL Server エージェント サービスが実行されていることを確認します。**  
  
    -   SQL Server エージェントでは、WMI、および履歴および追跡データに使用可能なメッセージ本文を使用します。 これにより、メッセージ ボックス データベースをクリーンアップするジョブを実行することができます。 SQL Server エージェントの詳細については、SQL Server オンライン ブックを参照してください。  
  
-   **メッセージ本文の追跡を有効にします。**  
  
    -   本文の追跡は、サービス インスタンスの処理後のメッセージを保存するために必要なメッセージが完了しました。  
  
-   **お客様のビジネス ニーズに応じて追跡を構成します。**  
  
    -   履歴および追跡データを表示するには、最初、BizTalk Server 管理コンソールを使用して追跡を構成する必要があります。 有効化または追跡オプションを無効にするときに考慮すべき事項は複数あります。 多くのデータを追跡する、高速、BizTalk 追跡 (BizTalkDTADb) データベース サイズが大きく、実行時のパフォーマンスに悪影響をします。 詳細については、次を参照してください。 [、BizTalk Server 管理コンソールを使用した追跡構成](http://msdn.microsoft.com/49b7f9d3-60b5-41bd-ba8b-029253926bef)します。  
  
-   **適切なトラブルシューティングのための追跡の種類を選択または監査**  
  
    -   アイテム イベント、メッセージのプロパティ、メッセージ本文、およびオーケストレーション イベントの詳細が表示されるよう、開発環境またはステージング環境または運用環境でのいずれかをトラブルシューティングするには、すべての追跡オプションを有効する必要があります。 これは、システムのイベントのシーケンスを再作成し、アプリケーションのデバッグに使用できる追跡情報の豊富なセットを提供します。  
  
    -   実稼働レベルの監査、監査イベントについてのみ追跡を有効にするイベントを慎重に選択します。 たとえば、多くの企業は、メッセージが入力して、システムを終了したことを証明することができるようにします。 これを実現する必要があります、受信の追跡を有効にする受信ポートと送信ポートを対応する送信メッセージの追跡を有効にします。 必要に応じて、メッセージ プロパティとメッセージ本文の追跡を追加することができます。  
  
    -   ビジネス主要業績評価指標 (Kpi) または指定されたビジネス マイルス トーンの達成によって測定される進行状況を測定するためには、ビジネス アクティビティの監視 (BAM) のいずれも追跡を使用する必要があります。 BAM の追跡には、追跡、これは重要では、履歴および追跡データを BAM の追跡と組み合わせて使用する必要がありますは場合、本文のメッセージを格納する機能が制限されています。 BAM の追跡の詳細については、次を参照してください。[ビジネス アクティビティの監視を使用して](../core/using-business-activity-monitoring.md)します。  
  
-   **アーカイブし、を定期的に BizTalk 追跡 (BizTalkDTADb) データベースからデータを削除**  
  
    -   有効にした場合、追跡をアーカイブし、システム パフォーマンスが向上する適切なサイズ、データベースを保つために定期的に BizTalk 追跡データベースからデータを削除します。 詳細については、次を参照してください。[アーカイブおよび BizTalk 追跡データベースの削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)します。  
  
## <a name="see-also"></a>参照  
 [追跡メッセージおよびインスタンス データの表示](../core/viewing-tracked-message-and-instance-data.md)