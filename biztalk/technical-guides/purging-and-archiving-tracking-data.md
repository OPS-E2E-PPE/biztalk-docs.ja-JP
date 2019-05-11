---
title: 削除とアーカイブ データの追跡 |Microsoft Docs
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
ms.openlocfilehash: 7f18b65d8e33a7a651d743f0ff6cd3292396189a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399559"
---
# <a name="purging-and-archiving-tracking-data"></a>削除とアーカイブ データの追跡
構成して、DTA Purge and Archive SQL エージェント ジョブを有効にするのには重要です。 このジョブをアーカイブして、BizTalk 追跡 (DTA) データベースから古いデータを削除します。 これは、正常性のために不可欠な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システム。 追跡データベースのクエリを実行すると、追跡ホストの他のプロセスのパフォーマンスに影響を与える大きな追跡データベースが開始されます。 追跡データは追跡データベースから削除されませんが場合、データベースは拡張し続けます。  
  
## <a name="guidelines-for-using-the-dta-purge-and-archive-job"></a>DTA の使用に関するガイドラインは、Purge and Archive ジョブ  
  
-   **DTA Purge and Archive SQL エージェント ジョブが適切に構成された、有効化、および正常に完了することを確認します。**  
  
     アーカイブ ファイルの書き込み先のディレクトリを含めるように構成する必要がありますまずために、このジョブは既定で有効にできません。  
  
-   **古いデータを消去しないだけの場合必要があります最初に、アーカイブし、変更、SQL エージェント ジョブ"dtasp_PurgeTrackingDatabase"ストアド プロシージャを呼び出します。**  
  
     これにより、アーカイブの手順をスキップし、のみ、消去を行います。 ストアド プロシージャおよびそれを使用する SQL エージェント ジョブの変更の詳細については、これはの参照[「方法にデータから、BizTalk 追跡データベースの削除」](http://go.microsoft.com/fwlink/?LinkId=153817) (http://go.microsoft.com/fwlink/?LinkId=153817)します。  
  
-   **ジョブが追跡データを受信した追跡データが生成された高速消去できることを確認します。**  
  
     ジョブの背後にあるをピーク負荷時に取得するのにもかまいませんが、遅延を解消することを必ず。 Purge ジョブでは、背後にある取得し、遅延を解消することはありませんが場合、追跡データベースは引き続き拡大、およびパフォーマンスが悪影響を受ける最終的には。  
  
-   **論理削除を確認し、物理最適な時間の長さのデータを保持するようにパラメーターを削除します。**  
  
     これらのパラメーターの詳細については、次を参照してください。 ["アーカイブと削除、BizTalk 追跡データベース"](http://go.microsoft.com/fwlink/?LinkId=153816) (http://go.microsoft.com/fwlink/?LinkId=153816)します。  
  
-   **追跡を維持する必要がある場合、ファイルをアーカイブして、正常に復元し、それらを使用するためのプロセスがあることを確認します。**  
  
## <a name="see-also"></a>参照  
 [チェックリスト:SQL Server の構成](~/technical-guides/checklist-configuring-sql-server.md)