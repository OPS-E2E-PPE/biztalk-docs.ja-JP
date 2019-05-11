---
title: マスター シークレットをバックアップする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [Master Secret server], backing up
- backing up, Master Secret server
- Master Secret server, backing up
ms.assetid: 22c23f66-b7df-4379-8a9f-065406ba8aa8
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1e38ebeb861d26bfdb31819ea1d94d830bf58fe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387092"
---
# <a name="how-to-back-up-the-master-secret"></a><span data-ttu-id="f4eb3-102">マスター シークレットをバックアップする方法</span><span class="sxs-lookup"><span data-stu-id="f4eb3-102">How to Back Up the Master Secret</span></span>
<span data-ttu-id="f4eb3-103">ことができます、NTFS にマスター シークレット サーバーからマスター シークレットをバックアップするファイル システムまたはフロッピー ディスクなどのリムーバブル メディア。</span><span class="sxs-lookup"><span data-stu-id="f4eb3-103">You can back up the master secret from the master secret server onto an NTFS file system or removable media, such as a floppy disk.</span></span>  
  
 <span data-ttu-id="f4eb3-104">シングル サインオン管理者および Windows 管理者は、このタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4eb3-104">You must be a Single Sign-On Administrator and a Windows administrator to perform this task.</span></span> <span data-ttu-id="f4eb3-105">SSO システムでは、パスワードを求められます。</span><span class="sxs-lookup"><span data-stu-id="f4eb3-105">The SSO system will prompt you for a password.</span></span> <span data-ttu-id="f4eb3-106">後で、シークレットを復元するには、同じパスワードを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4eb3-106">To restore the secret later, you must specify the same password.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="f4eb3-107">マスター シークレット サーバーが失敗し、キーを紛失した場合、または、キーが破損している場合は、SSO データベースに格納されているデータを取得することができなきます。</span><span class="sxs-lookup"><span data-stu-id="f4eb3-107">If the master secret server fails and you lose the key, or if the key becomes corrupted, you will not be able to retrieve data stored in the SSO database.</span></span> <span data-ttu-id="f4eb3-108">マスター シークレットは、または SSO データベースからデータが失われるリスクをバックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4eb3-108">You must back up the master secret, or you risk losing data from the SSO database.</span></span>  
  
### <a name="to-back-up-the-master-secret-using-the-mmc-snap-in"></a><span data-ttu-id="f4eb3-109">MMC スナップインを使用してマスター シークレットをバックアップするには</span><span class="sxs-lookup"><span data-stu-id="f4eb3-109">To back up the master secret using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="f4eb3-110">**開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、 をクリックし、 **SSO 管理**。</span><span class="sxs-lookup"><span data-stu-id="f4eb3-110">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="f4eb3-111">ENTSSO MMC スナップインの [スコープ] ウィンドウで、**エンタープライズ シングル サインオン**ノード。</span><span class="sxs-lookup"><span data-stu-id="f4eb3-111">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="f4eb3-112">右クリックして**システム**、 をクリックし、**シークレットのバックアップ**します。</span><span class="sxs-lookup"><span data-stu-id="f4eb3-112">Right-click **System**, and then click **Backup Secret**.</span></span>  
  
### <a name="to-back-up-the-master-secret-using-the-command-line"></a><span data-ttu-id="f4eb3-113">コマンドラインを使用してマスター シークレットをバックアップするには</span><span class="sxs-lookup"><span data-stu-id="f4eb3-113">To back up the master secret using the command line</span></span>  
  
1. <span data-ttu-id="f4eb3-114">**開始** メニューのをクリックして**すべてのプログラム**、順にクリックします**アクセサリ**します。</span><span class="sxs-lookup"><span data-stu-id="f4eb3-114">On the **Start** menu, click **All Programs**, and then click **Accessories**.</span></span> <span data-ttu-id="f4eb3-115">右クリックして**コマンド プロンプト**、 をクリックし、**として実行しています**。</span><span class="sxs-lookup"><span data-stu-id="f4eb3-115">Right-click **Command Prompt**, and then click **Run As…**.</span></span>  
  
2. <span data-ttu-id="f4eb3-116">適切な管理者を選択し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="f4eb3-116">Select the appropriate Administrator, and then click **OK**.</span></span>  
  
3. <span data-ttu-id="f4eb3-117">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="f4eb3-117">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="f4eb3-118">既定のインストール ディレクトリは*\<ドライブ\>*: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="f4eb3-118">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4. <span data-ttu-id="f4eb3-119">型 \* \* ssoconfig – backupSecret *\<バックアップ ファイル\>\*\*<em>ここで、*\<バックアップ ファイル\></em>をマスター シークレットをバックアップ、ファイルの名前とパスです。</span><span class="sxs-lookup"><span data-stu-id="f4eb3-119">Type \*\*ssoconfig –backupSecret \*\<backup file\>\*\*<em>, where \*\<backup file\></em> is the path and name of the file where the master secret will be backed up.</span></span> <span data-ttu-id="f4eb3-120">たとえば、A:\ssobackup.bak</span><span class="sxs-lookup"><span data-stu-id="f4eb3-120">For example, A:\ssobackup.bak</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="f4eb3-121">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="f4eb3-121">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
5. <span data-ttu-id="f4eb3-122">このファイルを保護するパスワードを提供します。</span><span class="sxs-lookup"><span data-stu-id="f4eb3-122">Provide a password to protect this file.</span></span> <span data-ttu-id="f4eb3-123">このパスワードを思い出すのに役立つパスワードのヒントを提供して、パスワードの確認を求められます。</span><span class="sxs-lookup"><span data-stu-id="f4eb3-123">You will be prompted to confirm the password and to provide a password hint to help you remember this password.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f4eb3-124">保存し、安全な場所にバックアップ ファイルを保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4eb3-124">You must save and store the backup file in a secure location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4eb3-125">参照</span><span class="sxs-lookup"><span data-stu-id="f4eb3-125">See Also</span></span>  
 <span data-ttu-id="f4eb3-126">[マスター シークレットを生成する方法](../core/how-to-generate-the-master-secret.md) </span><span class="sxs-lookup"><span data-stu-id="f4eb3-126">[How to Generate the Master Secret](../core/how-to-generate-the-master-secret.md) </span></span>  
 <span data-ttu-id="f4eb3-127">[マスター シークレットを復元する方法](../core/how-to-restore-the-master-secret.md) </span><span class="sxs-lookup"><span data-stu-id="f4eb3-127">[How to Restore the Master Secret](../core/how-to-restore-the-master-secret.md) </span></span>  
 <span data-ttu-id="f4eb3-128">[マスター シークレット サーバー](../core/master-secret-server.md) </span><span class="sxs-lookup"><span data-stu-id="f4eb3-128">[Master Secret Server](../core/master-secret-server.md) </span></span>  
 [<span data-ttu-id="f4eb3-129">マスター シークレットの管理</span><span class="sxs-lookup"><span data-stu-id="f4eb3-129">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)