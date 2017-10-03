---
title: "低待機時間シナリオ Optimizations2 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19cd78ce-ad7d-4e4b-8188-a63d707905d5
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 009b1298e90b586830f062c8e884b88995f9e33f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="low-latency-scenario-optimizations"></a>低待機時間シナリオの最適化
既定では、BizTalk Server は、低待機時間ではなく、スループットに最適です。 次の最適化は、待機時間の削減の必要があるシナリオで、BizTalk Server に適用できます。  
  
> [!NOTE]  
>  これらの最適化は、待機時間が改善されますが、全体的なスループットにいくつかのコストで行うことがあります。  
  
## <a name="increase-the-biztalk-server-host-internal-message-queue-size"></a>BizTalk Server ホストの内部メッセージ キューのサイズを増やす  
 各 BizTalk ホストでは、内部のメモリ内キューがあります。 低待機時間シナリオでパフォーマンスを向上させるためには、100 ~ 10,000 の既定値からこのキューのサイズが増加します。 内部メッセージ キュー サイズの値を変更する方法の詳細については、次を参照してください。[リソース ベースの調整設定の変更方法](http://go.microsoft.com/fwlink/?LinkID=208366)(http://go.microsoft.com/fwlink/?LinkID=208366)、BizTalk Server のドキュメントにします。  
  
> [!NOTE]  
>  内部メッセージ キューのサイズ値を増やすと、ホスト インスタンスによって使用されるメモリを増やします。  
  
## <a name="increase-the-biztalk-server-host-in-process-messages"></a>BizTalk Server ホストのインプロセス メッセージを向上します。  
 パフォーマンスを向上させるために 1000 ~ 10,000 の既定値からのインプロセス メッセージを大ききます。 インプロセス メッセージの値を変更する方法の詳細については、次を参照してください。[ホストの制限の既定の設定を変更する方法](http://go.microsoft.com/fwlink/?LinkID=208366)(http://go.microsoft.com/fwlink/?LinkID=208366)、BizTalk Server のドキュメントにします。  
  
> [!NOTE]  
>  内部メッセージ キューのサイズ値を増やすと、ホスト インスタンスによって使用されるメモリを増やします。  
  
## <a name="optimize-orchestrations-for-low-latency"></a>低待機時間のオーケストレーションを最適化します。  
 「低待機時間シナリオでオーケストレーションを最適化するための推奨事項」セクションの推奨事項に従って[オーケストレーション パフォーマンスの最適化](../technical-guides/optimizing-orchestration-performance.md)です。  
  
## <a name="configure-polling-intervals"></a>ポーリング間隔を構成します。  
 設定ダッシュ ボードを使用すると、BizTalk グループ全体では特定のホストのポーリング間隔を構成できます。 ポーリング間隔を変更します。  
  
1.  **BizTalk Server 管理コンソール**、展開**BizTalk Server 管理コンソール**を右クリックして**BizTalk グループ**、クリックして**設定**.  
  
2.  **BizTalk 設定ダッシュ ボード** ダイアログ ボックスで、**ホスト** ページで 、**全般** タブの **ポーリング間隔**が表示されます**メッセージング**と**オーケストレーション**値。 既定では、これら両方の値は 500 ミリ秒に設定されます。  
  
 次の表は、BizTalk プロセス内の 64 ビット ホスト (RxHost、TxHost および PxHost) 上でのテストを使用したポーリングの値を一覧表示します。 ポーリングを無効にするには、非常に多数の表に一覧されているにポーリング間隔を設定できます。  
  
|サーバーのホスト|メッセージング|オーケストレーション|  
|------------------|---------------|-------------------|  
|**RxHost**<br /><br /> おのみをパブリッシュするため、BizTalk メッセージ ボックスで、一方向の受信メッセージの受信場所、ポーリングは、RxHost では必要ありません (受信ホスト)。|200000|200000|  
|**TxHost**<br /><br /> おのみメッセージング インスタンスから受信 BizTalk メッセージ ボックス、ためポーリングのオーケストレーションは TxHost (送信ホスト) では必要ありません。|50|200000|  
|**PxHost**<br /><br /> 私たちがのみのオーケストレーション インスタンスから受信 BizTalk メッセージ ボックス、ためポーリングをメッセージングで必要はありません (処理ホスト) PxHost です。|200000|50|  
  
## <a name="see-also"></a>参照  
 [BizTalk Server のパフォーマンスを最適化します。](../technical-guides/optimizing-biztalk-server-performance.md)