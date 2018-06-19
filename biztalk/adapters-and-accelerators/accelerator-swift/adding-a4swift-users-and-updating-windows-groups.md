---
title: A4SWIFT のユーザーを追加して、Windows グループの更新 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- user accounts, Windows groups
- Windows groups, user accounts
- user accounts, creating
- Windows groups, updating
- updating Windows groups
- A4SWIFT, creating user accounts
ms.assetid: ddc54457-6499-402c-9cc2-f7b17bbc255f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce3fbf2f3b78b13205b43989c2b0c03909dec392
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209930"
---
# <a name="adding-a4swift-users-and-updating-windows-groups"></a><span data-ttu-id="d06a3-102">A4SWIFT のユーザーを追加して、Windows グループの更新</span><span class="sxs-lookup"><span data-stu-id="d06a3-102">Adding A4SWIFT Users and Updating Windows Groups</span></span>
<span data-ttu-id="d06a3-103">作成し、Message Repair and New Submission の役割用の証明書をインストールして、後に作成する必要が[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザーを追加および[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]グループへのユーザーです。</span><span class="sxs-lookup"><span data-stu-id="d06a3-103">After you create and install certificates for Message Repair and New Submission roles, you must create [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] users and add [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] users to groups.</span></span>  
  
 <span data-ttu-id="d06a3-104">**概要**</span><span class="sxs-lookup"><span data-stu-id="d06a3-104">**Summary**</span></span>  
  
 <span data-ttu-id="d06a3-105">Message Repair and New Submission のユーザーを作成し、ローカルまたはドメイン アカウントを追加して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]ユーザー グループを次のようにします。</span><span class="sxs-lookup"><span data-stu-id="d06a3-105">Create Message Repair and New Submission users and add local or domain accounts to [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] user groups, as follows:</span></span>  
  
-   <span data-ttu-id="d06a3-106">[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]管理コンソールで、Message Repair and New Submission のプロセスのワークフローの段階での役割があるユーザーの数を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d06a3-106">In the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Management Console, you need to create as many users as there are roles in the workflow stages of your Message Repair and New Submission process.</span></span> <span data-ttu-id="d06a3-107">これらのユーザーのそれぞれに個別の証明書を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="d06a3-107">Associate a distinct certificate with each of these users.</span></span>  
  
-   <span data-ttu-id="d06a3-108">使用して、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]コンピューターの管理ユーティリティを確認することを作成するには、修復、各ローカル ユーザーを追加または A4SWIFT のユーザーにメッセージを承認します。</span><span class="sxs-lookup"><span data-stu-id="d06a3-108">Using the [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Computer Management utility, add each local user who is creating, repairing, verifying, or approving a message to the A4SWIFT Users.</span></span>  
  
-   <span data-ttu-id="d06a3-109">使用して、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]コンピューター管理ユーティリティ、BizTalk Service BizTalk Group サービスのログ名 フィールドに記載されているローカル ユーザーを追加、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザー グループ。</span><span class="sxs-lookup"><span data-stu-id="d06a3-109">Using the [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Computer Management utility, add the local user that is listed in the Log On As field for the BizTalk Service BizTalk Group service to the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Users group.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d06a3-110">詳細については[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザーとロールを参照してください[Message Repair and New Submission のロールの作成の部門と](../../adapters-and-accelerators/accelerator-swift/creating-departments-and-roles-for-message-repair-and-new-submission.md)です。</span><span class="sxs-lookup"><span data-stu-id="d06a3-110">For more information about [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] users and roles, see [Creating Departments and Roles for Message Repair and New Submission](../../adapters-and-accelerators/accelerator-swift/creating-departments-and-roles-for-message-repair-and-new-submission.md).</span></span>  
  
### <a name="to-add-user-accounts-to-the-a4swift-users-group"></a><span data-ttu-id="d06a3-111">A4SWIFT の Users グループにユーザー アカウントを追加するには</span><span class="sxs-lookup"><span data-stu-id="d06a3-111">To add User Accounts to the A4SWIFT Users Group</span></span>  
  
1.  <span data-ttu-id="d06a3-112">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリック**コンピューターの管理**です。</span><span class="sxs-lookup"><span data-stu-id="d06a3-112">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Computer Management**.</span></span>  
  
2.  <span data-ttu-id="d06a3-113">**コンピューターの管理**ダイアログ ボックスで、左側のウィンドウで展開**ローカル ユーザーとグループ**、クリックして**グループ**です。</span><span class="sxs-lookup"><span data-stu-id="d06a3-113">In the **Computer Management** dialog box, in the left pane, expand **Local Users and Groups**, and then click **Groups**.</span></span>  
  
3.  <span data-ttu-id="d06a3-114">**コンピューターの管理**ダイアログ ボックスで、右側のウィンドウでダブルクリック**A4SWIFT ユーザー**です。</span><span class="sxs-lookup"><span data-stu-id="d06a3-114">In the **Computer Management** dialog box, in the right pane, double-click **A4SWIFT Users**.</span></span>  
  
4.  <span data-ttu-id="d06a3-115">**A4SWIFT ユーザー プロパティ**ダイアログ ボックスで、をクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="d06a3-115">In the **A4SWIFT Users Properties** dialog box, click **Add**.</span></span>  
  
5.  <span data-ttu-id="d06a3-116">**ユーザー、コンピューター、またはグループ** ダイアログ ボックスで、**を選択するオブジェクト名の入力** ウィンドウで、作成、修復、検証、または、メッセージを承認したローカル ユーザーの名前を入力し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="d06a3-116">In the **Select Users, Computers, or Groups** dialog box, in the **Enter the object names to select** pane, type the name of a local user who is creating, repairing, verifying, or approving a message, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="d06a3-117">各ローカル ユーザーの作成、修復、検証、またはメッセージを承認するには、手順 5. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d06a3-117">Repeat step 5 for each local user who is creating, repairing, verifying, or approving a message.</span></span>  
  
7.  <span data-ttu-id="d06a3-118">A4SWIFT Users のプロパティ] ダイアログ ボックス [ **OK**です。</span><span class="sxs-lookup"><span data-stu-id="d06a3-118">In the A4SWIFT Users Properties dialog box, click **OK**.</span></span>  
  
8.  <span data-ttu-id="d06a3-119">コンピューターの管理 ダイアログ ボックスの左側のウィンドウで、サービスとアプリケーションを展開し、サービス をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d06a3-119">In the Computer Management dialog box, in the left pane, expand Services and Applications, and then click Services.</span></span> <span data-ttu-id="d06a3-120">右側のウィンドウでをクリックして**BizTalk Service BizTalk Group**です。</span><span class="sxs-lookup"><span data-stu-id="d06a3-120">In the right pane, click **BizTalk Service BizTalk Group**.</span></span> <span data-ttu-id="d06a3-121">[ログオン方法] 列に示されたユーザーに注意してください**BizTalk Service BizTalk Group**です。</span><span class="sxs-lookup"><span data-stu-id="d06a3-121">Note the user listed in the Log On As column for **BizTalk Service BizTalk Group**.</span></span>  
  
9. <span data-ttu-id="d06a3-122">左側のウィンドウで、**コンピューターの管理** ダイアログ ボックスで、展開**ローカル ユーザーとグループ**、クリックして**グループ**です。</span><span class="sxs-lookup"><span data-stu-id="d06a3-122">In the left pane of the **Computer Management** dialog box, expand **Local Users and Groups**, and then click **Groups**.</span></span> <span data-ttu-id="d06a3-123">ダブルクリックして**A4SWIFT ユーザー**です。</span><span class="sxs-lookup"><span data-stu-id="d06a3-123">Double-click **A4SWIFT Users**.</span></span> <span data-ttu-id="d06a3-124">[ログオン方法] 列で、ユーザーが表示されていることを確認してください。 **BizTalk Service BizTalk Group**の一部である、 **A4SWIFT ユーザー**グループ。</span><span class="sxs-lookup"><span data-stu-id="d06a3-124">Ensure that the user listed in the Log On As column for **BizTalk Service BizTalk Group** is part of the **A4SWIFT Users** group.</span></span> <span data-ttu-id="d06a3-125">そのユーザーがいない場合は、追加、 **A4SWIFT ユーザー**グループ。</span><span class="sxs-lookup"><span data-stu-id="d06a3-125">If not, add that user to the **A4SWIFT Users** group.</span></span>  
  
10. <span data-ttu-id="d06a3-126">サーバーからログオフし、再度ログオンします。</span><span class="sxs-lookup"><span data-stu-id="d06a3-126">Log off the server, and then log back on.</span></span>