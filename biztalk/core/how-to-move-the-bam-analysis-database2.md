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
# <a name="how-to-move-the-bam-analysis-database"></a><span data-ttu-id="34cf0-102">BAM 分析データベースを移動する方法</span><span class="sxs-lookup"><span data-stu-id="34cf0-102">How to Move the BAM Analysis Database</span></span>
<span data-ttu-id="34cf0-103">この手順を使用すると、BAM 分析データベースを別のサーバーに移動します。</span><span class="sxs-lookup"><span data-stu-id="34cf0-103">You can use this procedure to move the BAM Analysis database to another server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="34cf0-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="34cf0-104">Prerequisites</span></span>  
 <span data-ttu-id="34cf0-105">この手順を実行するには、SQL Server sysadmin 固定サーバーの役割のメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="34cf0-105">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-move-the-bam-analysis-database"></a><span data-ttu-id="34cf0-106">BAM 分析データベースを移動するには</span><span class="sxs-lookup"><span data-stu-id="34cf0-106">To move the BAM Analysis database</span></span>  
  
1. <span data-ttu-id="34cf0-107">BAM を復元するときに使用する .xml ファイルのコピーを用意します。</span><span class="sxs-lookup"><span data-stu-id="34cf0-107">Get a copy of the .xml file used for restoring BAM:</span></span>  
  
   1. <span data-ttu-id="34cf0-108">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="34cf0-108">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
   2. <span data-ttu-id="34cf0-109">コマンド プロンプトで、次のディレクトリに移動します</span><span class="sxs-lookup"><span data-stu-id="34cf0-109">At the command prompt, navigate to the following directory:</span></span>  
  
       [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="34cf0-110">追跡</span><span class="sxs-lookup"><span data-stu-id="34cf0-110">Tracking</span></span>  
  
   3. <span data-ttu-id="34cf0-111">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="34cf0-111">At the command prompt, type:</span></span>  
  
      ```  
      Bm.exe get-config –filename:BAMConfiguration.xml  
      ```  
  
      > [!NOTE]
      >  <span data-ttu-id="34cf0-112">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="34cf0-112">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
2. <span data-ttu-id="34cf0-113">古いサーバー上のデータベースをバックアップする方法の SQL Server オンライン ブックの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="34cf0-113">Follow the instructions in SQL Server Books Online on how to back up the database on the old server.</span></span>  
  
3. <span data-ttu-id="34cf0-114">BAM 分析データベースを新しい SQL Server にコピーします。</span><span class="sxs-lookup"><span data-stu-id="34cf0-114">Copy the BAM Analysis database to the new SQL Server.</span></span>  
  
4. <span data-ttu-id="34cf0-115">SQL Server Books Online に記載されている手順に従い、新しいサーバーにデータベースを復元します。</span><span class="sxs-lookup"><span data-stu-id="34cf0-115">Follow the instructions in SQL Server Books Online on how to restore the database on the new server.</span></span>  
  
5. <span data-ttu-id="34cf0-116">BAMConfiguration.xml ファイルを編集し、AnalysisDatabase DeploymentUnit セクションの ServerName を新しいサーバー名に変更します。</span><span class="sxs-lookup"><span data-stu-id="34cf0-116">Edit the BAMConfiguration.xml file and change the ServerName in the AnalysisDatabase DeploymentUnit section to the new server name.</span></span>  
  
6. <span data-ttu-id="34cf0-117">BAMConfiguration.xml ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="34cf0-117">Save and close the BAMConfiguration.xml file.</span></span>  
  
7. <span data-ttu-id="34cf0-118">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="34cf0-118">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
8. <span data-ttu-id="34cf0-119">コマンド プロンプトで、次のディレクトリに移動します</span><span class="sxs-lookup"><span data-stu-id="34cf0-119">At the command prompt, navigate to the following directory:</span></span>  
  
    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="34cf0-120">追跡</span><span class="sxs-lookup"><span data-stu-id="34cf0-120">Tracking</span></span>  
  
9. <span data-ttu-id="34cf0-121">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="34cf0-121">At the command prompt, type:</span></span>  
  
    ```  
    bm.exe update-config -FileName:BAMConfiguration.xml  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="34cf0-122">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="34cf0-122">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34cf0-123">参照</span><span class="sxs-lookup"><span data-stu-id="34cf0-123">See Also</span></span>  
 [<span data-ttu-id="34cf0-124">BizTalk Server データベースの移動</span><span class="sxs-lookup"><span data-stu-id="34cf0-124">Moving BizTalk Server Databases</span></span>](../core/moving-biztalk-server-databases.md)