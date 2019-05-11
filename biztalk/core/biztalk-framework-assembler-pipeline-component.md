---
title: BizTalk Framework アセンブラー パイプライン コンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, BizTalk Framework Assembler
- BizTalk Framework Assembler [pipeline component]
ms.assetid: 116dff8d-b7f8-4564-a7fb-6440682683dc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 139d4bedbe8f42e9e7c97b2647b27d712697e8f4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358075"
---
# <a name="biztalk-framework-assembler-pipeline-component"></a>BizTalk Framework アセンブラー パイプライン コンポーネント
BizTalk Framework は正確に行うための 1 つの方法の 1 回 HTTP や SMTP などのネットワーク上のトランスポート プロトコルを使用して配信を保証します。 このフレームワークは 1998 年から存在して、保留中の標準的なイニシアチブ前段階としてという考えに基づいて Web サービス、特に WSReliable します。 問題は通常、正確に保証-メッセージ キュー (MSMQ とも呼ばれます) などのテクノロジのドメインをデータの配信が行われたとします。 ただし、このようなテクノロジは、通常は、データ フローの 2 つのエンドポイントでの一般的なソフトウェアを必要し、もアドレス オープンなトランスポート プロトコルの使用に何も操作を行いますに基づいてパブリック ネットワークでは、たとえば、データを使用してエンタープライズの境界間のフローをインターネットです。  
  
 当然ながら、BizTalk Framework の一部を実装のこの問題を解決するために以前に試行に存在するのと同じメカニズム保証が正確に、データの 1 回だけ配信します。 問題を他のソリューションの良い例では、電子データ交換 (EDI)、ANSI X12 制御番号と標準的な 997 機能確認ドキュメント フォーム データを 1 回だけ受信されると、送信者であることを保証の基礎受信側で発生した問題の通知。  
  
 BizTalk Framework での BizTalk Framework プロトコル要件を理解、両方のデータを取引先システム、ただし異なる。  
  
- 予測可能なエンベロープ形式を使用して転送をラップします。  
  
- グローバルに一意の識別子を持つ各送信転送をタグ付けします。  
  
- 済みのデータの場合でも、グローバルに一意の識別子を含む受信確認を送信者に常に返す受信、受信確認、および処理します。  
  
- 何らかの手段を送信者がこれを超える、転送が有効な送信、受信側から受信確認が到着するか、または一定の期間に渡すまでを繰り返すことができます。  
  
  BizTalk Framework アセンブラー パイプライン コンポーネントは、送信および受信確認が、指定した時間に到着しないことを再送信する前に、BizTalk Framework エンベロープとコンテンツをメッセージのシリアル化します。 受信し、配信確認メッセージを処理およびメッセージ インスタンスを削除する責任を負いますもできます。 (送信メッセージのメッセージ インスタンスのコピーは、BizTalk が宛先から受信確認を受け取るまでに、メッセージ ボックス データベースに保持されます。 確認メッセージが受信した後、メッセージ インスタンスは削除、メッセージング エンジンによって。)  
  
## <a name="see-also"></a>参照  
 [BizTalk Framework アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-biztalk-framework-assembler-pipeline-component.md)   
 [パイプライン コンポーネント](../core/pipeline-components.md)