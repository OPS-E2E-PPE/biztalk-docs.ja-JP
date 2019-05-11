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
ms.openlocfilehash: bb3fcbb2799cba8e808c2bd2da66c09706fe7a33
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393451"
---
# <a name="other-activities-that-can-affect-dehydration-behavior"></a>退避の動作に影響を与える他のアクティビティ
次のアクティビティに直接または間接的に影響退避および全体のパフォーマンスとこれは、テスト シナリオに組み込む必要があります。  
  
- **BizTalk Server 管理コンソール クエリ。** これらのクエリでは、リソースを消費し、種類と、クエリの頻度に応じて全体的なスループットに影響します。  
  
- **バックアップ、アーカイブ、およびアクティビティを削除します。** これらのアクティビティもリソースを消費し、テスト シナリオに組み込む必要があります。  
  
- **32 ビットおよび 64 ビット ホストが混在します。** 32 ビットおよび 64 ビット ホストの混在を使用する場合の考慮事項を次に示します。  
  
  - ストレス条件下では仮想および物理メモリの消費量を測定し、特定のしきい値と比較することです。 64 ビット システムで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロセスでは、同じシステムと同じ既定値を使用して 32 ビットからの退避ポリシーに違いがあるためにより多くのメモリを使用します。 オーケストレーションを個別の受信、送信、およびメッセージ ボックスのホストを必ず。  
  
     違いはありません、明白な 64 ビット システムでは、32 ビットの既定のしきい値を使用する場合、オーケストレーション ホストのみが、64 ビット ボックスにある限りです。 ただし、ストレス条件下で、さまざまな**MemoryThrottlingCriteria**が多いため、スループットを最大化のシナリオでチューニングする必要がありますが、少なくとも 2 倍または (として十分なメモリがある場合) の存在、する必要があります設定活躍要因。 ものを検索し、最適のストレス条件下で退避のしきい値を調整する必要があります。  
  
  - 退避の動作は、すべてのサブスクリプションの配信時刻履歴によって異なります。異なるサブスクリプションように検討してくださいこの退避プロパティの値をチューニングの履歴は異なるできます。  
  
  - オーケストレーション ホスト サービスが 1 つのホストでは、再利用されるが、別の履歴は異なるものになります。  
  
  - サーバーに異なるバージョンを使用しているときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、退避ポリシーで、2 つの間の違いがあります。  
  
## <a name="see-also"></a>参照  
 [BTSNTSvc.exe.config ファイル](../core/btsntsvc-exe-config-file.md)