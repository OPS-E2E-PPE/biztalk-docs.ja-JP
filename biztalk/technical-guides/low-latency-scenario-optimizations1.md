---
title: 低待機時間シナリオ Optimizations1 |Microsoft Docs
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
ms.openlocfilehash: ed309a8ea9d6728dc4e0e653969f456e69f6eb34
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986059"
---
# <a name="low-latency-scenario-optimizations"></a>低待機時間シナリオの最適化
既定では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は低待機時間よりもスループットに最適化されています。 次の最適化が適用された[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]テスト シナリオではこのガイドに使用します。  
  
> [!NOTE]  
>  これらの最適化では、待機時間が改善されますが、全体的なスループットをいくつかのコストで行うことがあります。  
  
## <a name="increase-the-biztalk-server-host-internal-message-queue-size"></a>BizTalk Server ホストの内部メッセージ キューのサイズを増やす  
 各 BizTalk ホストには、内部のメモリ内キューがあります。 低待機時間シナリオのパフォーマンスを向上させるためには、100 ~ 1000 の既定値からこのキューのサイズを大ききます。 内部メッセージ キューのサイズの値を変更する方法の詳細については、「方法を既定のホスト制限設定の変更」、BizTalk Server ヘルプでを参照してください。 [ http://go.microsoft.com/fwlink/?LinkID=120225](http://go.microsoft.com/fwlink/?LinkID=120225)します。  
  
## <a name="reduce-the-maxreceiveinterval-value-in-the-admserviceclass-table-of-the-biztalk-server-management-database"></a>BizTalk Server 管理データベースの adm_ServiceClass テーブルの MaxReceiveInterval 値を減らします  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ポーリング メカニズムを使用して、メッセージ ボックスで、ホスト キューからメッセージを受信します。 **MaxReceiveInterval** BizTalk 管理 (BizTalkMgmtDb) データベースの adm_ServiceClass テーブル内の値は、各 BizTalk ホスト インスタンスが待機するミリ秒単位で最大値まで、メッセージ ボックス データベースをポーリングします。 Adm_ServiceClass テーブルには、次のサービスの種類のレコードが含まれています。  
  
- **XLANG/S** -オーケストレーションの BizTalk ホスト インスタンスの場合  
  
- **Messaging InProcess** – のインプロセス ホスト インスタンス  
  
- **MSMQT** -MSMQT アダプターのホスト インスタンスの場合  
  
- **Messaging Isolated** -HTTP の場合で使用される、プロセス ホストのインスタンスから SOAP、および特定の WCF 受信アダプターのハンドラー  
  
  既定では、低待機時間よりもスループットが最適化された 500 (ミリ秒単位) をこの値が設定されます。 特定のシナリオでは、この値を減らすことで待機時間を改善できます。  
  
> [!NOTE]
>  この値を変更は、関連付けられているサービスの種類のすべてのインスタンスに影響を与えるため、この値を変更する前にすべてのホスト インスタンスへの影響を評価するように注意します。  
> 
> [!NOTE]
>  この値は、メッセージ ボックスが残っている未処理メッセージを持たない場合にのみ使用します。 メッセージ ボックス内の未処理のメッセージのバックログが絶えず場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ポーリング遅延に待機することがなく、メッセージの処理を試みます。 すべてのメッセージが処理された後[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MaxReceiveInterval に指定された値を使用して、ポーリングが開始されます。  
> 
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]高比率 MaxReceiveInterval がメッセージ ボックス データベースのインスタンスを格納する SQL Server コンピューターで過剰な CPU 使用率を引き起こす可能性が値を減らす、メッセージ ボックス データベースのインスタンスへのホスト インスタンスの環境。 たとえば、低い値に、MaxReceiveInterval が減少 (\< 100) で、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 1 つのメッセージ ボックスおよび > 50 ホスト インスタンスの使用環境では、SQL Server の CPU 使用率は 50% を超える上昇する可能性があります。 この現象は、継続的にホストのキューのポーリングに伴うオーバーヘッドは大幅な場合に発生します。 MaxReceiveInterval を 100 未満の値を小さく場合、SQL Server コンピューターの CPU 使用率がこの影響を評価する必要もあります。