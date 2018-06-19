---
title: 低待機時間シナリオ Optimizations1 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cd2a891a-ee4b-4542-b3ce-434e2a6474be
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12f16f67f1c161f74e6a9179db8c85f48b5b3e14
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009187"
---
# <a name="low-latency-scenario-optimizations"></a>低待機時間シナリオの最適化
既定では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]低待機時間ではなく、スループットを最適化します。 次の最適化が適用された[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]テスト シナリオではこのガイドに使用します。  
  
> [!NOTE]  
>  これらの最適化では、待機時間が改善されますが、全体的なスループットにいくつかのコストで行うことがあります。  
  
## <a name="increase-the-biztalk-server-host-internal-message-queue-size"></a>BizTalk Server ホストの内部メッセージ キューのサイズを増やす  
 各 BizTalk ホストでは、内部のメモリ内キューがあります。 低待機時間シナリオでパフォーマンスを向上させるためには、100 ~ 1000 の既定値からこのキューのサイズが増加します。 内部メッセージ キュー サイズの値を変更する方法の詳細については、「方法に、既定のホスト制限設定の変更」、BizTalk Server ヘルプでを参照してください。 [http://go.microsoft.com/fwlink/?LinkID=120225](http://go.microsoft.com/fwlink/?LinkID=120225)です。  
  
## <a name="reduce-the-maxreceiveinterval-value-in-the-admserviceclass-table-of-the-biztalk-server-management-database"></a>BizTalk Server 管理データベースの adm_ServiceClass テーブルの MaxReceiveInterval 値を減らします  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ポーリング機構を使用して、メッセージ ボックス内のホスト キューからメッセージを受信します。 **MaxReceiveInterval** BizTalk 管理 (BizTalkMgmtDb) データベースの adm_ServiceClass テーブルに値は、各 BizTalk ホスト インスタンスが待機するミリ秒単位で最大値まで、メッセージ ボックス データベースをポーリングします。 Adm_ServiceClass テーブルには、次のサービスの種類のレコードが含まれます。  
  
-   **XLANG/S** -オーケストレーションの BizTalk ホスト インスタンスの場合  
  
-   **Messaging InProcess** – インプロセス ホスト インスタンスの詳細  
  
-   **MSMQT** – MSMQT アダプターのホスト インスタンスの詳細  
  
-   **Messaging Isolated**の HTTP の場合で使用される、処理ホストのインスタンスから SOAP、および特定の WCF 受信アダプターのハンドラー。  
  
 既定では、これは、低待機時間ではなく、スループットについて最適化されて 500 (ミリ秒単位) にこの値が設定されます。 特定のシナリオでは、この値を減らすことによって待機時間を向上できます。  
  
> [!NOTE]  
>  この値を変更は関連付けられているサービスの種類のすべてのインスタンスに影響を与えるため、この値を変更する前にすべてのホスト インスタンスへの影響を評価するように注意します。  
  
> [!NOTE]  
>  この値は、メッセージ ボックス データベースに残りのメッセージが未処理があるない場合にのみ使用します。 定数、メッセージ ボックス内の未処理のメッセージのバックログがない場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ポーリング遅延に待機することがなく、メッセージの処理を試みます。 すべてのメッセージを処理した後[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MaxReceiveInterval に指定された値を使用して、ポーリングが開始されます。  
  
> [!NOTE]  
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MaxReceiveInterval がメッセージ ボックス データベース インスタンスを格納する SQL Server コンピューターで過剰な CPU 使用率を引き起こす可能性が値を小さく、メッセージ ボックス データベースのインスタンスにホスト インスタンスの比率が高い環境。 たとえば、MaxReceiveInterval が低い値に減らさ (\< 100) で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境の 1 つのメッセージ ボックスおよび > 50 ホスト インスタンスでは、SQL Server の CPU 使用率は 50% を超える上昇する可能性があります。 この現象は、継続的にホスト キューのポーリングに関連するオーバーヘッドが大幅なために発生することができます。 MaxReceiveInterval を 100 未満の値を小さく場合もの SQL Server コンピューターの CPU 使用率がこの影響を評価する必要があります。