---
title: "BAM スター スキーマ データベース 1 に移動する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Star Schema database [BAM], migrating
- migrating, Star Schema database [BAM]
ms.assetid: b4a5f8fc-0dc4-4987-b96f-ecd49bd4dba3
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6661a9ae315988a5348198fa463e24ea508cf50f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-move-the-bam-star-schema-database"></a>BAM スター スキーマ データベースを移動する方法
ここでは、BAM スター スキーマ データベースを他のサーバーに移動する手順について説明します。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行するには、SQL Server sysadmin 固定サーバーの役割のメンバーであるアカウントを使用してログオンする必要があります。  
  
### <a name="to-move-the-bam-star-schema-database"></a>BAM スター スキーマ データベースを移動するには  
  
1.  BAM を復元するときに使用する .xml ファイルのコピーを用意します。  
  
    1.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
    2.  コマンド プロンプトで、次のディレクトリに移動します  
  
         [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]追跡  
  
    3.  コマンド プロンプトで、次のように入力します。  
  
        ```  
        Bm.exe get-config –filename:BAMConfiguration.xml  
        ```  
  
        > [!NOTE]
        >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
2.  古いサーバー上のデータベースをバックアップする方法 SQL Server オンライン ブックの指示に従います。  
  
3.  BAM スター スキーマ データベースを新しい SQL Server にコピーします。  
  
4.  SQL Server Books Online に記載されている手順に従い、新しいサーバーにデータベースを復元します。  
  
5.  BAMConfiguration.xml ファイルで、StarSchemaDatabase DeploymentUnit セクションの ServerName を新しいサーバー名に変更します。  
  
6.  BAMConfiguration.xml ファイルを保存して閉じます。  
  
7.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
8.  コマンド プロンプトで、次のディレクトリに移動します  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]追跡  
  
9. コマンド プロンプトで、次のように入力します。  
  
    ```  
    bm.exe update-config -FileName:BAMConfiguration.xml  
    ```  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
10. 次の手順を実行して、SQL Connection 2 を更新します。"BAM_AN_" で始まるすべての BAM 分析 DTS パッケージのサーバー名およびデータベース名を変更してください。  
  
    1.  SQL Server Management Studio を使用して、BAM がホストされているサーバーを開きます。  
  
    2.  開く、**データ変換サービス**フォルダーです。  
  
    3.  開く、**ローカル パッケージ**フォルダーです。  
  
    4.  DTS パッケージを開き、ダブルクリックして**接続 2**接続を開きます。  
  
    5.  ドロップダウン ボックスから新しいサーバー名とデータベース名を選択します。  
  
11. 次の手順を実行して、BAM 分析データベースのデータ ソースを更新します。  
  
    1.  SQL Server 分析マネージャーを使用して、BAM 分析データベースをホストするサーバーを展開します。  
  
    2.  開く、**データソース**フォルダーです。  
  
    3.  キューブのデータ ソースを右クリックし、をクリックして**編集**です。  
  
    4.  **接続** タブで、新しいサーバー名および BAM スター スキーマ データベースのデータベース名を入力し、をクリックして**OK**です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server データベースの移動](../core/moving-biztalk-server-databases.md)