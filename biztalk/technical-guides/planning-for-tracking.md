---
title: "追跡の計画 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8ffc8573-1b4a-47c7-96ab-0471f43facf5
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9853fccde9c5fa6e8c223106c8386f19298d0b9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="planning-for-tracking"></a>追跡の計画
メッセージの追跡は、格納するためのメッセージ本文、メッセージ プロパティ、メタデータなどのメッセージ インスタンスの部分は、データベースでは、通常アーカイブのためのプロセスです。 追跡されているメッセージ インスタンス部分見なすことができます、その後で [グループ ハブ] ページからクエリを実行して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 アーカイブ済みのデータにアクセスするだけでなく、便利なツールを識別して、開発中の問題の修正またはステージング環境の可能性があるライブ データを表示することもできます。  
  
 メッセージの追跡プロセスには、リソースを使用する可能性があります、ため、計画を作成する前に、このトピックの内容を確認してください。  
  
 追跡の詳細については、次を参照してください。[状態と動作状況の追跡](http://go.microsoft.com/fwlink/?LinkId=154187)(http://go.microsoft.com/fwlink/?LinkId=154187)。  
  
## <a name="configuring-and-enabling-the-dta-purge-and-archive-sql-agent-job"></a>構成し有効化、DTA Purge and Archive SQL エージェント ジョブ  
 このジョブをアーカイブしてがあまり大きくならないように、BizTalk 追跡データベースから古いデータを削除します。 これは、正常なために不可欠な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システムです。 追跡データベースを照会する追跡ホストおよびその他のすべてのプロセスのパフォーマンスに影響を与える大きな追跡データベースが開始されます。  
  
-   **DTA Purge and Archive SQL エージェント ジョブが適切に構成された、有効であり、正常に完了することを確認します。** アーカイブ ファイルの書き込み先ディレクトリを含めるようにを構成する必要がありますまずために、このジョブは既定で有効にできません。  
  
-   **ジョブが、受信追跡データが生成された高速の追跡データが削除できることを確認します。** ピーク負荷時の背後に取得するジョブもかまわないが遅れを取り戻すことが常になります。 Purge ジョブでは、背後にあるを取得し、遅延を解消することはありません場合に増加し、BizTalk 追跡データベースは引き続き、パフォーマンスが悪影響を受ける最終的には  
  
-   **論理削除を確認し、物理削除パラメーターを確認するには、なりすぎないように、十分な時間の長いデータを維持しています。** これらのパラメーターの詳細については、次を参照してください。[アーカイブ化および BizTalk 追跡データベースを削除](http://go.microsoft.com/fwlink/?LinkID=153816)(http://go.microsoft.com/fwlink/?LinkID=153816)。  
  
-   **だけ古いデータを削除しないようにする必要がある場合必要があります、最初に、アーカイブし、SQL を変更するエージェント ジョブの"dtasp_PurgeTrackingDatabase"ストアド プロシージャを呼び出します。** これは、アーカイブ手順をスキップし、実行するだけで、パージします。 詳細については、このストアド プロシージャと、使用する SQL エージェント ジョブを変更するを参照してください[BizTalk 追跡データベースからデータを消去する方法](http://go.microsoft.com/fwlink/?LinkID=153817)(http://go.microsoft.com/fwlink/?LinkID=153817)。  
  
-   **BizTalk 追跡データベースのアーカイブ ファイルを保持する必要がある場合は、正常に復元し、それらを使用するプロセスがあることを確認します。**  
  
-   **場合は、BizTalk 追跡データベースを消去して一時的に対処するパフォーマンスの問題があると、不要になった追跡情報を収集する BizTalk を構成する場合、グローバル追跡を無効にすることを検討する可能性があります。** グローバル追跡をオフにする方法については、トピックを参照してください。[グローバル追跡を無効にする方法](http://go.microsoft.com/fwlink/?LinkID=154193)(http://go.microsoft.com/fwlink/?LinkID=154193)。  
  
## <a name="creating-a-dedicated-tracking-host"></a>専用の追跡ホストを作成します。  
 ときにオプション**ホストの追跡を許可する**は BizTalk Server 管理コンソールで、そのホストのインスタンスのホストに、Tracking Data Decode Service (TDDS) から追跡したデータの移動には実行に対して有効で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックスBizTalk 追跡データベースへのデータベースです。 TDDS は、リソースが多用される可能性があります、ためには、対象の「専用」の追跡ホストを作成することを検討してください、**ホストの追跡を許可する**オプションが有効になっており、これが実行されないその他の[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロセス (たとえば、アダプターまたはオーケストレーション)。 BizTalk グループに 1 つ以上の BizTalk server が含まれている場合も TDDS の高可用性を実現する、グループ内の各サーバーでこのホストのインスタンスを作成するベスト プラクティスと見なされます。  
  
## <a name="testing-to-measure-maximum-sustainable-tracking-throughput"></a>維持可能な最大の追跡スループットを測定するテスト  
 広範なメッセージの追跡は、多くのリソースを集中的なアクティビティと適切に管理しない場合のパフォーマンスが極端に悪影響を与えることができます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。 そのための維持可能な最大の追跡スループットを測定する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境システムが維持可能な特定のメッセージ フロー レートで無期限に実行されます。 維持可能な最大の追跡スループットの測定の詳細については、次を参照してください。[維持可能な最大の追跡スループットの測定](http://go.microsoft.com/fwlink/?LinkID=153815)(http://go.microsoft.com/fwlink/?LinkID=153815)。  
  
##  <a name="BKMK_TrackingBP"></a>追跡のベスト プラクティス  
  
-   **計画時に追跡するために必要な情報を決定する**: 追跡、プロジェクトを配置した後は、追跡オプションを設定および履歴データの量を制限できるようにするために必要な情報がステージングの計画時に決定する必要があります必要な情報のみを付与します。  
  
-   **すべてのメッセージを追跡しない**: ことをお勧めできませんのすべてのメッセージを追跡するたびに、メッセージがブラウザーであるため[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]別のコピーを作成します。 特定のポートのみを追跡すると、代わりにスコープを絞ることができます。 これにより、システムのパフォーマンスを最大限にし、データベースをきちんと整頓します。  
  
-   **送信ポートの追跡を設定し、受信パイプラインでの代わりにポート**: パイプラインに追跡オプションを設定する場合、パイプラインを使用するすべてのポートに対してグローバルに追跡オプションは設定もできます。 これは、順番が原因でより多くのデータが意図したものと追跡されているシステムのパフォーマンスが低下します。 代わりに、ポートの送信に追跡オプションを設定し、ポートを受信できます。  
  
-   **BizTalk 追跡データベースのサイズを変更するとき、さまざまな要因を考慮**:  
  
    -   BizTalk 追跡データベースのサイズ変更、コンティンジェンシー乗数を計算の結果に追加することで、インデックス サイズなど、SQL Server の要因を考慮してください。  
  
    -   BizTalk 追跡データベース内のメッセージのサイズを決定するとき、メッセージ コンテキストの平均サイズを追加メッセージのサイズこれは重要な場合メッセージ サイズと比較します。  
  
    -   BizTalk 追跡データベース内のメッセージのサイズを制限するためには、昇格したプロパティの数を制限します。 ルーティングを行うのために必要がある場合、プロパティだけに上位変換を使用する必要があります、それ以外の場合 識別フィールドを使用します。  
  
    -   場合、オーケストレーション**図形の開始と終了**オプションが有効になっている、各オーケストレーション インスタンス内の各図形の開始および停止イベントは、BizTalk 追跡データベースに保存されていることを考慮に入れています。