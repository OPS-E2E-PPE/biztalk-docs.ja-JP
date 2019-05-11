---
title: BizTalk Server データベースの移動 |Microsoft Docs
description: などのサービスを停止して、SQL Server エージェント ジョブを使用して、新しいサーバーに BizTalk Server データベースを移行する手順
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec302e6d-c89d-4fe7-849f-97b5566e8ba4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: baa475b4e8e9cbf63cc921451bb7ae19d6857c57
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335903"
---
# <a name="how-to-move-the-biztalk-server-databases"></a>BizTalk Server データベースを移動する方法

## <a name="overview"></a>概要
ここでは、プライマリ [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースを他のサーバーに移動する手順について説明します。 これと同じ基本的な手順を使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースを、ローカルの [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] からリモートの [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] または [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] クラスターに移動することもできます。  

## <a name="prerequisites"></a>前提条件  
メンバーであるアカウントでサインイン、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]この手順を実行する、sysadmin 固定サーバー ロール。  
  
## <a name="move-steps"></a>ステップを移動します。
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サービスをすべて停止します。 詳細については、次を参照してください。 [BizTalk Server サービスの再起動とシャット ダウンの BizTalk Server](how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)します。
  
   > [!IMPORTANT]
   >  データベースを移動する前に、すべての [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サービスおよびジョブが停止していることを必ず確認してください。  
  
2. IIS サービスを停止します。  
  
3. SQL Server エージェント サービスを停止します。  
  
4. 説明されているデータベースのバックアップの手順に従って、BizTalk データベースをバックアップ[バックアップと、BizTalk Server データベースを復元](../core/backing-up-and-restoring-the-biztalk-server-databases.md)します。  
  
5. 次のデータベースの新しいサーバー上の BizTalk データベース復元手順に従って復元[、データベースを復元する方法](../core/how-to-restore-your-databases.md)します。  
  
6. SQL Server エージェント ジョブが、新しいサーバーに転送するため以下で説明されているスクリプト[Back Up and SQL エージェント ジョブを復元する方法](../core/how-to-back-up-and-restore-sql-agent-jobs.md)します。  それぞれのスクリプトを新しいサーバーで実行してジョブを再作成します。  
  
    それぞれのスクリプトを新しいサーバーで実行してジョブを再作成します。 などの特定のジョブ、 **Backup BizTalk Server (BizTalkMsgBoxDb)** ジョブ、しない限り、新しいサーバーのファイル パスとサーバー名は、古いサーバーと同じように再構成する必要があります。  
  
   > [!NOTE]
   >  SSIS または DTS を使用することもできます。**ジョブ転送**タスクのジョブを新しいサーバーに移動するが、ほとんどのユーザーはおそらく方が簡単な SQL Management Studio を使用してジョブのスクリプトを作成します。  
  
7. 前の手順」の説明に従って、SQL Server エージェント ジョブをスクリプトだけでなくする必要がありますログインもスクリプト化」の説明に従って[Back Up and SQL Server ログインを復元する方法](../core/how-to-back-up-and-restore-sql-server-logins.md)します。 これらのログインは、移動先のサーバーに復元する必要があります。  
  
8. 復元、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 9 ~ 22 での手順に従ってデータベース[、データベースを復元する方法](../core/how-to-restore-your-databases.md)します。 この手順によって BizTalk 管理 (BizTalkMgmtDb) データベースおよびレジストリが更新され、BizTalk データベースの新しい場所が反映されます。  
  
   > [!NOTE]
   >  **SampleUpdateInfo.xml**ファイルを新しいサーバーに移動したものを除き、データベースのすべてのコメント。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server データベースの移動](../core/moving-biztalk-server-databases.md)