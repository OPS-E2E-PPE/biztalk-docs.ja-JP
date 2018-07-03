---
title: BAM スター スキーマ データベースを 1 に移動する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Star Schema database [BAM], migrating
- migrating, Star Schema database [BAM]
ms.assetid: b4a5f8fc-0dc4-4987-b96f-ecd49bd4dba3
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3068c9d1c72c30c51f77d9fad7b8ddf5881ed09
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983411"
---
# <a name="how-to-move-the-bam-star-schema-database"></a>BAM スター スキーマ データベースを移動する方法
ここでは、BAM スター スキーマ データベースを他のサーバーに移動する手順について説明します。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行するには、SQL Server sysadmin 固定サーバーの役割のメンバーであるアカウントを使用してログオンする必要があります。  
  
### <a name="to-move-the-bam-star-schema-database"></a>BAM スター スキーマ データベースを移動するには  
  
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
  
3. BAM スター スキーマ データベースを新しい SQL Server にコピーします。  
  
4. SQL Server Books Online に記載されている手順に従い、新しいサーバーにデータベースを復元します。  
  
5. BAMConfiguration.xml ファイルで、StarSchemaDatabase DeploymentUnit セクションの ServerName を新しいサーバー名に変更します。  
  
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
  
10. 次の手順を実行して、SQL Connection 2 を更新します。"BAM_AN_" で始まるすべての BAM 分析 DTS パッケージのサーバー名およびデータベース名を変更してください。  
  
    1.  SQL Server Management Studio を使用して、BAM がホストされているサーバーを開きます。  
  
    2.  開く、**データ変換サービス**フォルダー。  
  
    3.  開く、**ローカル パッケージ**フォルダー。  
  
    4.  DTS パッケージを開きをダブルクリック**Connection 2**接続を開きます。  
  
    5.  ドロップダウン ボックスから新しいサーバー名とデータベース名を選択します。  
  
11. 次の手順を実行して、BAM 分析データベースのデータ ソースを更新します。  
  
    1.  SQL Server 分析マネージャーを使用して、BAM 分析データベースをホストするサーバーを展開します。  
  
    2.  開く、**データソース**フォルダー。  
  
    3.  キューブのデータ ソースを右クリックし、をクリックし、**編集**します。  
  
    4.  **接続** タブで、新しいサーバー名と、BAM スター スキーマ データベースのデータベース名を入力し、をクリックし、 **OK**します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server データベースの移動](../core/moving-biztalk-server-databases.md)