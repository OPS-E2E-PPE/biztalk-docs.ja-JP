---
title: リリース フェーズの推奨事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c5ac72aa-decd-4b3e-be34-e585e54568b3
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a186306a951b249c7bcadb243549c8761f6408fa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397968"
---
# <a name="release-phase-recommendations"></a>リリース フェーズの推奨事項
リリース フェーズでは、実稼働のハードウェア上に現在検証済みのシステムを伝達する必要があります。  
  
## <a name="propagate-test-bed-optimizations-to-production-systems"></a>テスト ベッド最適化の実稼働システムに反映されるまでください。  
 システムの成果物と実稼働のハードウェア上に構成を反映し、最大を開始すること、プロセスは、比較的簡単なプロセスになります。 ただし、実際が簡単に見落とされることができますが、このフェーズ中にパフォーマンスに関する考慮事項があります。  
  
-   **プラットフォームの最適化が伝達されていることを確認**します。 実装との検証中には、任意の数のプラットフォーム レベルのパフォーマンスの最適化を実装するために一般的です。  
  
     たとえば、HTTP などの分離アダプターのインターネット インフォメーション サーバー (IIS) を使用する場合は、数など、アダプターを実行する IIS のプロセスの数を増やすために使用できる一般的なパフォーマンスを最適化します。 リリースの追跡し、同様、運用環境に反映する必要があります前に見つかったパフォーマンス最適化などにします。  
  
-   **設定してデータのバックアップを自動化、ログ配布、データ保有期間の構成、および削除タスク**します。 実稼働に対する保証の一環として、データベースのバックアップおよび消去されます (例、BizTalk 追跡データベース、および BAM データベース) の位置の頻度は持続可能性に対するキーがまだ存在しない実稼働環境にこれらの設定を移行する必要があります。  
  
## <a name="see-also"></a>参照  
 [プロジェクトの計画フェーズの推奨事項](../core/project-planning-recommendations-by-phase.md)   
 [要件フェーズの推奨事項](../core/requirements-phase-recommendations.md)   
 [デザイン フェーズの推奨事項](../core/design-phase-recommendations.md)   
 [実装フェーズの推奨事項](../core/implementation-phase-recommendations.md)   
 [検証フェーズの推奨事項](../core/verification-phase-recommendations.md)