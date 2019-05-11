---
title: BAM 警告を復旧する方法 |Microsoft Docs
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
ms.openlocfilehash: 5fc3e51593b0a01fb43111f58f01ec07efdc09f4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335618"
---
# <a name="how-to-recover-bam-alerts"></a>BAM 警告を復旧する方法
復旧処理の一環として[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、ビジネス アクティビティ監視 (BAM) を使用している場合は、BAM 警告も復旧する必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 メンバーとしてログオンする必要があります、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators グループにこの手順を実行します。  
  
### <a name="to-recover-bam-alerts-sql-server-2008"></a>BAM 警告 (SQL Server 2008) を復旧するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008**、 をクリックして**構成ツール**をクリックして**Notification Services コマンド プロンプト**します。  
  
2.  コマンド プロンプトで、次のように入力します。  
  
     **nscontrol register-name BamAlerts-サーバー***\<ServerName\>***-service - serviceusername"** *\<ServiceUserName\>* **"-servicepassword"** *\<ServicePassword\>* **"**   
  
     これにより、Notification Services が適切なデータベース (この情報は、nscontrol により、サービス コンピューターのレジストリに保持) にログオンできます。  
  
    > [!IMPORTANT]
    >  新しい Notification Services データベース サーバーを使用して、忘れず、 **-サーバー**サービスを再登録するときのオプションします。 さらに、古いものと、新しい Notification Services サービスの同じユーザー名を使用する必要があります。  
  
3.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
4.  コマンド プロンプトで「:**開始 NS$ BamAlerts を net**します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server を実行しているコンピューターの復旧](../core/recovering-a-computer-running-biztalk-server.md)