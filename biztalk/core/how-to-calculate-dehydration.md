---
title: "退避を計算する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 88f2d09c-60db-4daf-b850-23f2c8915502
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a327695099ec575f2a13ccb75b4152e4a7de1af
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-calculate-dehydration"></a>退避を計算する方法
退避を計算するには、構成されたプロパティおよび特定の実行時の値を使用します。 仮定の退避シナリオを計算する方法を次の例に示します。  
  
### <a name="to-calculate-dehydration"></a>退避を計算するには  
  
1.  メモリの負荷を測定する 0 と 1 の間の要素を alpha によって表します。  実際には、アルファは、3 つのコンポーネントを持つメモリ制限条件 (退避プロパティ) です。この例ではを表してそれら alpha(virtual)、alpha(private) alpha(physical) として。 次のように定義します。  
  
    ```  
    IF ActualPrivateBytes < OptimalUsage  
       alpha(private) = 1  
    ELSE IF ActualPrivateBytes > MaximalUsage  
       alpha(private) = 0  
    ELSE  
       alpha(private) = (MaximalUsage - ActualPrivateBytes) / (MaximalUsage - OptimalUsage)  
    ```  
  
    > [!NOTE]
    >  OptimalUsage と MaximalUsage には各退避プロパティの既定値があります。 これらの値は BTSNTSvc.exe.config ファイルで変更できます。 詳細については、次を参照してください。[既定の退避プロパティ](../core/dehydration-default-properties.md)です。  
  
2.  その他の alpha コンポーネントも同様に定義します。 次のように定義します。  
  
    ```  
    alpha = Minimum { alpha(virtual), alpha(private), alpha(physical) }  
    where alpha(…) = 1 whenever IsActive=false for that given memory unit  
    ```  
  
3.  次に TestThreshold を定義します (TestThreshold、MinThreshold、および MaxThreshold は秒単位で定義します)。  
  
    ```  
    TestThreshold = MinThreshold + (alpha * (MaxThreshold – MinThreshold))  
    ```  
  
    > [!NOTE]
    >  MinThreshold の既定値 = 1 です。 MaxThreshold の既定値 = 1800。 これらの値は BTSNTSvc.exe.config ファイルで変更できます。 詳細については、次を参照してください。[既定の退避プロパティ](../core/dehydration-default-properties.md)です。  
  
4.  次に TimeBlocked と EstimatedTime を定義します。  
  
    -   TimeBlocked = サブスクリプションが満たされるまでに待機する実際の時間  
  
    -   EstimatedTime = このオーケストレーションがアイドルである推定時間 (たとえば、待ち受け中の残りのタイムアウト)  
  
 退避するかどうかの決定は、次のブール値条件の結果によって決まります (true = 退避)。  
  
-   待避 = (EstimatedTime > TestThreshold または TimeBlocked > (2* TestThreshold))  
  
> [!NOTE]
>  推定時間は遅延が終了するまでの残り時間です (5 分間と 2 分間の遅延が経過した場合、TimeBlocked=120 秒、EstimatedTime=180 秒です)。  
  
## <a name="see-also"></a>参照  
 [既定の退避プロパティ](../core/dehydration-default-properties.md)   
 [BTSNTSvc.exe.config ファイル](../core/btsntsvc-exe-config-file.md)