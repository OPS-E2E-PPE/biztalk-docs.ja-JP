---
title: "Id の作成に失敗しました |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 531f1057-1b6d-40ae-bf2f-a36baf4e0341
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 246db2e9546fbbea3db07cbaa5267f57936dfa14
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="failed-to-create-identity"></a><span data-ttu-id="16ae0-102">ID を作成できませんでした</span><span class="sxs-lookup"><span data-stu-id="16ae0-102">Failed to create identity</span></span>
## <a name="details"></a><span data-ttu-id="16ae0-103">詳細</span><span class="sxs-lookup"><span data-stu-id="16ae0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="16ae0-104">製品名</span><span class="sxs-lookup"><span data-stu-id="16ae0-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="16ae0-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="16ae0-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="16ae0-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="16ae0-106">Event ID</span></span>|<span data-ttu-id="16ae0-107">0</span><span class="sxs-lookup"><span data-stu-id="16ae0-107">0</span></span>|  
|<span data-ttu-id="16ae0-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="16ae0-108">Event Source</span></span>|<span data-ttu-id="16ae0-109">0</span><span class="sxs-lookup"><span data-stu-id="16ae0-109">0</span></span>|  
|<span data-ttu-id="16ae0-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="16ae0-110">Component</span></span>|<span data-ttu-id="16ae0-111">0</span><span class="sxs-lookup"><span data-stu-id="16ae0-111">0</span></span>|  
|<span data-ttu-id="16ae0-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="16ae0-112">Symbolic Name</span></span>|<span data-ttu-id="16ae0-113">0</span><span class="sxs-lookup"><span data-stu-id="16ae0-113">0</span></span>|  
|<span data-ttu-id="16ae0-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="16ae0-114">Message Text</span></span>|<span data-ttu-id="16ae0-115">このエラーは、アダプターがエンドポイント ID を作成できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="16ae0-115">This error indicates the adapter failed to create the endpoint identity.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="16ae0-116">説明</span><span class="sxs-lookup"><span data-stu-id="16ae0-116">Explanation</span></span>  
 <span data-ttu-id="16ae0-117">このエラーは、アダプターがエンドポイント ID を作成できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="16ae0-117">This error indicates the adapter failed to create the endpoint identity.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="16ae0-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="16ae0-118">User Action</span></span>  
 <span data-ttu-id="16ae0-119">エンドポイント ID を構成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="16ae0-119">Use the following procedure to configure the endpoint identity.</span></span>  
  
#### <a name="to-configure-the-endpoint-identity"></a><span data-ttu-id="16ae0-120">エンドポイント ID を構成するには</span><span class="sxs-lookup"><span data-stu-id="16ae0-120">To configure the endpoint identity</span></span>  
  
1.  <span data-ttu-id="16ae0-121">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="16ae0-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="16ae0-122">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="16ae0-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="16ae0-123">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="16ae0-123">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="16ae0-124">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="16ae0-124">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="16ae0-125">**[プロパティ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="16ae0-125">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="16ae0-126">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="16ae0-126">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="16ae0-127">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="16ae0-127">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="16ae0-128">**WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブです。</span><span class="sxs-lookup"><span data-stu-id="16ae0-128">In the **WCF [***transport type***] Transport Properties** dialog box, click the **General** tab.</span></span>  
  
9. <span data-ttu-id="16ae0-129">**エンドポイント Id**セクションで、**編集**です。</span><span class="sxs-lookup"><span data-stu-id="16ae0-129">In the **Endpoint Identity** section, click **Edit**.</span></span>  
  
10. <span data-ttu-id="16ae0-130">**Id エディター**  ダイアログ ボックスで、設定が有効であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="16ae0-130">In the **Identity Editor** dialog box, ensure that the settings are valid.</span></span>