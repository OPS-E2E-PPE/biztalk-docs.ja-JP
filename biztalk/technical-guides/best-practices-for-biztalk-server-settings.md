---
title: BizTalk Server 設定のベスト プラクティス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e62024e1-f502-45a8-932f-edd8460bcf5f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 461e2e1a4256d79112e4eec94047c25df34a4511
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001122"
---
# <a name="best-practices-for-biztalk-server-settings"></a>BizTalk Server 設定のベスト プラクティス
このトピックでの運用準備の手順を実行する際に従う必要のあるベスト プラクティス[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
 **アダプターのパフォーマンスを向上させるメッセージのバッチ処理を構成します。**  
  
- 1 つのバッチには、複数の操作を組み合わせることで、アダプターによって実行されるトランザクションの数を最小限に抑えます。  
  
- メッセージの数だけでなく、バッチ内のバイトの合計数に基づいてバッチ サイズを制限します。 バッチ サイズの制限の詳細については、次を参照してください。[アダプターのパフォーマンスを向上させるバッチ処理構成](../technical-guides/configuring-batching-to-improve-adapter-performance.md)します。  
  
  **サイズの大きいメッセージのしきい値を調整します。**  
  
- スループットを向上させるのにはバッファー サイズの大きいメッセージの数の削減サイズの大きいメッセージのしきい値を増やすマッピング中にディスクにします。  
  
  **計画時に追跡する必要がある情報を決定します。**  
  
- 計画段階中には、追跡する必要がある情報を決定する必要があります。これにより、プロジェクトを配置した後に追跡オプションを設定して必要な情報のみを付与する追跡データの量を制限します。  
  
  > [!NOTE]  
  >  追跡に関連するベスト プラクティスの詳細については、次を参照してください。[追跡の計画](../technical-guides/planning-for-tracking.md)このガイドと[状態と動作状況の追跡](http://go.microsoft.com/fwlink/p/?LinkId=154187)(http://go.microsoft.com/fwlink/p/?LinkId=154187)します。  
  
  **すべてのメッセージを追跡しません。**  
  
- すべてのメッセージを追跡しないことをお勧めします。 これは、メッセージにアクセスするたびに BizTalk Server がメッセージの別のコピーを作成するためです。 代わりに、特定のポートだけを追跡することによって、スコープを限定できます。 これにより、システムのパフォーマンスを最大化して、データベースをきちんと整頓します。  
  
  **送信ポートの追跡を設定し、受信パイプラインでの代わりにポート**  
  
- パイプラインに追跡オプションを設定した場合は、パイプラインを使用するすべてのポートに対してグローバルに追跡オプションも設定します。 これは、さらに可能性より多くのデータが意図したものと、追跡されているシステムのパフォーマンスが低下します。 代わりに、ポートの送信に追跡オプションを設定して、ポートを受信できます。  
  
  **リソース使用率に基づく制限を調整します。**  
  
- スロットル[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]既定では、システムの適切な保護を提供するように構成します。 制限の調整が実行を表示する状態のパフォーマンス カウンターを監視します。 自分のゲージでスロットルを適用するリソースが基づいている場合 (たとえば、データベースのサイズまたはメモリ使用率) はまたはの上に使用します。 次に、調整、調整のしきい値は切り上げまたは切り捨てです。 詳細については、次を参照してください。[制限のしきい値の調整: タイミングと理由](http://go.microsoft.com/fwlink/p/?LinkId=154188)(<http://go.microsoft.com/fwlink/p/?LinkId=154188>)。  
  
  **可能であれば、PassThruTransmit パイプラインを使用します。**  
  
- 場合は、宛先にメッセージを送信する前にドキュメントの処理は必要ありませんが、XML 送信パイプラインではなく PassThruTransmit パイプラインを使用します。  
  
  **オーケストレーション「図形の開始と終了」の使用量を最小限に抑えるイベントの追跡**  
  
- オーケストレーション図形の追跡には、オーケストレーションのデバッグの明らかな利点がありますが、パフォーマンスとスケーラビリティに影響があります。 **図形の開始と終了**追跡イベント大きなオーバーヘッドが発生することができます。 高スループットが必要な場合、運用環境におけるその使用を最小限に抑えることをお勧めします。  
  
  > [!NOTE]  
  >  **図形の開始と終了**追跡イベントはすべてのオーケストレーションでは、既定で有効になっています。  
  
## <a name="see-also"></a>参照  
 [チェックリスト: BizTalk Server の構成](../technical-guides/checklist-configuring-biztalk-server.md)