---
title: BAM インターセプタにおける一般的な問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a32145e2-1367-4576-9103-86c9182c11a8
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 787ed9f5fd2f94f719e224db471bde8c2aad9829
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357103"
---
# <a name="common-issues-with-the-bam-interceptors"></a>BAM インターセプタにおける一般的な問題
このトピックでは、BAM インターセプタを使用する際に発生する可能性がある、以下の一般的な問題について説明します。  
  
-   分散トランザクションに関連した SQL 例外  
  
## <a name="you-receive-a-sql-exception-concerning-a-completed-distributed-transaction-or-a-transaction-descriptor"></a>完了した分散トランザクションまたはトランザクション記述子に関連した SQL 例外が返される  
 BAM Windows Communication Framework (WCF) インターセプタを実行すると、次のいずれかの例外が表示される場合があります。  
  
- 分散トランザクションが完了しました。 このセッションを新規トランザクションまたは NULL トランザクションのいずれかに参加させます。  
  
- 新しい要求は、有効なトランザクション記述子を含んでいる必要があるため、この要求を開始できません。  
  
  この問題をトラブルシューティングする方法としては、以下が推奨されます。  
  
- BAM トレースを有効にします。 このトレースでは、エラーの根本原因を含むすべての関連メッセージが対象となります。 BAM トレースの詳細については、次を参照してください。 [BAM のトレースの有効化する方法](../core/how-to-enable-tracing-in-bam.md)します。  
  
- この分散トランザクション コーディネータ (DTC) 例外が表示される場合は、完全に同一なシナリオをトランザクションなしで返すことを試みます。  
  
- SQL Server Profiler を使用して、トランザクションが中断する原因となるエラーをトレースで検索します。  
  
## <a name="you-receive-an-error-similar-to-interceptor-configuration-polling-interval-0-must-be-at-least-5-seconds-when-using-the-wcf-interceptor"></a>WCF インターセプタを使用すると、「インターセプタ構成ポーリング間隔 '0' を '5' 秒以上にする必要があります」というエラーが返される  
 このエラーは、アプリケーション構成ファイルでインターセプタ構成ポーリング間隔の値を明示的に指定しなかった場合、または有効な下限値である 5 秒に満たない値を指定した場合に発生します。  
  
 この問題を解決するには、次のように PollingIntervalSec に有効な値を指定します。  
  
```  
<BamEndpointBehaviorExtension ConnectionString="Initial Catalog=BamPrimaryImport;Data Source=MyMachine;Integrated Security=SSPI;" PollingIntervalSec="1500" />  
```  
  
## <a name="see-also"></a>参照  
 [BAM インターセプタのトラブルシューティング](../core/troubleshooting-bam-interceptors.md)