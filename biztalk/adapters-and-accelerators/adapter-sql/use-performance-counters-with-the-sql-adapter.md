---
title: "SQL アダプターのパフォーマンス カウンターを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae381b78-d89e-4cf2-810b-821e49422463
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f81189e34346d377686dac79b44e5a9b34889dc
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="use-performance-counters-with-the-sql-adapter"></a>SQL アダプターのパフォーマンス カウンターを使用します。
[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]クライアントは、アダプターのパフォーマンスを測定するのにパフォーマンス カウンターを使用できます。 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ プログラムによって作成のパフォーマンス カウンター カテゴリ"[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]"アダプター パックのインストールと共にします。  
  
## <a name="the-lob-time-cumulative-performance-counter"></a>LOB (累積) 時間のパフォーマンス カウンター  
 **SQL 用の BizTalk .NET アダプター**カテゴリには 1 つのパフォーマンス カウンター「LOB 時間 (累積)」と呼ばれます。 このパフォーマンス カウンターは、SQL Server のクライアント ライブラリがアダプターを開始する操作が完了する時間をミリ秒単位で、時間を表します。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]特定の SQL Server インスタンスおよびデータベースの名前については、各操作のパフォーマンス カウンターのインスタンスを作成します。 次のパターンでは、インスタンスが作成されます。  
  
```  
<processId>:<appDomainId>:<endpointId>:<actionId>  
```  
  
 `<endpointId>`として派生`<sql_server_name>, <instance_name>, <database_name>`です。  
  
 \<ActionId\>は次のように派生します。  
  
-   接続を開くには、アクション ID「開く」です。  
  
-   受信操作は、操作 ID は"Inbound"です。  
  
-   送信操作は、操作 ID は、呼び出される操作のアクションと「/」は、アンダー スコア「_」に置換します。 また、アクション ID が付いて"ExecuteScalar"、"ExecuteReader"または"ExecuteNonQuery"方法によっては、アダプターは、SQL Server データベースで操作を実行する内部で使用します。 アダプターが内部的に使用するなど、 **ExecuteReader** SQL Server でストアド プロシージャを実行するメソッド。 そのため、ストアド プロシージャで MyProcedure、操作 ID になります。  
  
    ```  
    ExecuteReader_Procedure_dbo_MyProcedure  
    ```  

 パフォーマンス カウンターは、アダプターが SQL Server データベースへの最初の呼び出し後にのみ初期化されます。 また、 [InstanceLifetime](https://msdn.microsoft.com/library/system.diagnostics.performancecounter.instancelifetime.aspx)パフォーマンス カウンターのプロパティが 'Process' は、パフォーマンス カウンターは、カウンターを作成するプログラムが終了するとすぐに存在しなくなることを意味します。
  
> [!NOTE]
>  LOB Time (累積) パフォーマンス カウンターの有効桁数は、16 ミリ秒です。  
  
## <a name="enabling-performance-counters"></a>パフォーマンス カウンターを有効にします。  
 パフォーマンス カウンターを有効になっているやバインド プロパティを設定して無効になっている**EnablePerformanceCounters**です。 パフォーマンス カウンターを有効にするには設定、 **EnablePerformanceCounters**にプロパティのバインド**True**です。 パフォーマンス カウンターを無効にする設定**EnablePerformanceCounters**に**False**です。 既定では、プロパティに設定が**False**です。 このバインドのプロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a>パフォーマンス カウンターと WCF LOB Adapter SDK  
 値を変更する、 **EnablePerformanceCounters**に対応するパフォーマンス カウンターの値が変更もプロパティのバインド、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。 バインディング プロパティも、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]静的では、一方の[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]は動的です。 そのため、2 つのインスタンスがある場合、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]アプリケーション ドメインでのバインディング、および**EnablePerformanceCounters**に設定されているプロパティのバインド**True**いずれかでと**False**アダプター固有のパフォーマンス カウンターのいずれかで有効にし、他の無効になっているは、それ以外のです。 ただし、ためのバインディング プロパティ[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]は静的で、いずれかに設定されます**True**または**False**によってどのような値を最後に指定されました。  
  
## <a name="see-also"></a>参照  
[SQL アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-sql/troubleshoot-the-sql-adapter.md)