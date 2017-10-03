---
title: "不明または予期しないバインド要素 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56021ff3-5abf-46ab-90bb-4531ccc9abd0
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43c59c20968ea1329a6d689c7976aeba48650fc2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="unknown-or-unexpected-binding-element"></a><span data-ttu-id="95576-102">不明または予期しないバインド要素が含まれています</span><span class="sxs-lookup"><span data-stu-id="95576-102">Unknown or unexpected binding element</span></span>
## <a name="details"></a><span data-ttu-id="95576-103">詳細</span><span class="sxs-lookup"><span data-stu-id="95576-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="95576-104">製品名</span><span class="sxs-lookup"><span data-stu-id="95576-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="95576-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="95576-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="95576-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="95576-106">Event ID</span></span>|<span data-ttu-id="95576-107">0</span><span class="sxs-lookup"><span data-stu-id="95576-107">0</span></span>|  
|<span data-ttu-id="95576-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="95576-108">Event Source</span></span>|<span data-ttu-id="95576-109">0</span><span class="sxs-lookup"><span data-stu-id="95576-109">0</span></span>|  
|<span data-ttu-id="95576-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="95576-110">Component</span></span>|<span data-ttu-id="95576-111">0</span><span class="sxs-lookup"><span data-stu-id="95576-111">0</span></span>|  
|<span data-ttu-id="95576-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="95576-112">Symbolic Name</span></span>|<span data-ttu-id="95576-113">0</span><span class="sxs-lookup"><span data-stu-id="95576-113">0</span></span>|  
|<span data-ttu-id="95576-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="95576-114">Message Text</span></span>|<span data-ttu-id="95576-115">不明または予期しないバインド要素が含まれています</span><span class="sxs-lookup"><span data-stu-id="95576-115">Unknown or unexpected binding element</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="95576-116">説明</span><span class="sxs-lookup"><span data-stu-id="95576-116">Explanation</span></span>  
 <span data-ttu-id="95576-117">このエラーは、アダプターで、バインディングに指定されているユーザー定義のバインディング要素を検索できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="95576-117">This error indicates the adapter cannot find the user defined binding element specified in the binding.</span></span> <span data-ttu-id="95576-118">この状況は、主に WCF-Custom アダプターおよび WCF-CustomIsolated アダプターで発生します。</span><span class="sxs-lookup"><span data-stu-id="95576-118">This situation occurs primarily with the WCF-Custom and WCF-CustomIsolated adapters.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="95576-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="95576-119">User Action</span></span>  
 <span data-ttu-id="95576-120">バインド要素が有効なことを確認するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="95576-120">Use the following procedure to verify binding elements are valid.</span></span>  
  
#### <a name="to-verify-binding-elements-are-valid"></a><span data-ttu-id="95576-121">バインディング要素が有効であることを確認するには</span><span class="sxs-lookup"><span data-stu-id="95576-121">To verify binding elements are valid</span></span>  
  
1.  <span data-ttu-id="95576-122">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="95576-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="95576-123">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="95576-123">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="95576-124">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="95576-124">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="95576-125">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="95576-125">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="95576-126">**[プロパティ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95576-126">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="95576-127">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="95576-127">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="95576-128">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="95576-128">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="95576-129">Wcf **[***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブです。</span><span class="sxs-lookup"><span data-stu-id="95576-129">In the WCF **[***transport type***] Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="95576-130">構成で指定されたバインド要素が有効なことを確認します。</span><span class="sxs-lookup"><span data-stu-id="95576-130">Ensure that the binding elements specified in the configuration are valid.</span></span>