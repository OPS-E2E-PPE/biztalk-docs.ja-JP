---
title: 低待機時間シナリオ Optimizations2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 19cd78ce-ad7d-4e4b-8188-a63d707905d5
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9e5c8c5e225239461c9509aa50c105e4181ba12
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978627"
---
# <a name="low-latency-scenario-optimizations"></a>低待機時間シナリオの最適化
既定では、BizTalk Server は、低待機時間よりもスループットに最適化されています。 次の最適化は、待機時間の短縮が必要な場合のシナリオで、BizTalk Server に適用できます。  
  
> [!NOTE]  
>  これらの最適化は、待機時間が改善されますが、全体的なスループットをいくつかのコストで行うことがあります。  
  
## <a name="increase-the-biztalk-server-host-internal-message-queue-size"></a>BizTalk Server ホストの内部メッセージ キューのサイズを増やす  
 各 BizTalk ホストには、内部のメモリ内キューがあります。 低待機時間シナリオのパフォーマンスを向上させるためには、100 ~ 10,000 の既定値からこのキューのサイズを大ききます。 内部メッセージ キューのサイズの値を変更する方法の詳細については、[リソース ベースのスロットル設定の変更方法](http://go.microsoft.com/fwlink/?LinkID=208366)(http://go.microsoft.com/fwlink/?LinkID=208366) 、BizTalk Server のドキュメントにを参照してください。  
  
> [!NOTE]  
>  内部メッセージ キュー サイズの値を増やすと、ホスト インスタンスによって使用されるメモリが増加します。  
  
## <a name="increase-the-biztalk-server-host-in-process-messages"></a>BizTalk Server ホストのインプロセス メッセージを向上します。  
 パフォーマンスを向上させるために 1000 ~ 10,000 個の既定値からのプロセスでメッセージを増やします。 インプロセス メッセージの値を変更する方法の詳細については、[ホスト制限の既定の設定を変更する方法](http://go.microsoft.com/fwlink/?LinkID=208366)(http://go.microsoft.com/fwlink/?LinkID=208366) 、BizTalk Server のドキュメントにを参照してください。  
  
> [!NOTE]  
>  内部メッセージ キュー サイズの値を増やすと、ホスト インスタンスによって使用されるメモリが増加します。  
  
## <a name="optimize-orchestrations-for-low-latency"></a>低待機時間のオーケストレーションを最適化します。  
 「低待機時間シナリオ オーケストレーションを最適化するための推奨事項」セクションで推奨事項に従って[オーケストレーション パフォーマンスの最適化](../technical-guides/optimizing-orchestration-performance.md)します。  
  
## <a name="configure-polling-intervals"></a>ポーリング間隔を構成します。  
 設定ダッシュ ボードを使用すると、BizTalk グループ全体で特定のホストのポーリング間隔を構成できます。 ポーリング間隔を変更するには。  
  
1. **BizTalk Server 管理コンソール**、展開**BizTalk Server 管理**を右クリックして**BizTalk グループ**、 をクリックし、**設定**.  
  
2. **BizTalk 設定ダッシュ ボード** ダイアログ ボックスで、**ホスト** ページの 、**全般** タブの **ポーリング間隔**が表示されます**メッセージング**と**オーケストレーション**値。 既定では、2 つの値が 500 ミリ秒に設定されます。  
  
   次の表では、BizTalk プロセス内の 64 ビット ホスト (RxHost、TxHost および PxHost) でのテストに使用したポーリング値を示します。 ポーリングを無効にするには、テーブルに一覧されている非常に大きな数値にポーリング間隔を設定できます。  
  
|サーバーのホスト|メッセージング|オーケストレーション|  
|------------------|---------------|-------------------|  
|**RxHost**<br /><br /> のみが公開されますので、一方向で、BizTalk メッセージ ボックスへの着信メッセージの受信場所、RxHost でポーリングは必要ありません (ホストの受信)。|200000|200000|  
|**TxHost**<br /><br /> BizTalk メッセージ ボックスからメッセージング インスタンスを受信しましたがのみ、ために、TxHost (送信ホスト) でポーリングのオーケストレーションは必要ありません。|50|200000|  
|**PxHost**<br /><br /> BizTalk メッセージ ボックスからオーケストレーション インスタンスを受信しましたがのみ、ためポーリングのメッセージングは、(処理ホスト) PxHost で必要ありません。|200000|50|  
  
## <a name="see-also"></a>参照  
 [BizTalk Server パフォーマンスの最適化](../technical-guides/optimizing-biztalk-server-performance.md)