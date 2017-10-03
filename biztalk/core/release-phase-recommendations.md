---
title: "リリース フェーズの推奨事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c5ac72aa-decd-4b3e-be34-e585e54568b3
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46a38a8a06fac8dc35fed4d965ea9b7952c5fdfe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="release-phase-recommendations"></a>リリース フェーズの推奨事項
リリース フェーズでは、現在検証済みのシステムを実稼働のハードウェアに反映させます。  
  
## <a name="propagate-test-bed-optimizations-to-production-systems"></a>テスト ベッド最適化の実稼働システムへの反映  
 実稼働のハードウェアに対してシステムのアイテムおよび構成を反映させ、このハードウェアを起動して処理できるようにすることは、比較的簡単なプロセスです。 ただし、このフェーズでは、パフォーマンスに関して見落とされがちな次の事項を考慮する必要があります。  
  
-   **プラットフォームの最適化が反映されることを確認してください。**です。 実装と検証の間に、通常、プラットフォーム レベルのパフォーマンスの最適化を必要に応じて実装します。  
  
     たとえば、インターネット インフォメーション サーバー (IIS) で HTTP などの分離アダプターを使用する場合、アダプターが実行される IIS 内のプロセス数を増やすなど、一般的なパフォーマンスの最適化をいくつか利用できます。 このようなリリース前に見つかったパフォーマンスの最適化は、追跡して実稼働環境にも反映させる必要があります。  
  
-   **設定し、データのバックアップを自動化し、ログ配布、データ保有期間の構成、および削除の各タスク**です。 実稼働に対する保証の一環として、データベース (BizTalk 追跡データベースや BAM データベースなど) のバックアップおよび削除の頻度は、これらの設定をデータベースがまだ存在しない実稼働に移行する必要があることから持続性において重要です。  
  
## <a name="see-also"></a>参照  
 [プロジェクト計画のフェーズの推奨事項](../core/project-planning-recommendations-by-phase.md)   
 [要件フェーズの推奨事項](../core/requirements-phase-recommendations.md)   
 [設計フェーズの推奨事項](../core/design-phase-recommendations.md)   
 [実装フェーズの推奨事項](../core/implementation-phase-recommendations.md)   
 [検証フェーズの推奨事項](../core/verification-phase-recommendations.md)