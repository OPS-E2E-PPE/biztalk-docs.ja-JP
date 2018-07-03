---
title: 退避を計算する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 88f2d09c-60db-4daf-b850-23f2c8915502
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db413cfef1e49f1f3177d8a9f578c94f5a2a1a28
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998147"
---
# <a name="how-to-calculate-dehydration"></a>退避を計算する方法
退避を計算するには、構成されたプロパティおよび特定の実行時の値を使用します。 仮定の退避シナリオを計算する方法を次の例に示します。  
  
### <a name="to-calculate-dehydration"></a>退避を計算するには  
  
1. メモリの負荷を測定する 0 と 1 の間の要素を alpha によって表します。  実際には、アルファは、3 つのコンポーネントを持つメモリ制限の条件 (退避プロパティ)。この例ではそれらと示す alpha(virtual)、alpha(private) および alpha(physical)。 次のように定義します。  
  
   ```  
   IF ActualPrivateBytes < OptimalUsage  
      alpha(private) = 1  
   ELSE IF ActualPrivateBytes > MaximalUsage  
      alpha(private) = 0  
   ELSE  
      alpha(private) = (MaximalUsage - ActualPrivateBytes) / (MaximalUsage - OptimalUsage)  
   ```  
  
   > [!NOTE]
   >  OptimalUsage と MaximalUsage には各退避プロパティの既定値があります。 これらの値は BTSNTSvc.exe.config ファイルで変更できます。 詳細については、次を参照してください。[既定の退避プロパティ](../core/dehydration-default-properties.md)します。  
  
2. その他の alpha コンポーネントも同様に定義します。 次のように定義します。  
  
   ```  
   alpha = Minimum { alpha(virtual), alpha(private), alpha(physical) }  
   where alpha(…) = 1 whenever IsActive=false for that given memory unit  
   ```  
  
3. 次に TestThreshold を定義します (TestThreshold、MinThreshold、および MaxThreshold は秒単位で定義します)。  
  
   ```  
   TestThreshold = MinThreshold + (alpha * (MaxThreshold – MinThreshold))  
   ```  
  
   > [!NOTE]
   >  MinThreshold の既定値 = 1。 MaxThreshold の既定値 = 1800。 これらの値は BTSNTSvc.exe.config ファイルで変更できます。 詳細については、次を参照してください。[既定の退避プロパティ](../core/dehydration-default-properties.md)します。  
  
4. 次に TimeBlocked と EstimatedTime を定義します。  
  
   -   TimeBlocked = サブスクリプションが満たされるまでに待機する実際の時間  
  
   -   EstimatedTime = このオーケストレーションがアイドルである推定時間 (たとえば、待ち受け中の残りのタイムアウト)  
  
   退避するかどうかの決定は、次のブール値条件の結果によって決まります (true = 退避)。  
  
-   待避 = (EstimatedTime > TestThreshold または TimeBlocked > (2* TestThreshold))  
  
> [!NOTE]
>  推定時間は遅延が終了するまでの残り時間です (5 分間と 2 分間の遅延が経過した場合、TimeBlocked=120 秒、EstimatedTime=180 秒です)。  
  
## <a name="see-also"></a>参照  
 [既定の退避プロパティ](../core/dehydration-default-properties.md)   
 [BTSNTSvc.exe.config ファイル](../core/btsntsvc-exe-config-file.md)