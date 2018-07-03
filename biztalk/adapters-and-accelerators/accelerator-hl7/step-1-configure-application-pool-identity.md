---
title: '手順 1: アプリケーション プール Id の構成 |Microsoft Docs'
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
ms.openlocfilehash: 61cdbc019b2e36ea8c50d97ff03597374cb07253
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988491"
---
# <a name="step-1-configure-application-pool-identity"></a><span data-ttu-id="b541a-102">手順 1: アプリケーション プール Id を構成します。</span><span class="sxs-lookup"><span data-stu-id="b541a-102">Step 1: Configure Application Pool Identity</span></span>
<span data-ttu-id="b541a-103">このチュートリアルでは、Web サービスとして公開するオーケストレーションを処理するのに Microsoft インターネット インフォメーション サービス (IIS) アプリケーション プールを使用します。</span><span class="sxs-lookup"><span data-stu-id="b541a-103">In this tutorial, you use an application pool in Microsoft Internet Information Services (IIS) to process the orchestration, which you publish as a Web service.</span></span> <span data-ttu-id="b541a-104">アプリケーション プールは、ワーカー プロセスによって提供される Url の 1 つまたは複数のグループです。</span><span class="sxs-lookup"><span data-stu-id="b541a-104">An application pool is a grouping of one or more URLs served by a worker process.</span></span>  

 <span data-ttu-id="b541a-105">アプリケーション プールの id は、アプリケーション プールのワーカー プロセスを実行するサービス アカウントの名前です。</span><span class="sxs-lookup"><span data-stu-id="b541a-105">The identity of an application pool is the name of the service account under which the worker process of the application pool runs.</span></span> <span data-ttu-id="b541a-106">既定では、アプリケーション プールは、低レベルのユーザー アクセス権があり、このチュートリアルでは関数には不十分ですが、ネットワーク サービスのユーザー アカウントで動作します。</span><span class="sxs-lookup"><span data-stu-id="b541a-106">By default, application pools operate under the Network Service user account, which has low-level user-access rights and is insufficient for this tutorial to function.</span></span> <span data-ttu-id="b541a-107">セキュリティ上の理由から、絶対の最小アクセス許可を持つが、ユーザー アカウントにアプリケーション プール id を構成するのには、メッセージ ボックス データベース (BizTalkMsgBoxDb) と構成データベース (とも呼ばれる、BizTalk を書き込めません最小のアクセス許可。管理データベース、または BizTalkMgmtDb)。</span><span class="sxs-lookup"><span data-stu-id="b541a-107">For security reasons, you want to configure the application pool identity to a user account with the absolute minimum permissions, but at least permissions to write to the MessageBox database (BizTalkMsgBoxDb) and Configuration database (also known as the BizTalk Management database, or BizTalkMgmtDb).</span></span>  

### <a name="to-change-the-service-account-under-which-an-application-pool-runs"></a><span data-ttu-id="b541a-108">アプリケーション プールを実行するサービス アカウントを変更するには</span><span class="sxs-lookup"><span data-stu-id="b541a-108">To change the service account under which an application pool runs</span></span>  

1. <span data-ttu-id="b541a-109">クリックして**開始**、 をポイント**プログラム**、 をポイント**管理ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) マネージャー**.</span><span class="sxs-lookup"><span data-stu-id="b541a-109">Click **Start**, point to **Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  

2. <span data-ttu-id="b541a-110">インターネット インフォメーション サービス (IIS) マネージャーでは、ローカルのコンピューターを展開し、展開**アプリケーション プール**します。</span><span class="sxs-lookup"><span data-stu-id="b541a-110">In Internet Information Services (IIS) Manager, expand the local computer, and expand **Application Pools**.</span></span>  

3. <span data-ttu-id="b541a-111">構成するアプリケーション プールを右クリックし (既定では、このチュートリアルの実行で、 **DefaultAppPool**)、順にクリックします**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="b541a-111">Right-click the application pool you want to configure (by default, this tutorial runs under the **DefaultAppPool**), and then click **Properties**.</span></span>  

4. <span data-ttu-id="b541a-112">DefaultAppPool プロパティ ダイアログ ボックスで、上、 **Identity**  タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b541a-112">In the DefaultAppPool Properties dialog box, on the **Identity** tab, do the following:</span></span>  


   |     <span data-ttu-id="b541a-113">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b541a-113">Use this</span></span>     |                                                                                                                                                                                                                                                                     <span data-ttu-id="b541a-114">目的</span><span class="sxs-lookup"><span data-stu-id="b541a-114">To do this</span></span>                                                                                                                                                                                                                                                                      |
   |------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |  <span data-ttu-id="b541a-115">**定義済み**</span><span class="sxs-lookup"><span data-stu-id="b541a-115">**Predefined**</span></span>  | <span data-ttu-id="b541a-116">選択を解除**定義済みの**します。</span><span class="sxs-lookup"><span data-stu-id="b541a-116">Deselect **Predefined**.</span></span> <span data-ttu-id="b541a-117">**定義済みの**次などの標準のサービス アカウントには。</span><span class="sxs-lookup"><span data-stu-id="b541a-117">**Predefined** refers to standard service accounts, such as the following:</span></span><br /><br /> <span data-ttu-id="b541a-118">-   **ネットワーク サービス**(既定)、リモート コンピューター上のリソースにアクセスするために使用できる低レベルのユーザー アクセス権を持っています。</span><span class="sxs-lookup"><span data-stu-id="b541a-118">-   **Network Service** (the default), which has low-level user access rights that can be used for access to resources on remote computers.</span></span><br /><span data-ttu-id="b541a-119">-   **ローカル サービス**、低レベルのアクセス権を持っています。</span><span class="sxs-lookup"><span data-stu-id="b541a-119">-   **Local Service**, which has low-level access rights.</span></span> <span data-ttu-id="b541a-120">リモート コンピューター上のリソースへのアクセスを必要としない場合は、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="b541a-120">You use this setting for situations that do not require access to resources on remote computers.</span></span><br /><span data-ttu-id="b541a-121">-   **ローカル システム**、Network Service や Local Service アカウントよりも多くのユーザー権限を持つアカウントであります。</span><span class="sxs-lookup"><span data-stu-id="b541a-121">-   **Local System**, which is an account with more user rights than the Network Service or Local Service account.</span></span> |
   | <span data-ttu-id="b541a-122">**構成可能**</span><span class="sxs-lookup"><span data-stu-id="b541a-122">**Configurable**</span></span> |                                                                                                                                                                                                                                     <span data-ttu-id="b541a-123">選択**構成可能な**します。</span><span class="sxs-lookup"><span data-stu-id="b541a-123">Select **Configurable**.</span></span> <span data-ttu-id="b541a-124">**構成可能な**登録済みのユーザー名を参照します。</span><span class="sxs-lookup"><span data-stu-id="b541a-124">**Configurable** refers to registered user names.</span></span>                                                                                                                                                                                                                                      |
   |  <span data-ttu-id="b541a-125">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="b541a-125">**User name**</span></span>   |                                                                                                                                                                                                                                <span data-ttu-id="b541a-126">ワーカー プロセスが動作するアカウントのユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="b541a-126">Type the user name of the account under which you want the worker process to operate.</span></span>                                                                                                                                                                                                                                |
   |   <span data-ttu-id="b541a-127">**Password**</span><span class="sxs-lookup"><span data-stu-id="b541a-127">**Password**</span></span>   |                                                                                                                                                                                                                                                                 <span data-ttu-id="b541a-128">パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="b541a-128">Type the password.</span></span>                                                                                                                                                                                                                                                                  |


5. <span data-ttu-id="b541a-129">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b541a-129">Click **OK**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="b541a-130">または、セキュリティ強化のためのこのチュートリアルに対応したアクセス許可で作成したカスタム id の下で実行するまったく新しいアプリケーション プールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b541a-130">Alternatively, for increased security, you could create an entirely new application pool that runs under a custom identity that you create with permissions tailored for this tutorial.</span></span>  

   <span data-ttu-id="b541a-131">続行する[手順 2: 新しいプロジェクトを作成](../../adapters-and-accelerators/accelerator-hl7/step-2-create-a-new-project.md)です。</span><span class="sxs-lookup"><span data-stu-id="b541a-131">Proceed to [Step 2: Create a New Project](../../adapters-and-accelerators/accelerator-hl7/step-2-create-a-new-project.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="b541a-132">参照</span><span class="sxs-lookup"><span data-stu-id="b541a-132">See Also</span></span>  
 [<span data-ttu-id="b541a-133">メッセージ強化のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="b541a-133">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)