---
title: BAM Analysis の Database2 を移動する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migrating, Analysis database [BAM]
- Analysis database [BAM], migrating
ms.assetid: b0320273-4840-4573-bb82-bba95021535e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9f0afd5c8bbd06786c07b84dd465f97cbb1559d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384518"
---
# <a name="how-to-move-the-bam-analysis-database"></a>BAM 分析データベースを移動する方法
この手順を使用すると、BAM 分析データベースを別のサーバーに移動します。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行するには、SQL Server sysadmin 固定サーバーの役割のメンバーであるアカウントを使用してログオンする必要があります。  
  
### <a name="to-move-the-bam-analysis-database"></a>BAM 分析データベースを移動するには  
  
1. BAM を復元するときに使用する .xml ファイルのコピーを用意します。  
  
   1. をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
   2. コマンド プロンプトで、次のディレクトリに移動します  
  
       [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]追跡  
  
   3. コマンド プロンプトで、次のように入力します。  
  
      ```  
      Bm.exe get-config –filename:BAMConfiguration.xml  
      ```  
  
      > [!NOTE]
      >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
2. 古いサーバー上のデータベースをバックアップする方法の SQL Server オンライン ブックの指示に従います。  
  
3. BAM 分析データベースを新しい SQL Server にコピーします。  
  
4. SQL Server Books Online に記載されている手順に従い、新しいサーバーにデータベースを復元します。  
  
5. BAMConfiguration.xml ファイルを編集し、AnalysisDatabase DeploymentUnit セクションの ServerName を新しいサーバー名に変更します。  
  
6. BAMConfiguration.xml ファイルを保存して閉じます。  
  
7. をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
8. コマンド プロンプトで、次のディレクトリに移動します  
  
    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]追跡  
  
9. コマンド プロンプトで、次のように入力します。  
  
    ```  
    bm.exe update-config -FileName:BAMConfiguration.xml  
    ```  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server データベースの移動](../core/moving-biztalk-server-databases.md)