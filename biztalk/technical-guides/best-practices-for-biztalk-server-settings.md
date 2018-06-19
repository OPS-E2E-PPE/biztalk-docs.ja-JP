---
title: BizTalk Server 設定のベスト プラクティス |Microsoft ドキュメント
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
ms.openlocfilehash: bf1f89ced33be6f10ceaae37ccb2c899c4e01eac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299522"
---
# <a name="best-practices-for-biztalk-server-settings"></a>BizTalk Server 設定のベスト プラクティス
このトピックの運用の準備手順を実行する際に従う必要のあるベスト プラクティスの一覧[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。  
  
 **アダプターのパフォーマンスを向上させるメッセージのバッチ処理を構成します。**  
  
-   単一のバッチに 1 つ以上の操作を組み合わせることによって、アダプターによって実行されたトランザクションの数を最小限に抑えます。  
  
-   メッセージの数だけでなく、バッチ内のバイトの合計数に基づいてバッチ サイズを制限します。 バッチ サイズの制限の詳細については、次を参照してください。[アダプターのパフォーマンスを向上させるバッチ処理構成](../technical-guides/configuring-batching-to-improve-adapter-performance.md)です。  
  
 **サイズの大きいメッセージのしきい値を調整します。**  
  
-   スループットを向上させるのにはバッファーに格納されるサイズの大きいメッセージの数を減らすことがサイズの大きいメッセージのしきい値を増やすマッピング中にディスクにします。  
  
 **計画時に追跡するために必要な情報を決定します。**  
  
-   計画段階中には、追跡する必要があります。 情報を決定する必要があります。このように、プロジェクトを配置した後に追跡オプションを設定できに必要な情報のみを付与する追跡データの量を制限できます。  
  
    > [!NOTE]  
    >  追跡に関連するベスト プラクティスに関する詳細については、次を参照してください。[追跡の計画](../technical-guides/planning-for-tracking.md)このガイドでと[状態と動作状況の追跡](http://go.microsoft.com/fwlink/p/?LinkId=154187)(http://go.microsoft.com/fwlink/p/?LinkId=154187)。  
  
 **すべてのメッセージを追跡しません。**  
  
-   いないすべてのメッセージを追跡することをお勧めします。 メッセージの影響を受けるたびに BizTalk Server がメッセージの別のコピーを作成するためです。 特定のポートのみを追跡すると、代わりにスコープを絞ることができます。 これにより、システムのパフォーマンスを最大限にし、データベースをきちんと整頓します。  
  
 **送信ポートの追跡を設定し、受信パイプラインでの代わりにポート**  
  
-   パイプラインに追跡オプションを設定すると、パイプラインを使用するすべてのポートに対してグローバルに追跡オプションも設定されます。 これは、順番が原因でより多くのデータが意図したものと追跡されているシステムのパフォーマンスが低下します。 代わりに、ポートの送信に追跡オプションを設定し、ポートを受信できます。  
  
 **リソース使用率に基づいた制限を調整します。**  
  
-   調整[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]既定では、システムの適切な保護を提供するように構成します。 調整が実行を表示する状態の調整のパフォーマンス カウンターを監視します。 調整上のリソースが基づいている場合を各自で判断し、(たとえば、データベースのサイズまたはメモリ使用率) を下にある、または経由で利用できます。 次に、調整、調整のしきい値が切り上げまたは切り捨てです。 詳細については、次を参照してください。[制限のしきい値の調整: タイミングと理由](http://go.microsoft.com/fwlink/p/?LinkId=154188)(http://go.microsoft.com/fwlink/p/?LinkId=154188)。  
  
 **可能であれば、PassThruTransmit パイプラインを使用します。**  
  
-   宛先にメッセージを送信する前に、ドキュメント処理は必要ありません、XML 送信パイプラインではなく、PassThruTransmit パイプラインを使用します。  
  
 **オーケストレーション「図形の開始と終了」の使用量を最小限に抑えるイベントの追跡**  
  
-   オーケストレーション図形の追跡には、オーケストレーションをデバッグするための明らかな利点がありますが、パフォーマンスとスケーラビリティの問題があります。 **図形の開始と終了**追跡イベントと、大きなオーバーヘッドが発生することができます。 高いスループットが必要な実稼働環境での使用率を最小限に抑えることをお勧めします。  
  
    > [!NOTE]  
    >  **図形の開始と終了**追跡イベントがすべてのオーケストレーションでは既定で有効にします。  
  
## <a name="see-also"></a>参照  
 [チェックリスト: BizTalk Server を構成します。](../technical-guides/checklist-configuring-biztalk-server.md)