---
title: 退避の動作に影響を与える他のアクティビティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed940448-d3b1-4308-9b38-887904e03bd0
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed8c37dbcca5c15e777cf6a98e50227f8752e324
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979299"
---
# <a name="other-activities-that-can-affect-dehydration-behavior"></a>退避の動作に影響する可能性のあるその他のアクティビティ
次のアクティビティは、退避および全体のパフォーマンスに直接的または間接的に影響するため、テスト シナリオに組み込む必要があります。  
  
- **BizTalk Server 管理コンソール クエリ。** これらのクエリはリソースを消費し、クエリの種類と頻度に応じて全体的なスループットに影響します。  
  
- **バックアップ、アーカイブ、およびアクティビティを削除します。** これらのアクティビティもリソースを消費するので、テスト シナリオに組み込む必要があります。  
  
- **32 ビットおよび 64 ビット ホストが混在します。** 32 ビット ホストと 64 ビット ホストを混在して使用する場合は、次の点を考慮する必要があります。  
  
  - ストレス条件下で仮想メモリと物理メモリの使用量を測定し、その結果を特定のしきい値と比較します。 64 ビット システムでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロセスによってより多くのメモリが使用されるため、同じシステムおよび同じ既定値を使用する 32 ビットとは退避ポリシーが異なります。 オーケストレーション、受信、送信、およびメッセージ ボックスのホストを別々にしてください。  
  
     32 ビットの既定のしきい値を 64 ビット システムで使用する場合、オーケストレーション ホストのみが 64 ビット ボックスに配置されていれば、明確な違いはありません。 ただし、ストレス条件下で、さまざまな**MemoryThrottlingCriteria**が多いため、スループットを最大化のシナリオでチューニングする必要がありますが、少なくとも 2 倍または (として十分なメモリがある場合) の存在、する必要があります設定活躍要因。 ストレス条件下で退避のしきい値を調整し、最適なしきい値を見つける必要があります。  
  
  - 退避の動作は、各サブスクリプションの配信時刻履歴に応じて異なります。配信時刻履歴はサブスクリプションごとに異なる場合があるため、退避プロパティの値を調整する際にはこの点を考慮してください。  
  
  - あるホストでオーケストレーション ホスト サービスを再利用し、別のホストで再利用しない場合、両ホストの履歴は異なるものになります。  
  
  - 複数のサーバーで異なるバージョンの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用している場合、両サーバーの退避ポリシーは異なるものになります。  
  
## <a name="see-also"></a>参照  
 [BTSNTSvc.exe.config ファイル](../core/btsntsvc-exe-config-file.md)