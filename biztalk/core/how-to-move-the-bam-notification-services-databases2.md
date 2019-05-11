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
# <a name="how-to-move-the-bam-notification-services-databases"></a><span data-ttu-id="d3555-102">BAM Notification Services データベースを移動する方法</span><span class="sxs-lookup"><span data-stu-id="d3555-102">How to Move the BAM Notification Services Databases</span></span>
<span data-ttu-id="d3555-103">ここでは、BAM Notification Services データベースを他のサーバーに移動する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="d3555-103">You can use this procedure to move the BAM Notification Services databases to another server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d3555-104">BAM Notification Services Application (BAMAlertsApplication) データベースおよび BAM Notification Services Instance (BAMAlertsNSMain) データベースは、一緒に移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3555-104">You must move the BAM Notification Services Application (BAMAlertsApplication) database and BAM Notification Services Instance (BAMAlertsNSMain) database together.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d3555-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="d3555-105">Prerequisites</span></span>  
 <span data-ttu-id="d3555-106">この手順を実行するには、SQL Server sysadmin 固定サーバーの役割のメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3555-106">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-move-the-bam-notification-services-databases"></a><span data-ttu-id="d3555-107">BAM Notification Services データベースを移動するには</span><span class="sxs-lookup"><span data-stu-id="d3555-107">To move the BAM Notification Services databases</span></span>  
  
1. <span data-ttu-id="d3555-108">BAM を復元するときに使用する .xml ファイルのコピーを用意します。</span><span class="sxs-lookup"><span data-stu-id="d3555-108">Get a copy of the .xml file used for restoring BAM:</span></span>  
  
   1. <span data-ttu-id="d3555-109">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="d3555-109">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
   2. <span data-ttu-id="d3555-110">コマンド プロンプトで、次のディレクトリに移動します</span><span class="sxs-lookup"><span data-stu-id="d3555-110">At the command prompt, navigate to the following directory:</span></span>  
  
       <span data-ttu-id="d3555-111">**%SystemDrive%\Program Files\Microsoft**  [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **\Tracking**</span><span class="sxs-lookup"><span data-stu-id="d3555-111">**%SystemDrive%\Program Files\Microsoft**  [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **\Tracking**</span></span>  
  
   3. <span data-ttu-id="d3555-112">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d3555-112">At the command prompt, type:</span></span>  
  
      ```  
      Bm.exe get-config –filename:BAMConfiguration.xml  
      ```  
  
      > [!NOTE]
      >  <span data-ttu-id="d3555-113">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="d3555-113">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
2. <span data-ttu-id="d3555-114">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d3555-114">At the command prompt, type:</span></span>  
  
   ```  
   Net stop NS$BamAlerts  
   ```  
  
3. <span data-ttu-id="d3555-115">古いサーバー上のデータベースをバックアップする方法の SQL Server オンライン ブックの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="d3555-115">Follow the instructions in SQL Server Books Online on how to back up the database on the old server.</span></span>  
  
4. <span data-ttu-id="d3555-116">BAM Notification Services データベースを新しい SQL Server にコピーします。</span><span class="sxs-lookup"><span data-stu-id="d3555-116">Copy the BAM Notification Services databases to the new SQL server.</span></span>  
  
5. <span data-ttu-id="d3555-117">SQL Server Books Online に記載されている手順に従い、新しいサーバーにデータベースを復元します。</span><span class="sxs-lookup"><span data-stu-id="d3555-117">Follow the instructions in SQL Server Books Online on how to restore the database on the new server.</span></span>  
  
6. <span data-ttu-id="d3555-118">BAMConfiguration.xml ファイルで、Alert DeploymentUnit セクションの ServerName を新しいサーバー名に変更します。</span><span class="sxs-lookup"><span data-stu-id="d3555-118">Edit the BAMConfiguration.xml file and change the ServerName in the Alert DeploymentUnit section to the new server name.</span></span>  
  
7. <span data-ttu-id="d3555-119">BAMConfiguration.xml ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="d3555-119">Save and close the BAMConfiguration.xml file.</span></span>  
  
8. <span data-ttu-id="d3555-120">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="d3555-120">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="d3555-121">コマンド プロンプトで、次のディレクトリに移動します</span><span class="sxs-lookup"><span data-stu-id="d3555-121">At the command prompt, navigate to the following directory:</span></span>  
  
     <span data-ttu-id="d3555-122">**%SystemDrive%\Program Files\Microsoft**  [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **\Tracking**</span><span class="sxs-lookup"><span data-stu-id="d3555-122">**%SystemDrive%\Program Files\Microsoft**  [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **\Tracking**</span></span>  
  
10. <span data-ttu-id="d3555-123">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d3555-123">At the command prompt, type:</span></span>  
  
    ```  
    bm.exe update-config -FileName:BAMConfiguration.xml  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="d3555-124">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="d3555-124">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
11. <span data-ttu-id="d3555-125">BAM Notification Services データベース名の参照を更新します。</span><span class="sxs-lookup"><span data-stu-id="d3555-125">Update references to the BAM Notification Services databases.</span></span> <span data-ttu-id="d3555-126">詳細については、次を参照してください。 [BAM Notification Services データベースへの参照を更新する方法](../core/how-to-update-references-to-the-bam-notification-services-databases.md)します。</span><span class="sxs-lookup"><span data-stu-id="d3555-126">For more information, see [How to Update References to the BAM Notification Services Databases](../core/how-to-update-references-to-the-bam-notification-services-databases.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3555-127">参照</span><span class="sxs-lookup"><span data-stu-id="d3555-127">See Also</span></span>  
 [<span data-ttu-id="d3555-128">BizTalk Server データベースの移動</span><span class="sxs-lookup"><span data-stu-id="d3555-128">Moving BizTalk Server Databases</span></span>](../core/moving-biztalk-server-databases.md)