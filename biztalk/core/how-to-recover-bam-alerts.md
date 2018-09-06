---
title: BAM 警告を復旧する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 56c477b4-4605-4763-b20a-3baf4529f13f
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec36491dd7368e0e2fdbcd8fb5abab9d840c6b1e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972544"
---
# <a name="how-to-recover-bam-alerts"></a>BAM 警告を復旧する方法
ビジネス アクティビティの監視 (BAM) を使用している場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の復旧処理の一環として BAM 警告を復旧する必要もあります。  
  
## <a name="prerequisites"></a>前提条件  
 メンバーとしてログオンする必要があります、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators グループにこの手順を実行します。  
  
### <a name="to-recover-bam-alerts-sql-server-2008"></a>BAM 警告 (SQL Server 2008) を復旧するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008**をクリックして**構成ツール**をクリックして**Notification Services コマンド プロンプト**です。  
  
2.  コマンド プロンプトで、次のように入力します。  
  
     **nscontrol register-name BamAlerts-サーバー***\<ServerName\>***-サービス - serviceusername"** *\<ServiceUserName\>* **"-servicepassword"** *\<ServicePassword\>* **"**   
  
     これにより、Notification Services が、適切なデータベース (この情報は、nscontrol により、サービス コンピューターのレジストリに保持) にログオンします。  
  
    > [!IMPORTANT]
    >  新しい Notification Services データベース サーバーを使用してください、 **-サーバー**サービスの再登録オプションを選択します。 また、新しい Notification Services サービスには、以前と同じユーザー名を使用する必要があります。  
  
3.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
4.  コマンド プロンプトで次のように入力します。: **「net start NS$ BamAlerts**です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server を実行しているコンピューターの復旧](../core/recovering-a-computer-running-biztalk-server.md)