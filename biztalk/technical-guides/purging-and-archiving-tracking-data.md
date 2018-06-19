---
title: 消去および追跡データをアーカイブ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14094fda-3fd9-4d45-9bbb-cd9377c2cbad
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94a2560bc8a57a8f60bf2d1ebcddf68b62fd178a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302938"
---
# <a name="purging-and-archiving-tracking-data"></a>消去および追跡データをアーカイブ
構成し、DTA Purge and Archive SQL エージェント ジョブを有効にするには重要です。 このジョブをアーカイブして、BizTalk 追跡 (DTA) データベースから古いデータを削除します。 これは、正常なために不可欠な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システムです。 追跡データベースを照会する追跡ホストおよびその他のすべてのプロセスのパフォーマンスに影響を与える大きな追跡データベースが開始されます。 追跡データは追跡データベースから削除されませんが場合、データベースが拡大し続けます。  
  
## <a name="guidelines-for-using-the-dta-purge-and-archive-job"></a>DTA の使用に関するガイドライン Purge and Archive ジョブ  
  
-   **DTA Purge and Archive SQL エージェント ジョブが適切に構成された、有効であり、正常に完了することを確認します。**  
  
     アーカイブ ファイルの書き込み先ディレクトリを含めるようにを構成する必要がありますまずために、このジョブは既定で有効にできません。  
  
-   **だけ古いデータを削除しないようにする必要がある場合必要があります、最初に、アーカイブし、SQL を変更するエージェント ジョブの"dtasp_PurgeTrackingDatabase"ストアド プロシージャを呼び出します。**  
  
     これは、アーカイブ手順をスキップし、実行するだけで、パージします。 詳細については、このストアド プロシージャと、使用する SQL エージェント ジョブを変更するを参照してください[「どのようにパージ データから BizTalk 追跡データベースへ」](http://go.microsoft.com/fwlink/?LinkId=153817) (http://go.microsoft.com/fwlink/?LinkId=153817)。  
  
-   **ジョブが、受信追跡データが生成された高速の追跡データが削除できることを確認します。**  
  
     ピーク負荷時の背後に取得するジョブもかまわないが遅れを取り戻すことが常になります。 Purge ジョブでは、背後にあるを取得し、遅延を解消することはありません場合に増加し、追跡データベースは引き続き、パフォーマンスが悪影響を受ける最終的には  
  
-   **論理削除を確認し、物理最適な時間の長さのデータを保持している場合のようにパラメーターを削除します。**  
  
     これらのパラメーターの詳細については、次を参照してください。 ["アーカイブと削除、BizTalk 追跡データベース"](http://go.microsoft.com/fwlink/?LinkId=153816) (http://go.microsoft.com/fwlink/?LinkId=153816)。  
  
-   **追跡を保持する必要がある場合、ファイルをアーカイブして、正常に復元し、それらを使用するためのプロセスがあることを確認します。**  
  
## <a name="see-also"></a>参照  
 [チェックリスト: SQL Server を構成します。](~/technical-guides/checklist-configuring-sql-server.md)