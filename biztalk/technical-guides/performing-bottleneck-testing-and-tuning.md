---
title: "テストとチューニングのボトルネックを実行する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95d41d95-3a76-4eb0-b07d-14c6b6dccdaa
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d21b558f75824340718f7bd6efa3f10ae9926ae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="performing-bottleneck-testing-and-tuning"></a>テストとチューニングのボトルネックを実行します。
システムのボトルネックを確認し、それに応じてシステムをチューニングするパフォーマンスのテストを完了する必要があります。  
  
## <a name="testing-a-subsystem"></a>サブシステムのテスト  
 システムのボトルネックを特定するためのベスト プラクティスは、たとえば、システム全体のサブセットに対してパフォーマンス テストの実行には。  
  
-   メッセージを送信またはからのメッセージを受信する外部システムのベースライン パフォーマンス パラメーターを確立[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。  
  
-   オーケストレーションの参加が、開始しないでください。 メッセージを受信キュー/ファイルの場所にドロップし、受信アダプターのドレイン キュー/ファイルの場所を受信し、メッセージ ボックス データベースにメッセージを公開します。 これにより、受信を分離するポートをその最大持続的な入力率を判断できます。  
  
-   メッセージは、メッセージ ボックス データベースに取り込まれたが、いったん受信アダプターを停止、オーケストレーション プロセスを有効にするや送信アダプター、およびしするオーケストレーションの転送速度を測定および送信アダプターがメッセージを処理することがことができます。  
  
## <a name="testing-the-end-to-end-system"></a>エンド ツー エンド システムをテストします。  
 エンド ツー エンドのパフォーマンスのについては説明しませんが、アプリケーション サブシステムのパフォーマンスを分離する効果的な方法は上記で説明されているため入力と出力のレートのテストです。 同じ共有リソース (たとえば、メッセージ ボックス データベース) に対して競合する複数のリソースが開始されるまで、いくつかのボトルネックを識別できないため、エンド ツー エンドのパフォーマンスをテストすることも必要があります。  
  
 負荷を生成する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境では、Microsoft BizTalk LoadGen 2007 ツールの使用を検討します。 LoadGen 2007 ツールの詳細については、次を参照してください。 [Microsoft BizTalk LoadGen 2007](http://go.microsoft.com/fwlink/?LinkID=59841) (http://go.microsoft.com/fwlink/?LinkID=59841)。  
  
 生成用のレポートのパフォーマンスを分析して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境では、パフォーマンス分析のログ (PAL) のツールの使用を検討します。 PAL ツールの詳細については、次を参照してください。[パフォーマンス分析のログ (PAL) のツールを使用して](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)です。  
  
## <a name="what-developers-operators-and-administrators-should-know"></a>どのような開発者、演算子、および管理者が知っておく必要があります。  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]開発者にでも精通している必要がある[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パフォーマンス特性およびチューニングできます。 オペレーターや管理者がメッセージ ボックス データベースのスケール アウト側面、SAN に精通する必要がありますの調整、ネットワークは、次のチューニング、および SQL Server データベースのチューニング (たとえばを参照してください[SQL Server の設定を変更しないで](../technical-guides/sql-server-settings-that-should-not-be-changed.md))。 開発者、演算子、および管理者は、チューニングする方法を認識する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]高スループットと低待機時間。