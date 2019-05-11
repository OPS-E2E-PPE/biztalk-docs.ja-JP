---
title: Oracle データベース アダプターを使用したパフォーマンス カウンターの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance counters, using
- performance counter, LOB Time Cumulative
- performance counters, enabling
- performance counters, and the WCF LOB Adapter SDK
ms.assetid: beb80896-7594-411e-a83c-169d5278e2ce
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bd80a3dea7f0e1b0e0e99e82c195540cd931c36
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375870"
---
# <a name="use-performance-counters-with-the-oracle-database-adapter"></a>Oracle データベース アダプターを使用したパフォーマンス カウンターを使用します。
Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]クライアントは、パフォーマンス カウンターを使用して、アダプターのパフォーマンスを測定します。 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ プログラムは、パフォーマンス カウンター カテゴリを作成します。 **Oracle DB の .NET アダプターを BizTalk**をインストールすると共に、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。  
  
## <a name="lob-time-cumulative-performance-counter"></a>LOB の時間 (累積) パフォーマンス カウンター  
 **Oracle DB の .NET アダプターを BizTalk**カテゴリ カウンター"LOB Time (累積)."と呼ばれる 1 つのパフォーマンスには このパフォーマンス カウンターは、LOB クライアント ライブラリは、アダプターを起動する操作を完了するまでをミリ秒単位の時間を示します。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]の次のパターンで、パフォーマンス カウンターのインスタンスを作成します。  
  
```  
<process id>:<app domain id>:<oracle data source>:<string>  
```  
  
 場所"string"になります。  
  
- Connection.Open  
  
- Connection.Close  
  
- メタデータ  
  
- メッセージ アクション。 たとえば、次のアクションが`http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert`文字列が SCOTT になります。Table.EMP.Insert します。  
  
  Oracle データ ソースは、接続 URI で指定されている同じです。  
  
  パフォーマンス カウンターは、アダプターが Oracle データベースへの最初の呼び出し後にのみ初期化されます。 また、パフォーマンス カウンターの InstanceLifetime プロパティは、'Process' は、パフォーマンス カウンターがカウンターを作成するプログラムが終了するとすぐには存在しなくなりますに設定されます。 詳細については、`InstanceLifetime property`を参照してください[ http://go.microsoft.com/fwlink/p/?LinkId=104181](http://go.microsoft.com/fwlink/p/?LinkId=104181)します。  
  
> [!NOTE]
>  LOB の時間 (累積) パフォーマンス カウンターの有効桁数は、16 ミリ秒です。  
  
## <a name="enabling-performance-counters"></a>パフォーマンス カウンターを有効にします。  
 パフォーマンス カウンターを有効またはバインドのプロパティを設定して無効にできる**EnablePerformanceCounters**します。 パフォーマンス カウンターを有効にするには設定、 **EnablePerformanceCounters**プロパティをバインド**True**します。 パフォーマンス カウンターを無効にするには設定**EnablePerformanceCounters**に**False**します。 既定では、 **EnablePerformanceCounters**に設定されている**False**します。  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a>パフォーマンス カウンターと WCF LOB Adapter SDK  
 値を変更する、 **EnablePerformanceCounters**に対応するパフォーマンス カウンターの値を変更してもプロパティをバインド、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。 バインド プロパティも、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]は静的で一方の場合、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]は動的です。 そのため、2 つのインスタンスがある場合、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] 、appdomain のバインドと**EnablePerformanceCounters**に設定されているプロパティのバインド**True**いずれかでと**False**アダプター固有のパフォーマンス カウンターのいずれかで有効にし、他の無効になっているで、他のです。 ただし、ためのバインディング プロパティ[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]は静的で、いずれかに設定されます**True**または**False**によってどのような値を最後に指定されました。  
  
## <a name="see-also"></a>参照  
[Oracle データベース アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)