---
title: "BAM Analysis Database2 を移動する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- migrating, Analysis database [BAM]
- Analysis database [BAM], migrating
ms.assetid: b0320273-4840-4573-bb82-bba95021535e
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f9ae627dffd36ceca78e7da0b9e8e516845691a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-move-the-bam-analysis-database"></a><span data-ttu-id="8cd2c-102">BAM 分析データベースを移動する方法</span><span class="sxs-lookup"><span data-stu-id="8cd2c-102">How to Move the BAM Analysis Database</span></span>
<span data-ttu-id="8cd2c-103">ここでは、BAM 分析データベースを他のサーバーに移動する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="8cd2c-103">You can use this procedure to move the BAM Analysis database to another server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8cd2c-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="8cd2c-104">Prerequisites</span></span>  
 <span data-ttu-id="8cd2c-105">この手順を実行するには、SQL Server sysadmin 固定サーバーの役割のメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cd2c-105">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-move-the-bam-analysis-database"></a><span data-ttu-id="8cd2c-106">BAM 分析データベースを移動するには</span><span class="sxs-lookup"><span data-stu-id="8cd2c-106">To move the BAM Analysis database</span></span>  
  
1.  <span data-ttu-id="8cd2c-107">BAM を復元するときに使用する .xml ファイルのコピーを用意します。</span><span class="sxs-lookup"><span data-stu-id="8cd2c-107">Get a copy of the .xml file used for restoring BAM:</span></span>  
  
    1.  <span data-ttu-id="8cd2c-108">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="8cd2c-108">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="8cd2c-109">コマンド プロンプトで、次のディレクトリに移動します</span><span class="sxs-lookup"><span data-stu-id="8cd2c-109">At the command prompt, navigate to the following directory:</span></span>  
  
         [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="8cd2c-110">追跡</span><span class="sxs-lookup"><span data-stu-id="8cd2c-110">Tracking</span></span>  
  
    3.  <span data-ttu-id="8cd2c-111">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8cd2c-111">At the command prompt, type:</span></span>  
  
        ```  
        Bm.exe get-config –filename:BAMConfiguration.xml  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="8cd2c-112">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="8cd2c-112">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
2.  <span data-ttu-id="8cd2c-113">古いサーバー上のデータベースをバックアップする方法 SQL Server オンライン ブックの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="8cd2c-113">Follow the instructions in SQL Server Books Online on how to back up the database on the old server.</span></span>  
  
3.  <span data-ttu-id="8cd2c-114">BAM 分析データベースを新しい SQL Server にコピーします。</span><span class="sxs-lookup"><span data-stu-id="8cd2c-114">Copy the BAM Analysis database to the new SQL Server.</span></span>  
  
4.  <span data-ttu-id="8cd2c-115">SQL Server Books Online に記載されている手順に従い、新しいサーバーにデータベースを復元します。</span><span class="sxs-lookup"><span data-stu-id="8cd2c-115">Follow the instructions in SQL Server Books Online on how to restore the database on the new server.</span></span>  
  
5.  <span data-ttu-id="8cd2c-116">BAMConfiguration.xml ファイルで、AnalysisDatabase DeploymentUnit セクションの ServerName を新しいサーバー名に変更します。</span><span class="sxs-lookup"><span data-stu-id="8cd2c-116">Edit the BAMConfiguration.xml file and change the ServerName in the AnalysisDatabase DeploymentUnit section to the new server name.</span></span>  
  
6.  <span data-ttu-id="8cd2c-117">BAMConfiguration.xml ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="8cd2c-117">Save and close the BAMConfiguration.xml file.</span></span>  
  
7.  <span data-ttu-id="8cd2c-118">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="8cd2c-118">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="8cd2c-119">コマンド プロンプトで、次のディレクトリに移動します</span><span class="sxs-lookup"><span data-stu-id="8cd2c-119">At the command prompt, navigate to the following directory:</span></span>  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="8cd2c-120">追跡</span><span class="sxs-lookup"><span data-stu-id="8cd2c-120">Tracking</span></span>  
  
9. <span data-ttu-id="8cd2c-121">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8cd2c-121">At the command prompt, type:</span></span>  
  
    ```  
    bm.exe update-config -FileName:BAMConfiguration.xml  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="8cd2c-122">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="8cd2c-122">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cd2c-123">参照</span><span class="sxs-lookup"><span data-stu-id="8cd2c-123">See Also</span></span>  
 [<span data-ttu-id="8cd2c-124">BizTalk Server データベースの移動</span><span class="sxs-lookup"><span data-stu-id="8cd2c-124">Moving BizTalk Server Databases</span></span>](../core/moving-biztalk-server-databases.md)