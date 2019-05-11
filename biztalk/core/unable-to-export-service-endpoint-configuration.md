---
title: サービス エンドポイント構成をエクスポートできません |Microsoft Docs
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
ms.openlocfilehash: 47c43f08e264b04a8c45fcd8fd946de28d314b81
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292779"
---
# <a name="unable-to-export-service-endpoint-configuration"></a><span data-ttu-id="e10d5-102">サービス エンドポイント構成をエクスポートできません。</span><span class="sxs-lookup"><span data-stu-id="e10d5-102">Unable to export service endpoint configuration</span></span>
## <a name="details"></a><span data-ttu-id="e10d5-103">詳細</span><span class="sxs-lookup"><span data-stu-id="e10d5-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="e10d5-104">製品名</span><span class="sxs-lookup"><span data-stu-id="e10d5-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="e10d5-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="e10d5-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="e10d5-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e10d5-106">Event ID</span></span>     |                                         <span data-ttu-id="e10d5-107">0</span><span class="sxs-lookup"><span data-stu-id="e10d5-107">0</span></span>                                          |
|  <span data-ttu-id="e10d5-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="e10d5-108">Event Source</span></span>   |                                         <span data-ttu-id="e10d5-109">0</span><span class="sxs-lookup"><span data-stu-id="e10d5-109">0</span></span>                                          |
|    <span data-ttu-id="e10d5-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e10d5-110">Component</span></span>    |                                         <span data-ttu-id="e10d5-111">0</span><span class="sxs-lookup"><span data-stu-id="e10d5-111">0</span></span>                                          |
|  <span data-ttu-id="e10d5-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="e10d5-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="e10d5-113">0</span><span class="sxs-lookup"><span data-stu-id="e10d5-113">0</span></span>                                          |
|  <span data-ttu-id="e10d5-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="e10d5-114">Message Text</span></span>   |              <span data-ttu-id="e10d5-115">サービス エンドポイント構成をエクスポートすることができません"{0}"</span><span class="sxs-lookup"><span data-stu-id="e10d5-115">Unable to export service endpoint configuration to "{0}"</span></span>              |
  
## <a name="explanation"></a><span data-ttu-id="e10d5-116">説明</span><span class="sxs-lookup"><span data-stu-id="e10d5-116">Explanation</span></span>  
 <span data-ttu-id="e10d5-117">このエラーは、ユーザーは、先に書き込むアクセス許可がないことを示します。</span><span class="sxs-lookup"><span data-stu-id="e10d5-117">This error indicates the user may not have permission to write to the destination.</span></span> <span data-ttu-id="e10d5-118">または、必要なプロパティの一部が正しく指定されていないアドレス (URI)、およびバインドの種類など。</span><span class="sxs-lookup"><span data-stu-id="e10d5-118">Or some of the required properties were not correctly specified, such as Address (URI), and Binding Type.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e10d5-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="e10d5-119">User Action</span></span>  
 <span data-ttu-id="e10d5-120">エンドポイント id を構成するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="e10d5-120">Use the following procedure to configure the endpoint identity.</span></span>  
  
#### <a name="to-configure-the-endpoint-identity"></a><span data-ttu-id="e10d5-121">エンドポイント id を構成するには</span><span class="sxs-lookup"><span data-stu-id="e10d5-121">To configure the endpoint identity</span></span>  
  
1. <span data-ttu-id="e10d5-122">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="e10d5-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="e10d5-123">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="e10d5-123">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="e10d5-124">アプリケーションを見つけて、トランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="e10d5-124">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="e10d5-125">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="e10d5-125">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="e10d5-126">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e10d5-126">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="e10d5-127">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="e10d5-127">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="e10d5-128">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="e10d5-128">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="e10d5-129">Wcf **[**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。</span><span class="sxs-lookup"><span data-stu-id="e10d5-129">In the WCF **[**<em>transport type</em>**] Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="e10d5-130">コピー先のフォルダーへの書き込みが許可されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e10d5-130">Ensure that writing to the destination folder is permitted.</span></span>  
  
10. <span data-ttu-id="e10d5-131">チェック、**動作** タブと**エンドポイント Id**の設定、**全般** タブが有効であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e10d5-131">Check the **Behavior** tab and the **Endpoint Identity** settings in the **General** tab to ensure they are valid.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e10d5-132">目的のフォルダーに書き込みアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="e10d5-132">You must have write permissions to the destination folder.</span></span> <span data-ttu-id="e10d5-133">これらのアクセス許可を取得する、コンピューターの管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="e10d5-133">Contact the administrator of the machine to get these permissions.</span></span>