---
title: サービス エンドポイント構成をエクスポートできません |。Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 795145fa-0ce4-498f-a82e-eb752a5f4764
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3b36fa47d9302f3f88f65575bfa8f74c6469e9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286882"
---
# <a name="unable-to-export-service-endpoint-configuration"></a><span data-ttu-id="64cd7-102">サービス エンドポイント構成をエクスポートできません</span><span class="sxs-lookup"><span data-stu-id="64cd7-102">Unable to export service endpoint configuration</span></span>
## <a name="details"></a><span data-ttu-id="64cd7-103">詳細</span><span class="sxs-lookup"><span data-stu-id="64cd7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="64cd7-104">製品名</span><span class="sxs-lookup"><span data-stu-id="64cd7-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="64cd7-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="64cd7-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="64cd7-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="64cd7-106">Event ID</span></span>|<span data-ttu-id="64cd7-107">0</span><span class="sxs-lookup"><span data-stu-id="64cd7-107">0</span></span>|  
|<span data-ttu-id="64cd7-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="64cd7-108">Event Source</span></span>|<span data-ttu-id="64cd7-109">0</span><span class="sxs-lookup"><span data-stu-id="64cd7-109">0</span></span>|  
|<span data-ttu-id="64cd7-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="64cd7-110">Component</span></span>|<span data-ttu-id="64cd7-111">0</span><span class="sxs-lookup"><span data-stu-id="64cd7-111">0</span></span>|  
|<span data-ttu-id="64cd7-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="64cd7-112">Symbolic Name</span></span>|<span data-ttu-id="64cd7-113">0</span><span class="sxs-lookup"><span data-stu-id="64cd7-113">0</span></span>|  
|<span data-ttu-id="64cd7-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="64cd7-114">Message Text</span></span>|<span data-ttu-id="64cd7-115">サービス エンドポイント構成を "{0}" にエクスポートできません</span><span class="sxs-lookup"><span data-stu-id="64cd7-115">Unable to export service endpoint configuration to "{0}"</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="64cd7-116">説明</span><span class="sxs-lookup"><span data-stu-id="64cd7-116">Explanation</span></span>  
 <span data-ttu-id="64cd7-117">このエラーは、宛先に書き込むアクセス許可がユーザーにない可能性があることを示します。</span><span class="sxs-lookup"><span data-stu-id="64cd7-117">This error indicates the user may not have permission to write to the destination.</span></span> <span data-ttu-id="64cd7-118">または、[アドレス (URI)] や [バインディングの種類] など、必要なプロパティの一部が適切に指定されませんでした。</span><span class="sxs-lookup"><span data-stu-id="64cd7-118">Or some of the required properties were not correctly specified, such as Address (URI), and Binding Type.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="64cd7-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="64cd7-119">User Action</span></span>  
 <span data-ttu-id="64cd7-120">エンドポイント ID を構成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="64cd7-120">Use the following procedure to configure the endpoint identity.</span></span>  
  
#### <a name="to-configure-the-endpoint-identity"></a><span data-ttu-id="64cd7-121">エンドポイント ID を構成するには</span><span class="sxs-lookup"><span data-stu-id="64cd7-121">To configure the endpoint identity</span></span>  
  
1.  <span data-ttu-id="64cd7-122">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="64cd7-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="64cd7-123">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="64cd7-123">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="64cd7-124">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="64cd7-124">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="64cd7-125">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="64cd7-125">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="64cd7-126">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64cd7-126">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="64cd7-127">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="64cd7-127">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="64cd7-128">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="64cd7-128">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="64cd7-129">Wcf **[***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブです。</span><span class="sxs-lookup"><span data-stu-id="64cd7-129">In the WCF **[***transport type***] Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="64cd7-130">コピー先フォルダーへの書き込みが許可されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="64cd7-130">Ensure that writing to the destination folder is permitted.</span></span>  
  
10. <span data-ttu-id="64cd7-131">チェック、**動作** タブおよび**エンドポイント Id**の設定、**全般**が有効であることを確認するには、タブ。</span><span class="sxs-lookup"><span data-stu-id="64cd7-131">Check the **Behavior** tab and the **Endpoint Identity** settings in the **General** tab to ensure they are valid.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="64cd7-132">送信先フォルダーの書き込みアクセス権が必要です。</span><span class="sxs-lookup"><span data-stu-id="64cd7-132">You must have write permissions to the destination folder.</span></span> <span data-ttu-id="64cd7-133">必要なアクセス権を取得するには、コンピューターの管理者に連絡してください。</span><span class="sxs-lookup"><span data-stu-id="64cd7-133">Contact the administrator of the machine to get these permissions.</span></span>