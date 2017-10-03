---
title: "バインド要素を作成できません |。Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5b036833-12ba-463c-8df6-9d5e1ac26b6d
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9b93bfd8ca7f87904f32fefa60837603677bc23
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="unable-to-create-binding-element"></a><span data-ttu-id="df119-102">バインド要素を作成できません</span><span class="sxs-lookup"><span data-stu-id="df119-102">Unable to create binding element</span></span>
## <a name="details"></a><span data-ttu-id="df119-103">詳細</span><span class="sxs-lookup"><span data-stu-id="df119-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="df119-104">製品名</span><span class="sxs-lookup"><span data-stu-id="df119-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="df119-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="df119-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="df119-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="df119-106">Event ID</span></span>|<span data-ttu-id="df119-107">0</span><span class="sxs-lookup"><span data-stu-id="df119-107">0</span></span>|  
|<span data-ttu-id="df119-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="df119-108">Event Source</span></span>|<span data-ttu-id="df119-109">0</span><span class="sxs-lookup"><span data-stu-id="df119-109">0</span></span>|  
|<span data-ttu-id="df119-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="df119-110">Component</span></span>|<span data-ttu-id="df119-111">0</span><span class="sxs-lookup"><span data-stu-id="df119-111">0</span></span>|  
|<span data-ttu-id="df119-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="df119-112">Symbolic Name</span></span>|<span data-ttu-id="df119-113">0</span><span class="sxs-lookup"><span data-stu-id="df119-113">0</span></span>|  
|<span data-ttu-id="df119-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="df119-114">Message Text</span></span>|<span data-ttu-id="df119-115">バインド "{0}" のバインド要素を作成できません。</span><span class="sxs-lookup"><span data-stu-id="df119-115">Unable to create binding element for binding "{0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="df119-116">説明</span><span class="sxs-lookup"><span data-stu-id="df119-116">Explanation</span></span>  
 <span data-ttu-id="df119-117">このエラーは、アダプターで、構成に指定されているバインディングを実行時に作成できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="df119-117">This error indicates the adapter cannot create the binding specified in the configuration at runtime.</span></span> <span data-ttu-id="df119-118">この状況は、主に WCF-Custom アダプターおよび WCF-CustomIsolated アダプターで発生します。</span><span class="sxs-lookup"><span data-stu-id="df119-118">This situation occurs primarily with the WCF-Custom and WCF-CustomIsolated adapters.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="df119-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="df119-119">User Action</span></span>  
 <span data-ttu-id="df119-120">バインド要素が有効なことを確認するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="df119-120">Use the following procedure to verify binding elements are valid.</span></span>  
  
#### <a name="to-verify-binding-elements"></a><span data-ttu-id="df119-121">バインド要素を検証するには</span><span class="sxs-lookup"><span data-stu-id="df119-121">To verify binding elements</span></span>  
  
1.  <span data-ttu-id="df119-122">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="df119-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="df119-123">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="df119-123">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="df119-124">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="df119-124">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="df119-125">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="df119-125">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="df119-126">**[プロパティ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df119-126">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="df119-127">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="df119-127">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="df119-128">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="df119-128">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="df119-129">**WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブです。</span><span class="sxs-lookup"><span data-stu-id="df119-129">In the **WCF [***transport type***] Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="df119-130">構成で指定されたバインド要素が有効なことを確認します。</span><span class="sxs-lookup"><span data-stu-id="df119-130">Ensure that the binding elements specified in the configuration are valid.</span></span>