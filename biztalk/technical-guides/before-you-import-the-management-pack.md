---
title: 管理パックをインポートする前に |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e3c13dd-613a-4885-a5d2-ad3ee492ff25
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c11849c379a4654bed78a8e86ba263e6da428c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299450"
---
# <a name="before-you-import-the-management-pack"></a><span data-ttu-id="845fa-102">管理パックをインポートする前に</span><span class="sxs-lookup"><span data-stu-id="845fa-102">Before You Import the Management Pack</span></span>
<span data-ttu-id="845fa-103">ベスト プラクティスとしてを使用しているオペレーティング システム用の Windows Server 管理パックをインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="845fa-103">As a best practice, you should import the Windows Server Management Pack for the operating system that you are using.</span></span> <span data-ttu-id="845fa-104">インポートする前に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理パックは、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="845fa-104">Before you import the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Management Pack, take the following actions:</span></span>  
  
-   <span data-ttu-id="845fa-105">Operations Manager 2007 R2 または 2012 がインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="845fa-105">Ensure that Operations Manager 2007 R2/2012 is installed.</span></span>  
  
-   <span data-ttu-id="845fa-106">SCOM 管理者グループまたは SCOM Authors グループのいずれかのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="845fa-106">You must be a member of either the SCOM Administrators group or the SCOM Authors group.</span></span> <span data-ttu-id="845fa-107">SCOM 管理サーバー上のローカル管理者は、すべての権限と、SCOM 管理者グループに与えられているアクセス許可があります。</span><span class="sxs-lookup"><span data-stu-id="845fa-107">Local administrators on the SCOM Management Server have all the rights and permissions that are granted to the SCOM Administrators group.</span></span>  
  
-   <span data-ttu-id="845fa-108">管理する各 BizTalk サーバーに SCOM エージェントを展開することで、BizTalk サーバーを Operations Manager で管理されたコンピューターとして設定します。</span><span class="sxs-lookup"><span data-stu-id="845fa-108">Set up your BizTalk Servers as managed computers in Operations Manager by deploying the SCOM agents on each BizTalk Server that you want to manage.</span></span> <span data-ttu-id="845fa-109">SCOM エージェントの展開には、次のタスクが含まれます。</span><span class="sxs-lookup"><span data-stu-id="845fa-109">The SCOM agent deployment involves the following tasks:</span></span>  
  
    -   <span data-ttu-id="845fa-110">SCOM エージェントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="845fa-110">Install the SCOM agent.</span></span>  
  
    -   <span data-ttu-id="845fa-111">BizTalk SCOM エージェント アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="845fa-111">Create a BizTalk SCOM agent account.</span></span>  
  
    -   <span data-ttu-id="845fa-112">構成、**として実行**アカウント。</span><span class="sxs-lookup"><span data-stu-id="845fa-112">Configure a **Run As** account.</span></span> <span data-ttu-id="845fa-113">次のグループに、実行アカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="845fa-113">Add the Run As account to the following groups:</span></span>  
  
        -   <span data-ttu-id="845fa-114">BizTalk グループ。</span><span class="sxs-lookup"><span data-stu-id="845fa-114">BizTalk Groups.</span></span>  
  
        -   <span data-ttu-id="845fa-115">BizTalk 管理者。</span><span class="sxs-lookup"><span data-stu-id="845fa-115">BizTalk Administrators.</span></span>  
  
        -   <span data-ttu-id="845fa-116">SSO 管理者。</span><span class="sxs-lookup"><span data-stu-id="845fa-116">SSO Administrators.</span></span>  
  
        -   <span data-ttu-id="845fa-117">SSO 関連管理者。</span><span class="sxs-lookup"><span data-stu-id="845fa-117">SSO Affiliate Administrators.</span></span>  
  
    -   <span data-ttu-id="845fa-118">監視を開始します。</span><span class="sxs-lookup"><span data-stu-id="845fa-118">Initiate monitoring.</span></span>  
  
-   <span data-ttu-id="845fa-119">Operation Manager コンソールで管理されたコンピューターは正常な状態です。</span><span class="sxs-lookup"><span data-stu-id="845fa-119">In Operation Manager Console, managed computers are in a healthy state.</span></span>  
  
-   <span data-ttu-id="845fa-120">必要なユーザーとして実行アカウントやプロファイルなど、設定する必要があるすべてのユーザー アカウントを構成します。</span><span class="sxs-lookup"><span data-stu-id="845fa-120">Configure any user accounts that have to be set up, such as any required Run As accounts or profiles.</span></span> <span data-ttu-id="845fa-121">この管理パックには、エージェントごとに特定の資格情報を定義するには、「BizTalk Server 監視アカウント」および「BizTalk Server 検出アカウント」という名前のユーザーとして実行プロファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="845fa-121">This management pack includes Run As profiles named “BizTalk Server Monitoring Account” and “BizTalk Server Discovery Account” to define specific credentials on a per-agent basis.</span></span> <span data-ttu-id="845fa-122">管理パックをインポートした後に、一部のエージェントに対してこの実行プロファイルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="845fa-122">You may have to use this Run As profile for some agents after you import the management pack.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="845fa-123">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="845fa-123">In this section</span></span>  
  
-   [<span data-ttu-id="845fa-124">この管理パックのファイル</span><span class="sxs-lookup"><span data-stu-id="845fa-124">Files in This Management Pack</span></span>](../technical-guides/files-in-this-management-pack.md)  
  
-   [<span data-ttu-id="845fa-125">推奨される追加の管理パック</span><span class="sxs-lookup"><span data-stu-id="845fa-125">Recommended Additional Management Packs</span></span>](../technical-guides/recommended-additional-management-packs.md)