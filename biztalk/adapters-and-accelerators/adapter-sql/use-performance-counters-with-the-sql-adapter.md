---
title: SQL アダプターを使用したパフォーマンス カウンターの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae381b78-d89e-4cf2-810b-821e49422463
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 29e6bdb107a845682aae8d587ccaa619ac075a45
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367408"
---
# <a name="use-performance-counters-with-the-sql-adapter"></a>SQL アダプターを使用したパフォーマンス カウンターを使用します。
[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] クライアントは、アダプターのパフォーマンスを測定するのにパフォーマンス カウンターを使用できます。 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ プログラムは、パフォーマンス カウンター カテゴリを作成します。"[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]"アダプター パックのインストールと共にします。  
  
## <a name="the-lob-time-cumulative-performance-counter"></a>LOB の時間 (累積) パフォーマンス カウンター  
 **SQL 用の BizTalk .NET アダプター**カテゴリには 1 つのパフォーマンス カウンター"LOB Time (累積)"と呼ばれます。 このパフォーマンス カウンターは、SQL Server のクライアント ライブラリは、アダプターを起動する操作を完了するまでをミリ秒単位の時間を表します。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]の各アクションは、特定の SQL Server インスタンスとデータベース名のパフォーマンス カウンターのインスタンスを作成します。 次のパターンでは、インスタンスが作成されます。  
  
```  
<processId>:<appDomainId>:<endpointId>:<actionId>  
```  
  
 `<endpointId>`としては、派生`<sql_server_name>, <instance_name>, <database_name>`します。  
  
 \<ActionId\>は次のように派生します。  
  
- 接続を開くは、操作 ID は、[開く] です。  
  
- 受信操作の場合は、操作 ID は、"Inbound"です。  
  
- 送信操作は、操作 ID が呼び出される操作のアクションを「/」は、アンダー スコア「_」で置き換えられます。 また、操作 ID は、アダプターは、SQL Server データベースで操作を実行する内部的に使用する方法によって"ExecuteScalar"、"ExecuteReader"または"ExecuteNonQuery"プレフィックスします。 アダプターが内部的に使用するなど、 **ExecuteReader**メソッドを SQL Server のストアド プロシージャを実行します。 そのため、ストアド プロシージャで MyProcedure、操作 ID になります。  
  
  ```  
  ExecuteReader_Procedure_dbo_MyProcedure  
  ```  

  パフォーマンス カウンターは、アダプターが SQL Server データベースの最初の呼び出し後にのみ初期化されます。 また、 [InstanceLifetime](https://msdn.microsoft.com/library/system.diagnostics.performancecounter.instancelifetime.aspx) 'Process' は、パフォーマンス カウンターは、カウンターを作成するプログラムが終了すると、すぐに存在しなくなることを意味するパフォーマンス カウンターのプロパティが設定されています。
  
> [!NOTE]
>  LOB の時間 (累積) パフォーマンス カウンターの有効桁数は、16 ミリ秒です。  
  
## <a name="enabling-performance-counters"></a>パフォーマンス カウンターを有効にします。  
 パフォーマンス カウンターを有効またはバインドのプロパティを設定して無効にできる**EnablePerformanceCounters**します。 パフォーマンス カウンターを有効にするには設定、 **EnablePerformanceCounters**プロパティをバインド**True**します。 パフォーマンス カウンターを無効にするには設定**EnablePerformanceCounters**に**False**します。 既定では、プロパティに設定が**False**します。 このバインドのプロパティの詳細については、次を参照してください。 [for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)します。  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a>パフォーマンス カウンターと WCF LOB Adapter SDK  
 値を変更する、 **EnablePerformanceCounters**に対応するパフォーマンス カウンターの値を変更してもプロパティをバインド、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。 バインド プロパティも、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]は静的で一方の場合、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]は動的です。 そのため、2 つのインスタンスがある場合、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] 、アプリケーション ドメインでのバインドと**EnablePerformanceCounters**に設定されているプロパティのバインド**True**いずれかでと**False**アダプター固有のパフォーマンス カウンターのいずれかで有効にし、他の無効になっているで、他のです。 ただし、ためのバインディング プロパティ[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]は静的で、いずれかに設定されます**True**または**False**によってどのような値を最後に指定されました。  
  
## <a name="see-also"></a>参照  
[SQL アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-sql/troubleshoot-the-sql-adapter.md)