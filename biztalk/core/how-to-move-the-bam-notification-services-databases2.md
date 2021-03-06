---
title: Services Databases2 の BAM Notification を移動する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Notification Services Application database [BAM]
- Notification Services Instance database [BAM]
- migrating, Notification Services database [BAM]
ms.assetid: 4b7f3397-65c9-4c71-8374-8764f4c2e2e3
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df16514ebd799f08caaea6eddcdc16ee671723a4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384508"
---
# <a name="how-to-move-the-bam-notification-services-databases"></a>BAM Notification Services データベースを移動する方法
ここでは、BAM Notification Services データベースを他のサーバーに移動する手順について説明します。  
  
> [!NOTE]
>  BAM Notification Services Application (BAMAlertsApplication) データベースおよび BAM Notification Services Instance (BAMAlertsNSMain) データベースは、一緒に移動する必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行するには、SQL Server sysadmin 固定サーバーの役割のメンバーであるアカウントを使用してログオンする必要があります。  
  
### <a name="to-move-the-bam-notification-services-databases"></a>BAM Notification Services データベースを移動するには  
  
1. BAM を復元するときに使用する .xml ファイルのコピーを用意します。  
  
   1. をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
   2. コマンド プロンプトで、次のディレクトリに移動します  
  
       **%SystemDrive%\Program Files\Microsoft**  [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **\Tracking**  
  
   3. コマンド プロンプトで、次のように入力します。  
  
      ```  
      Bm.exe get-config –filename:BAMConfiguration.xml  
      ```  
  
      > [!NOTE]
      >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
2. コマンド プロンプトで、次のように入力します。  
  
   ```  
   Net stop NS$BamAlerts  
   ```  
  
3. 古いサーバー上のデータベースをバックアップする方法の SQL Server オンライン ブックの指示に従います。  
  
4. BAM Notification Services データベースを新しい SQL Server にコピーします。  
  
5. SQL Server Books Online に記載されている手順に従い、新しいサーバーにデータベースを復元します。  
  
6. BAMConfiguration.xml ファイルで、Alert DeploymentUnit セクションの ServerName を新しいサーバー名に変更します。  
  
7. BAMConfiguration.xml ファイルを保存して閉じます。  
  
8. をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
9. コマンド プロンプトで、次のディレクトリに移動します  
  
     **%SystemDrive%\Program Files\Microsoft**  [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **\Tracking**  
  
10. コマンド プロンプトで、次のように入力します。  
  
    ```  
    bm.exe update-config -FileName:BAMConfiguration.xml  
    ```  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
11. BAM Notification Services データベース名の参照を更新します。 詳細については、次を参照してください。 [BAM Notification Services データベースへの参照を更新する方法](../core/how-to-update-references-to-the-bam-notification-services-databases.md)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server データベースの移動](../core/moving-biztalk-server-databases.md)