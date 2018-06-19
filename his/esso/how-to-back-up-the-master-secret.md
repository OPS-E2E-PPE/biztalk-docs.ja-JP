---
title: マスター シークレットをバックアップする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0841c52a-7b15-45f8-9900-f5c9e3abd90b
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 124c077d7a15a4938f94239518ad02c8268074a4
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "30250998"
---
# <a name="how-to-back-up-the-master-secret"></a><span data-ttu-id="bb5a1-102">マスター シークレットをバックアップする方法</span><span class="sxs-lookup"><span data-stu-id="bb5a1-102">How to Back Up the Master Secret</span></span>
<span data-ttu-id="bb5a1-103">マスター シークレットは、マスター シークレット サーバーから NTFS ファイル システムまたはリムーバブル メディア (フロッピー ディスクなど) にバックアップできます。</span><span class="sxs-lookup"><span data-stu-id="bb5a1-103">You can back up the master secret from the master secret server onto an NTFS file system or removable media, such as a floppy disk.</span></span>  
  
 <span data-ttu-id="bb5a1-104">このタスクを実行するには、シングル サインオン管理者および Windows 管理者でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="bb5a1-104">You must be a Single Sign-On administrator and a Windows administrator to perform this task.</span></span> <span data-ttu-id="bb5a1-105">シングル サインオン (SSO) システムでは、パスワードを求められます。</span><span class="sxs-lookup"><span data-stu-id="bb5a1-105">The Single Sign-On (SSO) system will prompt you for a password.</span></span> <span data-ttu-id="bb5a1-106">バックアップしたマスター シークレットを復元する際は、同じパスワードを指定してください。</span><span class="sxs-lookup"><span data-stu-id="bb5a1-106">To restore the secret later, you must specify the same password.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="bb5a1-107">マスター シークレット サーバーがクラッシュした場合と、キーを紛失したまたは資格情報データベースに格納されたデータを取得できませんでキーが破損した場合。</span><span class="sxs-lookup"><span data-stu-id="bb5a1-107">If the master secret server crashes and you lose the key, or if the key becomes corrupted, you will not be able to retrieve data stored in the Credential database.</span></span> <span data-ttu-id="bb5a1-108">マスター シークレットは、または資格情報データベースからデータが失われるリスクをバックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb5a1-108">You must back up the master secret, or you risk losing data from the Credential database.</span></span>  
  
### <a name="to-back-up-the-master-secret-using-the-mmc-snap-in"></a><span data-ttu-id="bb5a1-109">MMC スナップインを使用してマスター シークレットをバックアップするには</span><span class="sxs-lookup"><span data-stu-id="bb5a1-109">To back up the master secret using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="bb5a1-110">をクリックして**開始**、 をポイント**プログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、順にクリック**SSO 管理**です。</span><span class="sxs-lookup"><span data-stu-id="bb5a1-110">Click **Start**, point to **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="bb5a1-111">ENTSSO Microsoft 管理コンソール (MMC) スナップインの [スコープ] ウィンドウで、展開、**エンタープライズ シングル サインオン**ノード。</span><span class="sxs-lookup"><span data-stu-id="bb5a1-111">In the scope pane of the ENTSSO Microsoft Management Console (MMC) Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="bb5a1-112">右クリック**システム**、クリックして**マスター シークレットをバックアップ**です。</span><span class="sxs-lookup"><span data-stu-id="bb5a1-112">Right-click **System**, and then click **Back up Master Secret**.</span></span>  
  
### <a name="to-back-up-the-master-secret-using-the-command-line"></a><span data-ttu-id="bb5a1-113">コマンド ラインを使用してマスター シークレットをバックアップするには</span><span class="sxs-lookup"><span data-stu-id="bb5a1-113">To back up the master secret using the command line</span></span>  
  
1.  <span data-ttu-id="bb5a1-114">**開始** メニューのをクリックして**プログラム**、クリックして**アクセサリ**です。</span><span class="sxs-lookup"><span data-stu-id="bb5a1-114">On the **Start** menu, click **Programs**, and then click **Accessories**.</span></span> <span data-ttu-id="bb5a1-115">右クリック **コマンド プロンプト**, 、クリックして **実行付けて**します。</span><span class="sxs-lookup"><span data-stu-id="bb5a1-115">Right-click **Command Prompt**, and then click **Run As…**.</span></span>  
  
2.  <span data-ttu-id="bb5a1-116">適切な管理者を選択し、クリックして **OK**します。</span><span class="sxs-lookup"><span data-stu-id="bb5a1-116">Select the appropriate Administrator, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="bb5a1-117">コマンド プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="bb5a1-117">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="bb5a1-118">既定のインストール ディレクトリは*\<ドライブ >*: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="bb5a1-118">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="bb5a1-119">型`ssoconfig –backupsecret <backup file>`ここで、 *\<バックアップ ファイル >* マスター シークレットがバックアップ先、たとえば、ファイルの名前とパスは、`A:\ssobackup.bak`です。</span><span class="sxs-lookup"><span data-stu-id="bb5a1-119">Type `ssoconfig –backupsecret <backup file>`, where *\<backup file>* is the path and name of the file where the master secret will be backed up, for example, `A:\ssobackup.bak`.</span></span>  
  
5.  <span data-ttu-id="bb5a1-120">このファイルを保護するためにパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="bb5a1-120">Provide a password to help protect this file.</span></span>  
  
     <span data-ttu-id="bb5a1-121">パスワードの確認入力と、このパスワードを思い出すのに役立つパスワードのヒントの指定を求められます。</span><span class="sxs-lookup"><span data-stu-id="bb5a1-121">You will be prompted to confirm the password and to provide a password hint to help you remember this password.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bb5a1-122">バックアップ ファイルは、セキュリティで保護された場所に保存および格納してください。</span><span class="sxs-lookup"><span data-stu-id="bb5a1-122">You must save and store the backup file in a secure location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb5a1-123">参照</span><span class="sxs-lookup"><span data-stu-id="bb5a1-123">See Also</span></span>  
 <span data-ttu-id="bb5a1-124">[マスター シークレットを生成する方法](../esso/how-to-generate-the-master-secret.md) </span><span class="sxs-lookup"><span data-stu-id="bb5a1-124">[How to Generate the Master Secret](../esso/how-to-generate-the-master-secret.md) </span></span>  
 <span data-ttu-id="bb5a1-125">[マスター シークレットを復元する方法](../esso/how-to-restore-the-master-secret.md) </span><span class="sxs-lookup"><span data-stu-id="bb5a1-125">[How to Restore the Master Secret](../esso/how-to-restore-the-master-secret.md) </span></span>  
 <span data-ttu-id="bb5a1-126">[マスター シークレット サーバー](../esso/master-secret-server.md) </span><span class="sxs-lookup"><span data-stu-id="bb5a1-126">[Master Secret Server](../esso/master-secret-server.md) </span></span>  
 [<span data-ttu-id="bb5a1-127">マスター シークレットの管理</span><span class="sxs-lookup"><span data-stu-id="bb5a1-127">Managing the Master Secret</span></span>](../esso/managing-the-master-secret.md)