---
title: "BizTalk Framework アセンブラー パイプライン コンポーネント |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components, BizTalk Framework Assembler
- BizTalk Framework Assembler [pipeline component]
ms.assetid: 116dff8d-b7f8-4564-a7fb-6440682683dc
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 777e3d98ade5b4e0c54744cea6d37b1e43717e66
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-framework-assembler-pipeline-component"></a>BizTalk Framework アセンブラー パイプライン コンポーネント
BizTalk Framework は、HTTP または SMTP などの、回線上で使用できるトランスポート プロトコルを使用して、1 回限りの確実な配信を行うための方法の 1 つです。 このフレームワークは 1998 年から存在し、Web サービス (特に WSReliable) に基づいた、標準的なイニシアチブの先駆けと見なすことができます。 一般的に、1 回限りの確実なデータ配信の問題点は、メッセージ キュー (MSMQ とも呼ばれる) のようなテクノロジに関するものでした。 通常、このようなテクノロジでは、データ フローの両端のエンドポイントに共通のソフトウェアが必要となります。また、インターネットによる企業間のデータ通信などで必要となる、パブリック ネットワークに基づいたオープンなトランスポート プロトコルも使用できません。  
  
 BizTalk Framework には、1 回限りの確実なデータ配信に関する問題を解決するためのメカニズムがいくつか実装されています。これらのメカニズムは、問題解決のために以前に試行されたことのあるメカニズムです。 また、このような問題に対するソリューションの一例として、電子データ交換 (EDI) があります。これは、ANSI X12 制御番号と標準的な 997 の機能確認ドキュメントが基盤となっており、データの 1 回限りの受信、および受信側で発生した問題が送信側に通知されることが保証されます。  
  
 ただし、BizTalk Framework では、データを交換するシステムが異なっていても、両方のシステムで BizTalk Framework プロトコルの次の要件を認識できることが前提となっています。  
  
-   転送をラップするための予測可能なエンベロープ形式の使用。  
  
-   グローバル一意識別子による各送信転送へのタグ付け。  
  
-   既に受信したデータ、確認したデータ、および処理されたデータに対しても、グローバル一意識別子を含む受信確認が送信側に必ず返されること。  
  
-   受信側からの確認メッセージを受け取るか、転送が無効とされる一定の期間が経過するまで、送信側が転送を繰り返す何らかの方法があること。  
  
 BizTalk Framework アセンブラー パイプライン コンポーネントは、転送前に BizTalk Framework のエンベロープとコンテンツをメッセージにシリアル化し、指定した時間内に確認メッセージが配信されない場合はメッセージを再送信する役割を果たします。 また、確認メッセージを受信および処理して、メッセージ インスタンスを削除します  (送信メッセージのメッセージ インスタンスのコピーは、BizTalk が送信先から確認メッセージを受け取るまで、メッセージ ボックス データベース内に保存されます。 確認メッセージを受け取ると、メッセージング エンジンによってメッセージ インスタンスが削除されます)。  
  
## <a name="see-also"></a>参照  
 [BizTalk Framework アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-biztalk-framework-assembler-pipeline-component.md)   
 [パイプライン コンポーネント](../core/pipeline-components.md)