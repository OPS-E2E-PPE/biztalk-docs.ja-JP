---
title: クライアント エンドポイント構成をエクスポートできません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d93fe5e-fdb2-49c5-86de-d428b1ecda7f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ce781105c96f12705605e7c97f0e5229d2017f4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292795"
---
# <a name="unable-to-export-client-endpoint-configuration"></a><span data-ttu-id="98082-102">クライアント エンドポイント構成をエクスポートできません。</span><span class="sxs-lookup"><span data-stu-id="98082-102">Unable to export client endpoint configuration</span></span>
## <a name="details"></a><span data-ttu-id="98082-103">詳細</span><span class="sxs-lookup"><span data-stu-id="98082-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="98082-104">製品名</span><span class="sxs-lookup"><span data-stu-id="98082-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="98082-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="98082-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="98082-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="98082-106">Event ID</span></span>     |                                         <span data-ttu-id="98082-107">0</span><span class="sxs-lookup"><span data-stu-id="98082-107">0</span></span>                                          |
|  <span data-ttu-id="98082-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="98082-108">Event Source</span></span>   |                                         <span data-ttu-id="98082-109">0</span><span class="sxs-lookup"><span data-stu-id="98082-109">0</span></span>                                          |
|    <span data-ttu-id="98082-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="98082-110">Component</span></span>    |                                         <span data-ttu-id="98082-111">0</span><span class="sxs-lookup"><span data-stu-id="98082-111">0</span></span>                                          |
|  <span data-ttu-id="98082-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="98082-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="98082-113">0</span><span class="sxs-lookup"><span data-stu-id="98082-113">0</span></span>                                          |
|  <span data-ttu-id="98082-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="98082-114">Message Text</span></span>   |              <span data-ttu-id="98082-115">クライアント エンドポイント構成をエクスポートできません"{0}"</span><span class="sxs-lookup"><span data-stu-id="98082-115">Unable to export client endpoint configuration to "{0}"</span></span>               |
  
## <a name="explanation"></a><span data-ttu-id="98082-116">説明</span><span class="sxs-lookup"><span data-stu-id="98082-116">Explanation</span></span>  
 <span data-ttu-id="98082-117">このエラーは、次のいずれかを示します。</span><span class="sxs-lookup"><span data-stu-id="98082-117">This error indicates one of the following:</span></span>  
  
-   <span data-ttu-id="98082-118">ユーザーは、先に書き込むアクセス許可がありません。</span><span class="sxs-lookup"><span data-stu-id="98082-118">The user may not have permission to write to the destination.</span></span>  
  
     <span data-ttu-id="98082-119">\- または -</span><span class="sxs-lookup"><span data-stu-id="98082-119">\- OR -</span></span>  
  
-   <span data-ttu-id="98082-120">必要なプロパティの一部が正しく指定されていないなど**アドレス (URI)** と**バインドの種類**します。</span><span class="sxs-lookup"><span data-stu-id="98082-120">Some of the required properties were not correctly specified, such as **Address (URI)** and **Binding Type**.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="98082-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="98082-121">User Action</span></span>  
 <span data-ttu-id="98082-122">次の手順を使用して、ユーザーのアクセス許可の確認入力と確認を**アドレス (URI)** と**バインドの種類**設定が無効です。</span><span class="sxs-lookup"><span data-stu-id="98082-122">Use the following procedure to verify user permissions and confirm **Address (URI)** and **Binding Type** settings are valid.</span></span>  
  
#### <a name="to-verify-user-permissions-and-confirm-settings"></a><span data-ttu-id="98082-123">ユーザーのアクセス許可を確認し、設定を確認するには</span><span class="sxs-lookup"><span data-stu-id="98082-123">To verify user permissions and confirm settings</span></span>  
  
1. <span data-ttu-id="98082-124">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="98082-124">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="98082-125">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="98082-125">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="98082-126">アプリケーションを特定して、トランスポートを見つけます。</span><span class="sxs-lookup"><span data-stu-id="98082-126">Locate your application, and then locate your transport.</span></span>  
  
4. <span data-ttu-id="98082-127">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="98082-127">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="98082-128">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98082-128">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="98082-129">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="98082-129">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="98082-130">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="98082-130">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="98082-131">Wcf **[**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。</span><span class="sxs-lookup"><span data-stu-id="98082-131">In the WCF **[**<em>transport type</em>**] Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="98082-132">コピー先のフォルダーへの書き込みが許可されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="98082-132">Ensure writing to the destination folder is permitted.</span></span>  
  
10. <span data-ttu-id="98082-133">チェック、**動作** タブと**エンドポイント Id**設定**全般**が有効であることを確認するには、タブ。</span><span class="sxs-lookup"><span data-stu-id="98082-133">Check the **Behavior** tab and the **Endpoint Identity** settings in **General** tab to ensure they are valid.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="98082-134">目的のフォルダーに書き込みアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="98082-134">You must have write permissions to the destination folder.</span></span> <span data-ttu-id="98082-135">これらのアクセス許可を取得する、コンピューターの管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="98082-135">Contact the administrator of the machine to get these permissions.</span></span>