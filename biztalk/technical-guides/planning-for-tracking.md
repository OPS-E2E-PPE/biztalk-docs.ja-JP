---
title: 追跡の計画 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ffc8573-1b4a-47c7-96ab-0471f43facf5
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ddfc3a9490bb85169d56526b706c1b159aef8d9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393465"
---
# <a name="planning-for-tracking"></a>追跡の計画
メッセージの追跡は、格納するためのメッセージ本文、メッセージのプロパティやメタデータなどのメッセージ インスタンスの部分はデータベースでは、通常、アーカイブのためのプロセスです。 追跡されるメッセージ インスタンスの部分は、グループ ハブ ページからクエリを実行して、その後表示できます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 アーカイブ済みのデータにアクセスするだけでなく、開発の問題の修正やステージング環境を識別するのに便利なツールは、ライブ データを表示することもできます。  
  
 メッセージの追跡のプロセスは非常にリソースを消費できる、ので、プランを作成する前にこのトピックを確認してください。  
  
 追跡の詳細については、次を参照してください。[状態と動作状況の追跡](http://go.microsoft.com/fwlink/?LinkId=154187)(http://go.microsoft.com/fwlink/?LinkId=154187)します。  
  
## <a name="configuring-and-enabling-the-dta-purge-and-archive-sql-agent-job"></a>構成して有効 DTA Purge and Archive SQL エージェント ジョブ  
 このジョブをアーカイブしてがあまり大きくならないように、BizTalk 追跡データベースから古いデータを削除します。 これは、正常性のために不可欠な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システム。 追跡データベースのクエリを実行すると、追跡ホストの他のプロセスのパフォーマンスに影響を与える大きな追跡データベースが開始されます。  
  
-   **DTA Purge and Archive SQL エージェント ジョブが適切に構成された、有効化、および正常に完了することを確認します。** アーカイブ ファイルの書き込み先のディレクトリを含めるように構成する必要がありますまずために、このジョブは既定で有効にできません。  
  
-   **ジョブが追跡データを受信した追跡データが生成された高速消去できることを確認します。** ジョブの背後にあるをピーク負荷時に取得するのにもかまいませんが、遅延を解消することを必ず。 Purge ジョブでは、背後にある取得し、遅延を解消することはありませんが場合に、増加し、BizTalk 追跡データベースは引き続きし、パフォーマンスが悪影響を受ける最終的には。  
  
-   **論理削除を確認し、ことを確認して物理削除パラメーターがありませんが、十分な時間の長いデータを保持します。** これらのパラメーターの詳細については、次を参照してください。[アーカイブおよび BizTalk 追跡データベースの削除](http://go.microsoft.com/fwlink/?LinkID=153816)(http://go.microsoft.com/fwlink/?LinkID=153816)します。  
  
-   **古いデータを消去しないだけの場合必要があります最初に、アーカイブし、変更、SQL エージェント ジョブ"dtasp_PurgeTrackingDatabase"ストアド プロシージャを呼び出します。** これにより、アーカイブの手順をスキップし、のみ、消去を行います。 ストアド プロシージャおよびそれを使用する SQL エージェント ジョブの変更の詳細については、これはの参照[BizTalk 追跡データベースからのデータの削除方法](http://go.microsoft.com/fwlink/?LinkID=153817)(http://go.microsoft.com/fwlink/?LinkID=153817)します。  
  
-   **BizTalk 追跡データベースにアーカイブ ファイルを保持する必要がある場合は、正常に復元し、それらを使用する場所にプロセスがあることを確認します。**  
  
-   **一時的に、BizTalk 追跡データベースを削除することで対処はパフォーマンスの問題が発生した、不要になった追跡情報を収集する BizTalk を構成する場合は、グローバル追跡を無効にすることを検討する可能性があります。** グローバル追跡を無効にする方法については、トピックを参照してください。[グローバル追跡をオフにする方法](http://go.microsoft.com/fwlink/?LinkID=154193)(http://go.microsoft.com/fwlink/?LinkID=154193)します。  
  
## <a name="creating-a-dedicated-tracking-host"></a>専用の追跡ホストを作成します。  
 ときにオプション**ホストの追跡を許可する**BizTalk Server 管理コンソール、そのホストのインスタンスでホストは、Tracking Data Decode Service (TDDS) からの履歴データを移動の実行が有効になって、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックスBizTalk 追跡データベースへのデータベースです。 TDDS は、リソースの処理を要する可能性があります、ためには、対象の「専用」の追跡ホストを作成することを検討してください、**ホストの追跡を許可する**オプションが有効では実行されません、他の[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)](アダプターまたはオーケストレーション) などのプロセス。 BizTalk グループに 1 つ以上の BizTalk server が含まれている場合も TDDS の高可用性を実現する、グループ内の各サーバーでこのホストのインスタンスを作成するベスト プラクティスと見なされます。  
  
## <a name="testing-to-measure-maximum-sustainable-tracking-throughput"></a>維持可能な最大の追跡スループットを測定するテスト  
 追跡は大量のメッセージは多くのリソースを集中的なアクティビティと適切に管理しない場合のパフォーマンスに非常に悪影響を与えることができます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。 そのための維持可能な最大の追跡スループットを測定する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境システムが維持可能な特定のメッセージ フロー レートで無期限に実行されます。 維持可能な最大の追跡スループットの測定の詳細については、次を参照してください。[維持可能な最大の追跡スループットの測定](http://go.microsoft.com/fwlink/?LinkID=153815)(<http://go.microsoft.com/fwlink/?LinkID=153815>)。  
  
##  <a name="BKMK_TrackingBP"></a> 追跡のベスト プラクティス  
  
- **計画時に追跡する必要がある情報を決定する**:プロジェクトを展開した後に追跡オプションを指定し、追跡データの量を制限して必要な情報だけを取得するために、計画段階中に追跡する情報を決定する必要があります。  
  
- **すべてのメッセージを追跡しない**:すべてのメッセージを追跡しないため、お勧めするたびにメッセージが操作された、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]別のコピーを作成します。 代わりに、特定のポートだけを追跡することによって、スコープを限定できます。 これにより、システムのパフォーマンスを最大化して、データベースをきちんと整頓します。  
  
- **送信ポートの追跡を設定し、受信パイプラインでの代わりにポート**:パイプラインに追跡オプションを設定した場合は、パイプラインを使用するすべてのポートに対してグローバルに追跡オプションも設定します。 これは、さらに可能性より多くのデータが意図したものと、追跡されているシステムのパフォーマンスが低下します。 代わりに、ポートの送信に追跡オプションを設定して、ポートを受信できます。  
  
- **BizTalk 追跡データベースのサイズを変更するとき、さまざまな要因をアカウントにかかる**:  
  
  -   BizTalk 追跡データベースのサイズ変更、コンティンジェンシーの乗数を計算の結果に追加することで、インデックス サイズなど、SQL Server の要因を考慮しています。  
  
  -   BizTalk 追跡データベース内のメッセージのサイズを決定するときにメッセージ コンテキストの平均サイズに追加メッセージのサイズが大幅にある場合メッセージ サイズと比較します。  
  
  -   BizTalk 追跡データベース内のメッセージのサイズを制限するには、昇格したプロパティの数を制限します。 ルーティングの目的で必要な場合のみ使用して昇格させたプロパティ必要があります、識別フィールドを使用して、それ以外の場合。  
  
  -   場合、オーケストレーション**図形の開始と終了**オプションが有効になっている、各オーケストレーション インスタンス内の各図形の開始および停止イベントは、BizTalk 追跡データベースに保存されている考慮に入れています。