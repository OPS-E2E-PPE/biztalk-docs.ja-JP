---
title: BAM アーカイブの Database2 を移動する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Archive database [BAM], migrating
- migrating, Archive database [BAM]
ms.assetid: 88b96dc2-8c9c-43f5-afb9-a937e05de36b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e33b09bd4e6563800c70acfae12ff52acc2cb071
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967171"
---
# <a name="how-to-move-the-bam-archive-database"></a><span data-ttu-id="56120-102">BAM アーカイブ データベースを移動する方法</span><span class="sxs-lookup"><span data-stu-id="56120-102">How to Move the BAM Archive Database</span></span>
<span data-ttu-id="56120-103">ここでは、BAM アーカイブ データベースを他のサーバーに移動する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="56120-103">You can use this procedure to move the BAM Archive database to another server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="56120-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="56120-104">Prerequisites</span></span>  
 <span data-ttu-id="56120-105">この手順を実行するには、SQL Server sysadmin 固定サーバーの役割のメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="56120-105">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-move-the-bam-archive-database"></a><span data-ttu-id="56120-106">BAM アーカイブ データベースを移動するには</span><span class="sxs-lookup"><span data-stu-id="56120-106">To move the BAM Archive database</span></span>  
  
1. <span data-ttu-id="56120-107">BAM を復元するときに使用する .xml ファイルのコピーを用意します。</span><span class="sxs-lookup"><span data-stu-id="56120-107">Get a copy of the .xml file used for restoring BAM:</span></span>  
  
   1. <span data-ttu-id="56120-108">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="56120-108">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
   2. <span data-ttu-id="56120-109">コマンド プロンプトで、次のディレクトリに移動します</span><span class="sxs-lookup"><span data-stu-id="56120-109">At the command prompt, navigate to the following directory:</span></span>  
  
       [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="56120-110">追跡</span><span class="sxs-lookup"><span data-stu-id="56120-110">Tracking</span></span>  
  
   3. <span data-ttu-id="56120-111">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="56120-111">At the command prompt, type:</span></span>  
  
      ```  
      Bm.exe get-config –filename:BAMConfiguration.xml  
      ```  
  
      > [!NOTE]
      >  <span data-ttu-id="56120-112">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="56120-112">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
2. <span data-ttu-id="56120-113">SQL Server Books Online に記載されている手順に従い、古いサーバーのデータベースをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="56120-113">Follow the instructions in SQL Server Books Online to back up the database on the old server.</span></span>  
  
3. <span data-ttu-id="56120-114">BAM アーカイブ データベースを新しい SQL Server にコピーします。</span><span class="sxs-lookup"><span data-stu-id="56120-114">Copy the BAM Archive database to the new SQL server.</span></span>  
  
4. <span data-ttu-id="56120-115">新しいサーバー上のデータベースを復元する SQL Server オンライン ブックの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="56120-115">Follow the instructions in SQL Server Books Online to restore the database on the new server.</span></span>  
  
5. <span data-ttu-id="56120-116">BAMConfiguration.xml ファイルで、ArchivingDatabase DeploymentUnit セクションの ServerName を新しいサーバー名に変更します。</span><span class="sxs-lookup"><span data-stu-id="56120-116">Edit the BAMConfiguration.xml file and change the ServerName in the ArchivingDatabase DeploymentUnit section to the new server name.</span></span>  
  
6. <span data-ttu-id="56120-117">BAMConfiguration.xml ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="56120-117">Save and close the BAMConfiguration.xml file.</span></span>  
  
7. <span data-ttu-id="56120-118">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="56120-118">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
8. <span data-ttu-id="56120-119">コマンド プロンプトで、次のディレクトリに移動します</span><span class="sxs-lookup"><span data-stu-id="56120-119">At the command prompt, navigate to the following directory:</span></span>  
  
    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="56120-120">追跡</span><span class="sxs-lookup"><span data-stu-id="56120-120">Tracking</span></span>  
  
9. <span data-ttu-id="56120-121">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="56120-121">At the command prompt, type:</span></span>  
  
    ```  
    bm.exe update-config -FileName:BAMConfiguration.xml  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="56120-122">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="56120-122">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56120-123">参照</span><span class="sxs-lookup"><span data-stu-id="56120-123">See Also</span></span>  
 [<span data-ttu-id="56120-124">BizTalk Server データベースの移動</span><span class="sxs-lookup"><span data-stu-id="56120-124">Moving BizTalk Server Databases</span></span>](../core/moving-biztalk-server-databases.md)