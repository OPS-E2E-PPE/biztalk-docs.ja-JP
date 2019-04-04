---
title: ボトルネック テストとチューニングを実行する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 95d41d95-3a76-4eb0-b07d-14c6b6dccdaa
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 468f7a3a35922c6348369050593cbb56b56457d3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018595"
---
# <a name="performing-bottleneck-testing-and-tuning"></a>ボトルネック テストとチューニングを実行します。
システムのボトルネックを特定し、それに応じてシステムをチューニングするパフォーマンスのテストを完了する必要があります。  
  
## <a name="testing-a-subsystem"></a>サブシステムのテスト  
 システムのボトルネックを識別するためのベスト プラクティスは、たとえば、システム全体のサブセットに対してパフォーマンス テストの実行には。  
  
- メッセージを送信またはからのメッセージを受信する外部システムのベースライン パフォーマンス パラメーターを確立[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
- オーケストレーションを参加させるが、開始しないでください。 受信キュー/ファイルの場所にメッセージを削除し、受信アダプターのドレインにキュー/ファイルの場所を受信し、メッセージ ボックス データベースにメッセージを発行できるようにします。 これにより、受信を分離することが最大の持続的な入力率を決定するポート。  
  
- メッセージはメッセージ ボックス データベースにプルと受信アダプターを停止、オーケストレーション プロセスを有効にするや送信アダプター、し、次オーケストレーションする速度を測定か送信アダプターはメッセージの処理します。  
  
## <a name="testing-the-end-to-end-system"></a>エンド ツー エンド システムをテストします。  
 エンド ツー エンドのパフォーマンスは説明しませんが、アプリケーション サブシステムのパフォーマンスを分離する効果的な方法は、前のセクションの説明に従って、入力と出力料金のテストします。 同じ共有リソース (たとえば、メッセージ ボックス データベース) に対して競合する複数のリソースが開始されるまで、いくつかのボトルネックを識別できないため、エンド ツー エンドのパフォーマンスをテストすることも必要があります。  
  
 負荷を生成する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境では、Microsoft BizTalk LoadGen 2007 ツールの使用を検討します。 ダウンロード[LoadGen](https://www.microsoft.com/download/details.aspx?id=14925)します。  
  
 分析のパフォーマンス レポートを生成したり、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境では、パフォーマンス分析のログ (PAL) ツールの使用を検討します。 PAL ツールの詳細については、[パフォーマンス分析のログ (PAL) ツールを使用して](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)を参照してください。  
  
## <a name="what-developers-operators-and-administrators-should-know"></a>どのような開発者、演算子、および管理者が把握する必要があります。  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 開発者はでも熟知する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パフォーマンスの特性とチューニングします。 オペレーターや管理者は、メッセージ ボックス データベースのスケール アウト側面、SAN に精通する必要がありますの調整、ネットワークは、次のチューニング、および SQL Server データベースのチューニング (たとえばを参照してください[SQL Server の設定を変更しないこと](../technical-guides/sql-server-settings-that-should-not-be-changed.md))。 開発者、演算子、および管理者はチューニングする方法を認識する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]高スループットと低待機時間。