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
# <a name="how-to-move-the-bam-star-schema-database"></a><span data-ttu-id="ffd9b-102">BAM スター スキーマ データベースを移動する方法</span><span class="sxs-lookup"><span data-stu-id="ffd9b-102">How to Move the BAM Star Schema Database</span></span>
<span data-ttu-id="ffd9b-103">ここでは、BAM スター スキーマ データベースを他のサーバーに移動する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="ffd9b-103">You can use this procedure to move the BAM Star Schema database to another server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ffd9b-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="ffd9b-104">Prerequisites</span></span>  
 <span data-ttu-id="ffd9b-105">この手順を実行するには、SQL Server sysadmin 固定サーバーの役割のメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ffd9b-105">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-move-the-bam-star-schema-database"></a><span data-ttu-id="ffd9b-106">BAM スター スキーマ データベースを移動するには</span><span class="sxs-lookup"><span data-stu-id="ffd9b-106">To move the BAM Star Schema database</span></span>  
  
1. <span data-ttu-id="ffd9b-107">BAM を復元するときに使用する .xml ファイルのコピーを用意します。</span><span class="sxs-lookup"><span data-stu-id="ffd9b-107">Get a copy of the .xml file used for restoring BAM:</span></span>  
  
   1. <span data-ttu-id="ffd9b-108">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="ffd9b-108">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
   2. <span data-ttu-id="ffd9b-109">コマンド プロンプトで、次のディレクトリに移動します</span><span class="sxs-lookup"><span data-stu-id="ffd9b-109">At the command prompt, navigate to the following directory:</span></span>  
  
       [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="ffd9b-110">追跡</span><span class="sxs-lookup"><span data-stu-id="ffd9b-110">Tracking</span></span>  
  
   3. <span data-ttu-id="ffd9b-111">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="ffd9b-111">At the command prompt, type:</span></span>  
  
      ```  
      Bm.exe get-config –filename:BAMConfiguration.xml  
      ```  
  
      > [!NOTE]
      >  <span data-ttu-id="ffd9b-112">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="ffd9b-112">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
2. <span data-ttu-id="ffd9b-113">古いサーバー上のデータベースをバックアップする方法の SQL Server オンライン ブックの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="ffd9b-113">Follow the instructions in SQL Server Books Online on how to back up the database on the old server.</span></span>  
  
3. <span data-ttu-id="ffd9b-114">BAM スター スキーマ データベースを新しい SQL Server にコピーします。</span><span class="sxs-lookup"><span data-stu-id="ffd9b-114">Copy the BAM Star Schema database to the new SQL Server.</span></span>  
  
4. <span data-ttu-id="ffd9b-115">SQL Server Books Online に記載されている手順に従い、新しいサーバーにデータベースを復元します。</span><span class="sxs-lookup"><span data-stu-id="ffd9b-115">Follow the instructions in SQL Server Books Online on how to restore the database on the new server.</span></span>  
  
5. <span data-ttu-id="ffd9b-116">BAMConfiguration.xml ファイルで、StarSchemaDatabase DeploymentUnit セクションの ServerName を新しいサーバー名に変更します。</span><span class="sxs-lookup"><span data-stu-id="ffd9b-116">Edit the BAMConfiguration.xml file and change the ServerName in the StarSchemaDatabase DeploymentUnit section to the new server name.</span></span>  
  
6. <span data-ttu-id="ffd9b-117">BAMConfiguration.xml ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="ffd9b-117">Save and close the BAMConfiguration.xml file.</span></span>  
  
7. <span data-ttu-id="ffd9b-118">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="ffd9b-118">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
8. <span data-ttu-id="ffd9b-119">コマンド プロンプトで、次のディレクトリに移動します</span><span class="sxs-lookup"><span data-stu-id="ffd9b-119">At the command prompt, navigate to the following directory:</span></span>  
  
    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="ffd9b-120">追跡</span><span class="sxs-lookup"><span data-stu-id="ffd9b-120">Tracking</span></span>  
  
9. <span data-ttu-id="ffd9b-121">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="ffd9b-121">At the command prompt, type:</span></span>  
  
    ```  
    bm.exe update-config -FileName:BAMConfiguration.xml  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="ffd9b-122">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="ffd9b-122">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
10. <span data-ttu-id="ffd9b-123">次の手順を実行して、SQL Connection 2 を更新します。"BAM_AN_" で始まるすべての BAM 分析 DTS パッケージのサーバー名およびデータベース名を変更してください。</span><span class="sxs-lookup"><span data-stu-id="ffd9b-123">Update SQL Connection 2 to change the server and database name in all BAM analysis DTS packages, which are prefixed with "BAM_AN_", by following these steps:</span></span>  
  
    1.  <span data-ttu-id="ffd9b-124">SQL Server Management Studio を使用して、BAM がホストされているサーバーを開きます。</span><span class="sxs-lookup"><span data-stu-id="ffd9b-124">Using SQL Server Management Studio, open the server hosting BAM.</span></span>  
  
    2.  <span data-ttu-id="ffd9b-125">開く、**データ変換サービス**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="ffd9b-125">Open the **Data Transformation Services** folder.</span></span>  
  
    3.  <span data-ttu-id="ffd9b-126">開く、**ローカル パッケージ**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="ffd9b-126">Open the **Local Packages** folder.</span></span>  
  
    4.  <span data-ttu-id="ffd9b-127">DTS パッケージを開きをダブルクリック**Connection 2**接続を開きます。</span><span class="sxs-lookup"><span data-stu-id="ffd9b-127">Open the DTS package, and then double-click **Connection 2** to open the connection.</span></span>  
  
    5.  <span data-ttu-id="ffd9b-128">ドロップダウン ボックスから新しいサーバー名とデータベース名を選択します。</span><span class="sxs-lookup"><span data-stu-id="ffd9b-128">Select the new server and database name in the drop-down box.</span></span>  
  
11. <span data-ttu-id="ffd9b-129">次の手順を実行して、BAM 分析データベースのデータ ソースを更新します。</span><span class="sxs-lookup"><span data-stu-id="ffd9b-129">Update the data source in the BAM Analysis database as follows:</span></span>  
  
    1.  <span data-ttu-id="ffd9b-130">SQL Server 分析マネージャーを使用して、BAM 分析データベースをホストするサーバーを展開します。</span><span class="sxs-lookup"><span data-stu-id="ffd9b-130">Using SQL Server Analysis Manager, open the server hosting the BAM Analysis database.</span></span>  
  
    2.  <span data-ttu-id="ffd9b-131">開く、**データソース**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="ffd9b-131">Open the **Data Sources** folder.</span></span>  
  
    3.  <span data-ttu-id="ffd9b-132">キューブのデータ ソースを右クリックし、をクリックし、**編集**します。</span><span class="sxs-lookup"><span data-stu-id="ffd9b-132">Right-click the data source for the cube, and then click **Edit**.</span></span>  
  
    4.  <span data-ttu-id="ffd9b-133">**接続** タブで、新しいサーバー名と、BAM スター スキーマ データベースのデータベース名を入力し、をクリックし、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="ffd9b-133">On the **Connection** tab, type the new server name and database name for the BAM Star Schema database, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffd9b-134">参照</span><span class="sxs-lookup"><span data-stu-id="ffd9b-134">See Also</span></span>  
 [<span data-ttu-id="ffd9b-135">BizTalk Server データベースの移動</span><span class="sxs-lookup"><span data-stu-id="ffd9b-135">Moving BizTalk Server Databases</span></span>](../core/moving-biztalk-server-databases.md)