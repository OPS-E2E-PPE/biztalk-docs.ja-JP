---
title: Oracle E-business Suite アダプターを使用したパフォーマンス カウンターの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7d722b7-8343-4956-81ed-acd5a463a9b1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4b2c187dbc33a441de8d11d489c5377c0c4e742
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985011"
---
# <a name="use-performance-counters-with-the-oracle-e-business-suite-adapter"></a>Oracle E-business Suite アダプターを使用したパフォーマンス カウンターの使用します。
Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]クライアントは、パフォーマンス カウンターを使用して、アダプターのパフォーマンスを測定します。 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ プログラムは、パフォーマンス カウンター カテゴリを作成します。 **BizTalk .NET の Adapter for Oracle E-business Suite**をインストールすると共に、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。  
  
## <a name="lob-time-cumulative-performance-counter"></a>LOB Time (累積) パフォーマンス カウンター  
 **BizTalk .NET の Adapter for Oracle E-business Suite**カテゴリ カウンター"LOB Time (累積)."と呼ばれる 1 つのパフォーマンスには このパフォーマンス カウンターは、LOB クライアント ライブラリは、アダプターを起動する操作を完了するまでをミリ秒単位の時間を示します。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]の次のパターンで、パフォーマンス カウンターのインスタンスを作成します。  
  
```  
<process id>:<app domain id>:<oracle data source>:<string>  
```  
  
 場所"string"になります。  
  
- Connection.Open  
  
- Connection.Close  
  
- メタデータ  
  
- メッセージ アクション。 たとえば、次のアクションが`InterfaceTables/Insert/FND/APPS/MS_SAMPLE_EMPLOYEE`文字列は InterfaceTables.Insert.FND.APPS.MS_SAMPLE_EMPLOYEE になります。  
  
  Oracle データ ソースは、接続 URI で指定されている同じです。  
  
  パフォーマンス カウンターは、アダプターが Oracle データベースへの最初の呼び出し後にのみ初期化されます。 また、パフォーマンス カウンターの InstanceLifetime プロパティは、'Process' は、パフォーマンス カウンターがカウンターを作成するプログラムが終了するとすぐには存在しなくなりますに設定されます。 
  
> [!NOTE]
>  LOB の時間 (累積) パフォーマンス カウンターの有効桁数は、16 ミリ秒です。  
  
## <a name="enabling-performance-counters"></a>パフォーマンス カウンターを有効にします。  
 パフォーマンス カウンターを有効またはバインドのプロパティを設定して無効にできる**EnablePerformanceCounters**します。 パフォーマンス カウンターを有効にするには設定、 **EnablePerformanceCounters**プロパティをバインド**True**します。 パフォーマンス カウンターを無効にするには設定**EnablePerformanceCounters**に**False**します。 既定では、 **EnablePerformanceCounters**に設定されている**False**します。  
  
## <a name="performance-counters-and-the-wcf-lob-adapter-sdk"></a>パフォーマンス カウンターと WCF LOB Adapter SDK  
 値を変更する、 **EnablePerformanceCounters**に対応するパフォーマンス カウンターの値を変更してもプロパティをバインド、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。 バインド プロパティも、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]は静的で一方の場合、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]は動的です。 そのため、2 つのインスタンスがある場合、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] 、appdomain のバインドと**EnablePerformanceCounters**に設定されているプロパティのバインド**True**いずれかでと**False**アダプター固有のパフォーマンス カウンターのいずれかで有効にし、他の無効になっているで、他のです。 ただし、ためのバインディング プロパティ[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]は静的で、いずれかに設定されます**True**または**False**によってどのような値を最後に指定されました。  
  
## <a name="see-also"></a>参照  
[アダプターのトラブルシューティング](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)