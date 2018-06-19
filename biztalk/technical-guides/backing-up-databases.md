---
title: データベースのバックアップ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0524a8f0-15a3-4731-a7bd-c0c935fff6c8
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6a4b40be0a9a7d4846dd965a4d9f934e69690e7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22300538"
---
# <a name="backing-up-databases"></a>データベースのバックアップ
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]複数データベース間で分散トランザクションを使用して、BizTalk Server のバックアップ ジョブがすべての同期のバックアップを作成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。 これは、「完全な」データベースの復旧モデルでのトランザクションのマークを使用して行われます。 これは、機能は、データベース間で一貫性をするのには、バックアップに必要です。 詳細については、次を参照してください。 ["マークされたトランザクション、完全バックアップ、およびログのバックアップ"](http://go.microsoft.com/fwlink/?LinkId=151565) (http://go.microsoft.com/fwlink/?LinkId=151565)、BizTalk Server のドキュメントにします。  
  
## <a name="advantages-of-the-backup-biztalk-server-job"></a>バックアップの BizTalk Server のジョブの利点  
 BizTalk Server のバックアップ ジョブは、唯一のサポートされている方法をバックアップするため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。 使用[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]をバックアップするジョブ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実稼働環境でのデータベースはサポートされていません。  
  
 場合、バックアップ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブは実行されず、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース トランザクション ログが無限に増大します。 バックアップ ジョブには、それらが増え続ける境界のないトランザクションのログが切り捨てられます。 場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース トランザクション ログが拡大し続ける、ことがある時点で埋めるに格納するディスクです。  
  
> [!NOTE]  
>  両方のバックアップを使用して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブおよびログ配布が現在のみ完全に文書化されを実行するためのメソッドをサポート[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースのバックアップと復元します。  
  
## <a name="guidelines-for-the-backup-biztalk-server-job"></a>バックアップの BizTalk Server のジョブに関するガイドライン  
 全体を復元する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境を定期的にします。 これには、SQL server だけでなくが含まれますと[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースも実行しているコンピューター[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。 文書化し、実際に障害が発生する前に、これらの手順を練習する必要があります。  
  
> [!NOTE]  
>  バックアップ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブでは、古いバックアップ ファイルは削除されません。 定義し、古いバックアップ ファイルをアーカイブし、バックアップ ジョブを使用するバックアップのディレクトリから移動するプロセスを導入する必要があります。  
  
## <a name="additional-resources"></a>その他のリソース  
 次のトピックを参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ドキュメント。  
  
-   固有の仕様の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]バックアップし復元のタスクを参照してください[「チェックリスト:: バックアップと復元」](http://go.microsoft.com/fwlink/?LinkId=154070) (http://go.microsoft.com/fwlink/?LinkId=154070)。  
  
-   バックアップと復元の概要については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください["および復元する BizTalk Server のバックアップ"](http://go.microsoft.com/fwlink/?LinkId=154071) (http://go.microsoft.com/fwlink/?LinkId=154071)。  
  
-   BizTalk Server のバックアップ ジョブを構成する方法の詳細については、次を参照してください。 ["方法に構成 Backup BizTalk Server ジョブ"](http://go.microsoft.com/fwlink/?LinkId=154072) (http://go.microsoft.com/fwlink/?LinkId=154072)。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server のログ配布災害復旧を使用します。](../technical-guides/using-biztalk-server-log-shipping-for-disaster-recovery.md)