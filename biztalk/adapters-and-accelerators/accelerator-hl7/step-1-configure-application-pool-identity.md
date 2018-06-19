---
title: '手順 1: アプリケーション プール Id の構成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, application pools
- application pools
ms.assetid: 66286327-8580-4378-89ee-ddd7204b03c6
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e61ee2994e81c3fdd352506d6a9757cde557fbb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206578"
---
# <a name="step-1-configure-application-pool-identity"></a><span data-ttu-id="06491-102">手順 1: アプリケーション プール Id を構成します。</span><span class="sxs-lookup"><span data-stu-id="06491-102">Step 1: Configure Application Pool Identity</span></span>
<span data-ttu-id="06491-103">このチュートリアルでのアプリケーション プールを使用する[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Web サービスとして公開するオーケストレーションを処理するように、インターネット インフォメーション サービス (IIS)。</span><span class="sxs-lookup"><span data-stu-id="06491-103">In this tutorial, you use an application pool in [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Internet Information Services (IIS) to process the orchestration, which you publish as a Web service.</span></span> <span data-ttu-id="06491-104">アプリケーション プールは、ワーカー プロセスで処理された 1 つまたは複数の Url のグループです。</span><span class="sxs-lookup"><span data-stu-id="06491-104">An application pool is a grouping of one or more URLs served by a worker process.</span></span>  
  
 <span data-ttu-id="06491-105">アプリケーション プールの id は、アプリケーション プールのワーカー プロセスを実行するサービス アカウントの名前です。</span><span class="sxs-lookup"><span data-stu-id="06491-105">The identity of an application pool is the name of the service account under which the worker process of the application pool runs.</span></span> <span data-ttu-id="06491-106">既定では、アプリケーション プールは、低レベルのユーザー アクセス権があり、このチュートリアルでは関数には十分ではありませんが、ネットワーク サービスのユーザー アカウントで動作します。</span><span class="sxs-lookup"><span data-stu-id="06491-106">By default, application pools operate under the Network Service user account, which has low-level user-access rights and is insufficient for this tutorial to function.</span></span> <span data-ttu-id="06491-107">セキュリティ上の理由では、絶対最小権限を持つユーザー アカウントにアプリケーション プール id を構成するメッセージ ボックス データベース (BizTalkMsgBoxDb) および (とも呼ばれる、BizTalk の構成データベースに書き込む最小のアクセス許可管理データベース、または BizTalkMgmtDb)。</span><span class="sxs-lookup"><span data-stu-id="06491-107">For security reasons, you want to configure the application pool identity to a user account with the absolute minimum permissions, but at least permissions to write to the MessageBox database (BizTalkMsgBoxDb) and Configuration database (also known as the BizTalk Management database, or BizTalkMgmtDb).</span></span>  
  
### <a name="to-change-the-service-account-under-which-an-application-pool-runs"></a><span data-ttu-id="06491-108">アプリケーション プールを実行するサービス アカウントを変更するには</span><span class="sxs-lookup"><span data-stu-id="06491-108">To change the service account under which an application pool runs</span></span>  
  
1.  <span data-ttu-id="06491-109">をクリックして**開始**、 をポイント**プログラム**、 をポイント**管理ツール**、クリックして**インターネット インフォメーション サービス (IIS) マネージャー**.</span><span class="sxs-lookup"><span data-stu-id="06491-109">Click **Start**, point to **Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="06491-110">インターネット インフォメーション サービス (IIS) マネージャーでは、ローカル コンピューター を展開し、展開**アプリケーション プール**です。</span><span class="sxs-lookup"><span data-stu-id="06491-110">In Internet Information Services (IIS) Manager, expand the local computer, and expand **Application Pools**.</span></span>  
  
3.  <span data-ttu-id="06491-111">構成するアプリケーション プールを右クリックし (既定では、このチュートリアルの実行、 **DefaultAppPool**)、順にクリック**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="06491-111">Right-click the application pool you want to configure (by default, this tutorial runs under the **DefaultAppPool**), and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="06491-112">DefaultAppPool プロパティ ダイアログ ボックスで、 **Identity**  タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="06491-112">In the DefaultAppPool Properties dialog box, on the **Identity** tab, do the following:</span></span>  
  
    |<span data-ttu-id="06491-113">プロパティ</span><span class="sxs-lookup"><span data-stu-id="06491-113">Use this</span></span>|<span data-ttu-id="06491-114">目的</span><span class="sxs-lookup"><span data-stu-id="06491-114">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="06491-115">**定義済み**</span><span class="sxs-lookup"><span data-stu-id="06491-115">**Predefined**</span></span>|<span data-ttu-id="06491-116">選択を解除**定義済みの**します。</span><span class="sxs-lookup"><span data-stu-id="06491-116">Deselect **Predefined**.</span></span> <span data-ttu-id="06491-117">**定義済みの**次などの標準的なサービス アカウントを参照します。</span><span class="sxs-lookup"><span data-stu-id="06491-117">**Predefined** refers to standard service accounts, such as the following:</span></span><br /><br /> <span data-ttu-id="06491-118">-   **ネットワーク サービス**(既定)、リモート コンピューター上のリソースにアクセスするために使用できる低レベルのユーザー アクセス権を持っています。</span><span class="sxs-lookup"><span data-stu-id="06491-118">-   **Network Service** (the default), which has low-level user access rights that can be used for access to resources on remote computers.</span></span><br /><span data-ttu-id="06491-119">-   **ローカル サービス**、低レベルのアクセス権を持っています。</span><span class="sxs-lookup"><span data-stu-id="06491-119">-   **Local Service**, which has low-level access rights.</span></span> <span data-ttu-id="06491-120">リモート コンピューター上のリソースへのアクセスを必要としない場合は、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="06491-120">You use this setting for situations that do not require access to resources on remote computers.</span></span><br /><span data-ttu-id="06491-121">-   **ローカル システム**、Network Service や Local Service アカウントよりも多くのユーザー権限を持つアカウントであります。</span><span class="sxs-lookup"><span data-stu-id="06491-121">-   **Local System**, which is an account with more user rights than the Network Service or Local Service account.</span></span>|  
    |<span data-ttu-id="06491-122">**構成可能**</span><span class="sxs-lookup"><span data-stu-id="06491-122">**Configurable**</span></span>|<span data-ttu-id="06491-123">選択**構成可能な**します。</span><span class="sxs-lookup"><span data-stu-id="06491-123">Select **Configurable**.</span></span> <span data-ttu-id="06491-124">**構成可能な**は登録されているユーザー名を参照します。</span><span class="sxs-lookup"><span data-stu-id="06491-124">**Configurable** refers to registered user names.</span></span>|  
    |<span data-ttu-id="06491-125">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="06491-125">**User name**</span></span>|<span data-ttu-id="06491-126">ワーカー プロセスを操作するアカウントのユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="06491-126">Type the user name of the account under which you want the worker process to operate.</span></span>|  
    |<span data-ttu-id="06491-127">**Password**</span><span class="sxs-lookup"><span data-stu-id="06491-127">**Password**</span></span>|<span data-ttu-id="06491-128">パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="06491-128">Type the password.</span></span>|  
  
5.  <span data-ttu-id="06491-129">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="06491-129">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="06491-130">代わりに、セキュリティ強化のため、このチュートリアルに対応したアクセス許可で作成したカスタム id を実行しているまったく新しいアプリケーション プールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="06491-130">Alternatively, for increased security, you could create an entirely new application pool that runs under a custom identity that you create with permissions tailored for this tutorial.</span></span>  
  
 <span data-ttu-id="06491-131">進みます[手順 2: 新しいプロジェクトを作成](../../adapters-and-accelerators/accelerator-hl7/step-2-create-a-new-project.md)です。</span><span class="sxs-lookup"><span data-stu-id="06491-131">Proceed to [Step 2: Create a New Project](../../adapters-and-accelerators/accelerator-hl7/step-2-create-a-new-project.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06491-132">参照</span><span class="sxs-lookup"><span data-stu-id="06491-132">See Also</span></span>  
 [<span data-ttu-id="06491-133">メッセージの強化のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="06491-133">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)