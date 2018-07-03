---
title: Id の作成に失敗しました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 531f1057-1b6d-40ae-bf2f-a36baf4e0341
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 203257b261bba176b0a768da8242dad45366a923
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998115"
---
# <a name="failed-to-create-identity"></a><span data-ttu-id="52a73-102">ID を作成できませんでした</span><span class="sxs-lookup"><span data-stu-id="52a73-102">Failed to create identity</span></span>
## <a name="details"></a><span data-ttu-id="52a73-103">詳細</span><span class="sxs-lookup"><span data-stu-id="52a73-103">Details</span></span>  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="52a73-104">製品名</span><span class="sxs-lookup"><span data-stu-id="52a73-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="52a73-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="52a73-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="52a73-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="52a73-106">Event ID</span></span>     |                                         <span data-ttu-id="52a73-107">0</span><span class="sxs-lookup"><span data-stu-id="52a73-107">0</span></span>                                          |
|  <span data-ttu-id="52a73-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="52a73-108">Event Source</span></span>   |                                         <span data-ttu-id="52a73-109">0</span><span class="sxs-lookup"><span data-stu-id="52a73-109">0</span></span>                                          |
|    <span data-ttu-id="52a73-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="52a73-110">Component</span></span>    |                                         <span data-ttu-id="52a73-111">0</span><span class="sxs-lookup"><span data-stu-id="52a73-111">0</span></span>                                          |
|  <span data-ttu-id="52a73-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="52a73-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="52a73-113">0</span><span class="sxs-lookup"><span data-stu-id="52a73-113">0</span></span>                                          |
|  <span data-ttu-id="52a73-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="52a73-114">Message Text</span></span>   |      <span data-ttu-id="52a73-115">このエラーは、アダプターがエンドポイント ID を作成できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="52a73-115">This error indicates the adapter failed to create the endpoint identity.</span></span>      |

## <a name="explanation"></a><span data-ttu-id="52a73-116">説明</span><span class="sxs-lookup"><span data-stu-id="52a73-116">Explanation</span></span>  
 <span data-ttu-id="52a73-117">このエラーは、アダプターがエンドポイント ID を作成できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="52a73-117">This error indicates the adapter failed to create the endpoint identity.</span></span>  

## <a name="user-action"></a><span data-ttu-id="52a73-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="52a73-118">User Action</span></span>  
 <span data-ttu-id="52a73-119">エンドポイント ID を構成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="52a73-119">Use the following procedure to configure the endpoint identity.</span></span>  

#### <a name="to-configure-the-endpoint-identity"></a><span data-ttu-id="52a73-120">エンドポイント ID を構成するには</span><span class="sxs-lookup"><span data-stu-id="52a73-120">To configure the endpoint identity</span></span>  

1. <span data-ttu-id="52a73-121">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="52a73-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="52a73-122">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="52a73-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="52a73-123">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="52a73-123">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="52a73-124">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="52a73-124">Right-click the transport name.</span></span>  

5. <span data-ttu-id="52a73-125">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52a73-125">Click **Properties**.</span></span>  

6. <span data-ttu-id="52a73-126">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="52a73-126">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="52a73-127">クリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="52a73-127">Click **Configure**.</span></span>  

8. <span data-ttu-id="52a73-128">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブ。</span><span class="sxs-lookup"><span data-stu-id="52a73-128">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **General** tab.</span></span>  

9. <span data-ttu-id="52a73-129">**エンドポイント Id**セクションで、**編集**します。</span><span class="sxs-lookup"><span data-stu-id="52a73-129">In the **Endpoint Identity** section, click **Edit**.</span></span>  

10. <span data-ttu-id="52a73-130">**Id エディター**  ダイアログ ボックスで、設定が有効であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="52a73-130">In the **Identity Editor** dialog box, ensure that the settings are valid.</span></span>
