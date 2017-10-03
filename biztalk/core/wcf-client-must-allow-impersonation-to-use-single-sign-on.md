---
title: "WCF クライアントでのシングル サインオンを使用するための偽装を許可する必要があります |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5b9f294-4d8a-4a12-91e8-8d325db7c420
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5e43039a69d057b0d20767ff9061a8d6b4e4f70
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="wcf-client-must-allow-impersonation-to-use-single-sign-on"></a><span data-ttu-id="93450-102">シングル サインオンを使用するには、WCF クライアントが権限借用を許可する必要があります</span><span class="sxs-lookup"><span data-stu-id="93450-102">WCF client must allow impersonation to use Single Sign-On</span></span>
## <a name="details"></a><span data-ttu-id="93450-103">詳細</span><span class="sxs-lookup"><span data-stu-id="93450-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="93450-104">製品名</span><span class="sxs-lookup"><span data-stu-id="93450-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="93450-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="93450-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="93450-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="93450-106">Event ID</span></span>|<span data-ttu-id="93450-107">0</span><span class="sxs-lookup"><span data-stu-id="93450-107">0</span></span>|  
|<span data-ttu-id="93450-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="93450-108">Event Source</span></span>|<span data-ttu-id="93450-109">0</span><span class="sxs-lookup"><span data-stu-id="93450-109">0</span></span>|  
|<span data-ttu-id="93450-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="93450-110">Component</span></span>|<span data-ttu-id="93450-111">0</span><span class="sxs-lookup"><span data-stu-id="93450-111">0</span></span>|  
|<span data-ttu-id="93450-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="93450-112">Symbolic Name</span></span>|<span data-ttu-id="93450-113">0</span><span class="sxs-lookup"><span data-stu-id="93450-113">0</span></span>|  
|<span data-ttu-id="93450-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="93450-114">Message Text</span></span>|<span data-ttu-id="93450-115">シングル サインオンを使用するには、WCF クライアントが権限借用を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93450-115">The WCF client must allow impersonation to use Single Sign-On</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="93450-116">説明</span><span class="sxs-lookup"><span data-stu-id="93450-116">Explanation</span></span>  
 <span data-ttu-id="93450-117">シングル サインオン (SSO) が受信場所で有効ですが、WCF クライアントでは偽装を許可していません。</span><span class="sxs-lookup"><span data-stu-id="93450-117">Single Sign-On (SSO) is enabled in the receive location but the WCF client does not allow impersonation.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="93450-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="93450-118">User Action</span></span>  
 <span data-ttu-id="93450-119">サービスを実行する WCF クライアントが偽装を許可するようにします。</span><span class="sxs-lookup"><span data-stu-id="93450-119">Ensure that the WCF client invoking the service allows impersonation.</span></span>  
  
1.  <span data-ttu-id="93450-120">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="93450-120">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="93450-121">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="93450-121">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="93450-122">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="93450-122">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="93450-123">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="93450-123">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="93450-124">**[プロパティ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="93450-124">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="93450-125">ポート**型**一覧で、 **Wcf-custom** (または**Wcf-customisolate**)。</span><span class="sxs-lookup"><span data-stu-id="93450-125">In the port **Type** list, select **WCF-Custom** (or **WCF-CustomIsolate**).</span></span>  
  
7.  <span data-ttu-id="93450-126">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="93450-126">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="93450-127">**WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**動作**タブです。</span><span class="sxs-lookup"><span data-stu-id="93450-127">In the **WCF [***transport type***] Transport Properties** dialog box, click the **Behavior** tab.</span></span>  
  
9. <span data-ttu-id="93450-128">**動作**セクションで、 **ServiceAuthorization**です。</span><span class="sxs-lookup"><span data-stu-id="93450-128">In the **Behavior** section, click **ServiceAuthorization**.</span></span> <span data-ttu-id="93450-129">**構成**セクションで、プロパティ**ImpersonateCallerForAllOperations**に設定する必要があります**True**です。</span><span class="sxs-lookup"><span data-stu-id="93450-129">In the **Configuration** section, the property **ImpersonateCallerForAllOperations** should be set to **True**.</span></span>  
  
10. <span data-ttu-id="93450-130">**WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**他** タブ。</span><span class="sxs-lookup"><span data-stu-id="93450-130">In the **WCF [***transport type***] Transport Properties** dialog box, click the **Other** tab.</span></span>  
  
11. <span data-ttu-id="93450-131">資格情報のセクションで、オプションを選択**を使用してシングル サインオン**です。</span><span class="sxs-lookup"><span data-stu-id="93450-131">In the Credentials sections, select the option **Use Single Sign-On**.</span></span>