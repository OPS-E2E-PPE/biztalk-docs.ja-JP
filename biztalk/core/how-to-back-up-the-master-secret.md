---
title: マスター シークレットをバックアップする方法 |Microsoft ドキュメント
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
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 185f3ea674015e02cac2bdaa785c2ee06e67db65
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-back-up-the-master-secret"></a><span data-ttu-id="23f45-102">マスター シークレットをバックアップする方法</span><span class="sxs-lookup"><span data-stu-id="23f45-102">How to Back Up the Master Secret</span></span>
<span data-ttu-id="23f45-103">マスター シークレットは、マスター シークレット サーバーから NTFS ファイル システムまたはリムーバブル メディア (フロッピー ディスクなど) にバックアップできます。</span><span class="sxs-lookup"><span data-stu-id="23f45-103">You can back up the master secret from the master secret server onto an NTFS file system or removable media, such as a floppy disk.</span></span>  
  
 <span data-ttu-id="23f45-104">この作業を実行するには、シングル サインオン管理者および Windows 管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="23f45-104">You must be a Single Sign-On Administrator and a Windows administrator to perform this task.</span></span> <span data-ttu-id="23f45-105">SSO システムによってパスワードの入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="23f45-105">The SSO system will prompt you for a password.</span></span> <span data-ttu-id="23f45-106">バックアップしたマスター シークレットを復元する際は、同じパスワードを指定してください。</span><span class="sxs-lookup"><span data-stu-id="23f45-106">To restore the secret later, you must specify the same password.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="23f45-107">マスター シークレット サーバーに障害が発生してキーが失われたり、キーが破損したりすると、SSO データベースに格納されているデータを取得できなくなります。</span><span class="sxs-lookup"><span data-stu-id="23f45-107">If the master secret server fails and you lose the key, or if the key becomes corrupted, you will not be able to retrieve data stored in the SSO database.</span></span> <span data-ttu-id="23f45-108">マスター シークレットは必ずバックアップしてください。そうしないと、SSO データベースのデータが消失する危険性があります。</span><span class="sxs-lookup"><span data-stu-id="23f45-108">You must back up the master secret, or you risk losing data from the SSO database.</span></span>  
  
### <a name="to-back-up-the-master-secret-using-the-mmc-snap-in"></a><span data-ttu-id="23f45-109">MMC スナップインを使用してマスター シークレットをバックアップするには</span><span class="sxs-lookup"><span data-stu-id="23f45-109">To back up the master secret using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="23f45-110">**開始**  メニューのをクリックして **すべてのプログラム**, 、 をクリックして **Microsoft エンタープライズ シングル サインオン**, 、 をクリックし、 **SSO 管理**します。</span><span class="sxs-lookup"><span data-stu-id="23f45-110">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="23f45-111">ENTSSO MMC スナップインのスコープ ペインで、展開、 **エンタープライズ シングル サインオン** ノードです。</span><span class="sxs-lookup"><span data-stu-id="23f45-111">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="23f45-112">右クリック **システム**, 、クリックして **シークレットのバックアップ**します。</span><span class="sxs-lookup"><span data-stu-id="23f45-112">Right-click **System**, and then click **Backup Secret**.</span></span>  
  
### <a name="to-back-up-the-master-secret-using-the-command-line"></a><span data-ttu-id="23f45-113">コマンド ラインを使用してマスター シークレットをバックアップするには</span><span class="sxs-lookup"><span data-stu-id="23f45-113">To back up the master secret using the command line</span></span>  
  
1.  <span data-ttu-id="23f45-114">**開始**  メニューのをクリックして **すべてのプログラム**, 、 をクリックし、 **アクセサリ**します。</span><span class="sxs-lookup"><span data-stu-id="23f45-114">On the **Start** menu, click **All Programs**, and then click **Accessories**.</span></span> <span data-ttu-id="23f45-115">右クリック **コマンド プロンプト**, 、クリックして **実行付けて**します。</span><span class="sxs-lookup"><span data-stu-id="23f45-115">Right-click **Command Prompt**, and then click **Run As…**.</span></span>  
  
2.  <span data-ttu-id="23f45-116">適切な管理者を選択し、クリックして **OK**します。</span><span class="sxs-lookup"><span data-stu-id="23f45-116">Select the appropriate Administrator, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="23f45-117">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="23f45-117">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="23f45-118">既定のインストール ディレクトリは*\<ドライブ\>*: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="23f45-118">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="23f45-119">型 * * ssoconfig – backupSecret *\<バックアップ ファイル\>* * *、どこで*\<バックアップ ファイル\>*はマスター シークレットがバックアップ先ファイルの名前とパス。</span><span class="sxs-lookup"><span data-stu-id="23f45-119">Type **ssoconfig –backupSecret *\<backup file\>***, where *\<backup file\>* is the path and name of the file where the master secret will be backed up.</span></span> <span data-ttu-id="23f45-120">たとえば、A:\ssobackup.bak と指定します。</span><span class="sxs-lookup"><span data-stu-id="23f45-120">For example, A:\ssobackup.bak</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="23f45-121">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="23f45-121">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
5.  <span data-ttu-id="23f45-122">パスワードを指定してこのファイルを保護します。</span><span class="sxs-lookup"><span data-stu-id="23f45-122">Provide a password to protect this file.</span></span> <span data-ttu-id="23f45-123">パスワードの確認入力と、このパスワードを思い出すのに役立つパスワードのヒントの指定を求められます。</span><span class="sxs-lookup"><span data-stu-id="23f45-123">You will be prompted to confirm the password and to provide a password hint to help you remember this password.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="23f45-124">バックアップ ファイルは、セキュリティで保護された場所に保存および格納してください。</span><span class="sxs-lookup"><span data-stu-id="23f45-124">You must save and store the backup file in a secure location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23f45-125">参照</span><span class="sxs-lookup"><span data-stu-id="23f45-125">See Also</span></span>  
 <span data-ttu-id="23f45-126">[マスター シークレットを生成する方法](../core/how-to-generate-the-master-secret.md) </span><span class="sxs-lookup"><span data-stu-id="23f45-126">[How to Generate the Master Secret](../core/how-to-generate-the-master-secret.md) </span></span>  
 <span data-ttu-id="23f45-127">[マスター シークレットを復元する方法](../core/how-to-restore-the-master-secret.md) </span><span class="sxs-lookup"><span data-stu-id="23f45-127">[How to Restore the Master Secret](../core/how-to-restore-the-master-secret.md) </span></span>  
 <span data-ttu-id="23f45-128">[マスター シークレット サーバー](../core/master-secret-server.md) </span><span class="sxs-lookup"><span data-stu-id="23f45-128">[Master Secret Server](../core/master-secret-server.md) </span></span>  
 [<span data-ttu-id="23f45-129">マスター シークレットの管理</span><span class="sxs-lookup"><span data-stu-id="23f45-129">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)