---
title: "Oracle E-business Suite アダプターのパフォーマンス カウンターを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c7d722b7-8343-4956-81ed-acd5a463a9b1
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf2a9f345745c18ca03086833fffe3553e96cece
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="use-performance-counters-with-the-oracle-e-business-suite-adapter"></a>Oracle E-business Suite アダプターのパフォーマンス カウンターの使用します。
Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]クライアントは、アダプターのパフォーマンスを測定するパフォーマンス カウンターを使用することができます。 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ プログラムは、パフォーマンス カウンターのカテゴリを作成**BizTalk .NET Adapter for Oracle E-business Suite**をインストールすると共に、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。  
  
## <a name="lob-time-cumulative-performance-counter"></a>LOB Time (累積) パフォーマンス カウンター  
 **BizTalk .NET Adapter for Oracle E-business Suite**カテゴリには 1 つというパフォーマンス カウンター"LOB Time (累積)." このパフォーマンス カウンターは、LOB クライアント ライブラリは、アダプターを開始する操作が完了する時間をミリ秒単位で、時間を表します。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]パターンを次のいずれかで、パフォーマンス カウンターのインスタンスを作成します。  
  
```  
<process id>:<app domain id>:<oracle data source>:<string>  
```  
  
 ここで"string"可能性があります。  
  
-   Connection.Open  
  
-   Connection.Close  
  
-   メタデータ  
  
-   メッセージ アクション。 たとえば、次のアクションは`InterfaceTables/Insert/FND/APPS/MS_SAMPLE_EMPLOYEE`InterfaceTables.Insert.FND.APPS.MS_SAMPLE_EMPLOYEE は文字列になります。  
  
 Oracle データ ソースは、接続 URI の指定と同じです。  
  
 パフォーマンス カウンターは、アダプターが、Oracle データベースへの最初の呼び出し後にのみ初期化されます。 また、パフォーマンス カウンターの InstanceLifetime プロパティは、'Process' は、パフォーマンス カウンターは、カウンターを作成するプログラムが終了するとすぐに存在しなくなることを意味する設定です。 
  
> [!NOTE]
>  LOB Time (累積) パフォーマンス カウンターの有効桁数は、16 ミリ秒です。  
  
## <a name="enabling-performance-counters"></a>パフォーマンス カウンターを有効にします。  
 パフォーマンス カウンターを有効になっているやバインド プロパティを設定して無効になっている**EnablePerformanceCounters**です。 パフォーマンス カウンターを有効にするには設定、 **EnablePerformanceCounters**にプロパティのバインド**True**です。 パフォーマンス カウンターを無効にする設定**EnablePerformanceCounters**に**False**です。 既定では、 **EnablePerformanceCounters**に設定されている**False**です。  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a>パフォーマンス カウンターと WCF LOB Adapter SDK  
 値を変更する、 **EnablePerformanceCounters**に対応するパフォーマンス カウンターの値が変更もプロパティのバインド、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。 バインディング プロパティも、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]静的では、一方の[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]は動的です。 そのため、2 つのインスタンスがある場合、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] 、AppDomain にバインドされ、 **EnablePerformanceCounters**に設定されているプロパティのバインド**True**いずれかでと**False**アダプター固有のパフォーマンス カウンターのいずれかで有効にし、他の無効になっているは、それ以外のです。 ただし、ためのバインディング プロパティ[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]は静的で、いずれかに設定されます**True**または**False**によってどのような値を最後に指定されました。  
  
## <a name="see-also"></a>参照  
[アダプターのトラブルシューティング](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)