---
title: "BizTalk Server データベースを移動 |Microsoft ドキュメント"
description: "BizTalk Server データベースを含むサービスを停止して、SQL Server エージェント ジョブを使用して、新しいサーバーに移動する手順"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ec302e6d-c89d-4fe7-849f-97b5566e8ba4
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12bd1d6bc8a46d4e63dc69166d87f3678a0e3272
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-move-the-biztalk-server-databases"></a>BizTalk Server データベースを移動する方法

## <a name="overview"></a>概要
ここでは、プライマリ [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースを他のサーバーに移動する手順について説明します。 これと同じ基本的な手順を使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースを、ローカルの [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] からリモートの [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] または [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] クラスターに移動することもできます。  

## <a name="prerequisites"></a>前提条件  
メンバーであるアカウントでサインイン、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin 固定サーバー ロールにこの手順を実行します。  
  
## <a name="move-steps"></a>手順を移動します。
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サービスをすべて停止します。 詳細については、次を参照してください。 [BizTalk Server サービスの再起動とシャット ダウンの BizTalk Server](how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)です。
  
    > [!IMPORTANT]
    >  データベースを移動する前に、すべての [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サービスおよびジョブが停止していることを必ず確認してください。  
  
2.  IIS サービスを停止します。  
  
3.  SQL Server エージェント サービスを停止します。  
  
4.  」の説明に従って、データベース バックアップの手順に従って、BizTalk データベースをバックアップ[をバックアップおよび BizTalk Server データベースの復元](../core/backing-up-and-restoring-the-biztalk-server-databases.md)です。  
  
5.  新しいサーバーで、次のデータベース、BizTalk データベースの復元時にプロシージャ復元[、データベースを復元する方法](../core/how-to-restore-your-databases.md)です。  
  
6.  SQL Server エージェント ジョブは、以下に示す、新しいサーバーに転送するための説明に従ってスクリプト[Back Up and SQL エージェント ジョブを復元する方法](../core/how-to-back-up-and-restore-sql-agent-jobs.md)です。  それぞれのスクリプトを新しいサーバーで実行してジョブを再作成します。  
  
     それぞれのスクリプトを新しいサーバーで実行してジョブを再作成します。 などの特定のジョブ、 **BizTalk Server のバックアップ (BizTalkMsgBoxDb)**ジョブに、新しいサーバーのファイル パスとサーバー名は、古いサーバーと同じ場合を除き、再構成する必要があります。  
  
    > [!NOTE]
    >  SSIS または DTS を使用することもできます。**ジョブ転送**タスクは、新しいサーバーにジョブを移動するが、ほとんどのユーザーはおそらくほうが簡単な SQL Management Studio を使用してジョブのスクリプトを作成します。  
  
7.  SQL Server エージェント ジョブのスクリプトを作成して、前の手順」の説明に従って、に加えてする必要がありますログインもスクリプト」の説明に従って[Back Up and SQL Server ログインを復元する方法](../core/how-to-back-up-and-restore-sql-server-logins.md)です。 これらのログインは、移動先のサーバーに復元する必要があります。  
  
8.  復元、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースを次の手順 9. ~ 22. [、データベースを復元する方法](../core/how-to-restore-your-databases.md)です。 この手順によって BizTalk 管理 (BizTalkMgmtDb) データベースおよびレジストリが更新され、BizTalk データベースの新しい場所が反映されます。  
  
    > [!NOTE]
    >  **SampleUpdateInfo.xml**ファイルをすべてコメント アウトを除き、データベースの新しいサーバーに移動されました。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server データベースの移動](../core/moving-biztalk-server-databases.md)