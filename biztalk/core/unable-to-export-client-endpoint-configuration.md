---
title: クライアント エンドポイント構成をエクスポートできません |。Microsoft ドキュメント
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
ms.openlocfilehash: 941d42ff01bcf578bd7ba7c426c6fe5ca2bfbce3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286954"
---
# <a name="unable-to-export-client-endpoint-configuration"></a><span data-ttu-id="87b2a-102">クライアント エンドポイント構成をエクスポートできません</span><span class="sxs-lookup"><span data-stu-id="87b2a-102">Unable to export client endpoint configuration</span></span>
## <a name="details"></a><span data-ttu-id="87b2a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="87b2a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="87b2a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="87b2a-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="87b2a-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="87b2a-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="87b2a-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="87b2a-106">Event ID</span></span>|<span data-ttu-id="87b2a-107">0</span><span class="sxs-lookup"><span data-stu-id="87b2a-107">0</span></span>|  
|<span data-ttu-id="87b2a-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="87b2a-108">Event Source</span></span>|<span data-ttu-id="87b2a-109">0</span><span class="sxs-lookup"><span data-stu-id="87b2a-109">0</span></span>|  
|<span data-ttu-id="87b2a-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="87b2a-110">Component</span></span>|<span data-ttu-id="87b2a-111">0</span><span class="sxs-lookup"><span data-stu-id="87b2a-111">0</span></span>|  
|<span data-ttu-id="87b2a-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="87b2a-112">Symbolic Name</span></span>|<span data-ttu-id="87b2a-113">0</span><span class="sxs-lookup"><span data-stu-id="87b2a-113">0</span></span>|  
|<span data-ttu-id="87b2a-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="87b2a-114">Message Text</span></span>|<span data-ttu-id="87b2a-115">クライアント エンドポイント構成を "{0}" にエクスポートできません</span><span class="sxs-lookup"><span data-stu-id="87b2a-115">Unable to export client endpoint configuration to "{0}"</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="87b2a-116">説明</span><span class="sxs-lookup"><span data-stu-id="87b2a-116">Explanation</span></span>  
 <span data-ttu-id="87b2a-117">このエラーは、以下のいずれかを示します。</span><span class="sxs-lookup"><span data-stu-id="87b2a-117">This error indicates one of the following:</span></span>  
  
-   <span data-ttu-id="87b2a-118">宛先に書き込むアクセス許可がユーザーにない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="87b2a-118">The user may not have permission to write to the destination.</span></span>  
  
     <span data-ttu-id="87b2a-119">\- または -</span><span class="sxs-lookup"><span data-stu-id="87b2a-119">\- OR -</span></span>  
  
-   <span data-ttu-id="87b2a-120">一部の必須プロパティが正しく指定されていませんなど**アドレス (URI)** と**バインディングの種類**です。</span><span class="sxs-lookup"><span data-stu-id="87b2a-120">Some of the required properties were not correctly specified, such as **Address (URI)** and **Binding Type**.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="87b2a-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="87b2a-121">User Action</span></span>  
 <span data-ttu-id="87b2a-122">次の手順を使用して、ユーザーのアクセス許可を確認し、確認を**アドレス (URI)** と**バインディングの種類**設定が有効です。</span><span class="sxs-lookup"><span data-stu-id="87b2a-122">Use the following procedure to verify user permissions and confirm **Address (URI)** and **Binding Type** settings are valid.</span></span>  
  
#### <a name="to-verify-user-permissions-and-confirm-settings"></a><span data-ttu-id="87b2a-123">ユーザーのアクセス許可と設定を確認するには</span><span class="sxs-lookup"><span data-stu-id="87b2a-123">To verify user permissions and confirm settings</span></span>  
  
1.  <span data-ttu-id="87b2a-124">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="87b2a-124">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="87b2a-125">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="87b2a-125">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="87b2a-126">アプリケーションを特定し、トランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="87b2a-126">Locate your application, and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="87b2a-127">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="87b2a-127">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="87b2a-128">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87b2a-128">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="87b2a-129">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="87b2a-129">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="87b2a-130">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="87b2a-130">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="87b2a-131">Wcf **[***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブです。</span><span class="sxs-lookup"><span data-stu-id="87b2a-131">In the WCF **[***transport type***] Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="87b2a-132">宛先フォルダーへの書き込みが許可されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="87b2a-132">Ensure writing to the destination folder is permitted.</span></span>  
  
10. <span data-ttu-id="87b2a-133">チェック、**動作** タブおよび**エンドポイント Id**で設定**全般**が有効であることを確認するには、タブ。</span><span class="sxs-lookup"><span data-stu-id="87b2a-133">Check the **Behavior** tab and the **Endpoint Identity** settings in **General** tab to ensure they are valid.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="87b2a-134">送信先フォルダーの書き込みアクセス権が必要です。</span><span class="sxs-lookup"><span data-stu-id="87b2a-134">You must have write permissions to the destination folder.</span></span> <span data-ttu-id="87b2a-135">必要なアクセス権を取得するには、コンピューターの管理者に連絡してください。</span><span class="sxs-lookup"><span data-stu-id="87b2a-135">Contact the administrator of the machine to get these permissions.</span></span>