---
title: "無効なバインド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3e851f7f-ffc8-4f55-b06e-501a7f41b32a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e5733df4d4d7d6ef9e70e6a2a16302cc19ac5d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-binding"></a><span data-ttu-id="b63a9-102">バインドが無効です</span><span class="sxs-lookup"><span data-stu-id="b63a9-102">Invalid binding</span></span>
## <a name="details"></a><span data-ttu-id="b63a9-103">詳細</span><span class="sxs-lookup"><span data-stu-id="b63a9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b63a9-104">製品名</span><span class="sxs-lookup"><span data-stu-id="b63a9-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="b63a9-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="b63a9-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="b63a9-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="b63a9-106">Event ID</span></span>|<span data-ttu-id="b63a9-107">0</span><span class="sxs-lookup"><span data-stu-id="b63a9-107">0</span></span>|  
|<span data-ttu-id="b63a9-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="b63a9-108">Event Source</span></span>|<span data-ttu-id="b63a9-109">0</span><span class="sxs-lookup"><span data-stu-id="b63a9-109">0</span></span>|  
|<span data-ttu-id="b63a9-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b63a9-110">Component</span></span>|<span data-ttu-id="b63a9-111">0</span><span class="sxs-lookup"><span data-stu-id="b63a9-111">0</span></span>|  
|<span data-ttu-id="b63a9-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="b63a9-112">Symbolic Name</span></span>|<span data-ttu-id="b63a9-113">0</span><span class="sxs-lookup"><span data-stu-id="b63a9-113">0</span></span>|  
|<span data-ttu-id="b63a9-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="b63a9-114">Message Text</span></span>|<span data-ttu-id="b63a9-115">バインドが無効です</span><span class="sxs-lookup"><span data-stu-id="b63a9-115">Invalid binding</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b63a9-116">説明</span><span class="sxs-lookup"><span data-stu-id="b63a9-116">Explanation</span></span>  
 <span data-ttu-id="b63a9-117">このエラーは、受信場所または送信ポートのバインディング構成に指定されたバインディングを、アダプターが作成できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="b63a9-117">This error indicates the adapter cannot create the binding specified in the binding configuration of the receive location or send port.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b63a9-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="b63a9-118">User Action</span></span>  
 <span data-ttu-id="b63a9-119">バインディング要素を確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b63a9-119">Use the following procedure to verify binding elements.</span></span>  
  
#### <a name="to-verify-binding-elements"></a><span data-ttu-id="b63a9-120">バインド要素を検証するには</span><span class="sxs-lookup"><span data-stu-id="b63a9-120">To verify binding elements</span></span>  
  
1.  <span data-ttu-id="b63a9-121">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="b63a9-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="b63a9-122">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="b63a9-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="b63a9-123">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="b63a9-123">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="b63a9-124">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="b63a9-124">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="b63a9-125">**[プロパティ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b63a9-125">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="b63a9-126">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="b63a9-126">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="b63a9-127">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="b63a9-127">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="b63a9-128">**WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブです。</span><span class="sxs-lookup"><span data-stu-id="b63a9-128">In the **WCF [***transport type***] Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="b63a9-129">構成に指定されているバインディング要素が有効であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b63a9-129">Ensure the binding elements specified in the configuration are valid.</span></span>