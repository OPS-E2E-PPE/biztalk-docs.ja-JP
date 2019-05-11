---
title: バインド要素を作成できません |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5b036833-12ba-463c-8df6-9d5e1ac26b6d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7abce71026f0780d25ba586feaa08f53bfa41962
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292859"
---
# <a name="unable-to-create-binding-element"></a><span data-ttu-id="7822a-102">バインド要素を作成できません</span><span class="sxs-lookup"><span data-stu-id="7822a-102">Unable to create binding element</span></span>
## <a name="details"></a><span data-ttu-id="7822a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="7822a-103">Details</span></span>  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="7822a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="7822a-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="7822a-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="7822a-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="7822a-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7822a-106">Event ID</span></span>     |                                         <span data-ttu-id="7822a-107">0</span><span class="sxs-lookup"><span data-stu-id="7822a-107">0</span></span>                                          |
|  <span data-ttu-id="7822a-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="7822a-108">Event Source</span></span>   |                                         <span data-ttu-id="7822a-109">0</span><span class="sxs-lookup"><span data-stu-id="7822a-109">0</span></span>                                          |
|    <span data-ttu-id="7822a-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7822a-110">Component</span></span>    |                                         <span data-ttu-id="7822a-111">0</span><span class="sxs-lookup"><span data-stu-id="7822a-111">0</span></span>                                          |
|  <span data-ttu-id="7822a-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="7822a-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="7822a-113">0</span><span class="sxs-lookup"><span data-stu-id="7822a-113">0</span></span>                                          |
|  <span data-ttu-id="7822a-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="7822a-114">Message Text</span></span>   |                 <span data-ttu-id="7822a-115">バインディングのバインド要素を作成できません"{0}</span><span class="sxs-lookup"><span data-stu-id="7822a-115">Unable to create binding element for binding "{0}</span></span>                  |

## <a name="explanation"></a><span data-ttu-id="7822a-116">説明</span><span class="sxs-lookup"><span data-stu-id="7822a-116">Explanation</span></span>  
 <span data-ttu-id="7822a-117">このエラーは、アダプターは、構成時に指定されたバインディングを作成できませんを示します。</span><span class="sxs-lookup"><span data-stu-id="7822a-117">This error indicates the adapter cannot create the binding specified in the configuration at runtime.</span></span> <span data-ttu-id="7822a-118">Wcf-custom および Wcf-customisolated アダプターで主に、このような状況が発生します。</span><span class="sxs-lookup"><span data-stu-id="7822a-118">This situation occurs primarily with the WCF-Custom and WCF-CustomIsolated adapters.</span></span>  

## <a name="user-action"></a><span data-ttu-id="7822a-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="7822a-119">User Action</span></span>  
 <span data-ttu-id="7822a-120">バインド要素が有効であることを確認するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="7822a-120">Use the following procedure to verify binding elements are valid.</span></span>  

#### <a name="to-verify-binding-elements"></a><span data-ttu-id="7822a-121">バインディング要素を確認するには</span><span class="sxs-lookup"><span data-stu-id="7822a-121">To verify binding elements</span></span>  

1. <span data-ttu-id="7822a-122">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="7822a-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="7822a-123">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="7822a-123">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="7822a-124">アプリケーションを見つけて、トランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="7822a-124">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="7822a-125">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="7822a-125">Right-click the transport name.</span></span>  

5. <span data-ttu-id="7822a-126">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7822a-126">Click **Properties**.</span></span>  

6. <span data-ttu-id="7822a-127">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="7822a-127">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="7822a-128">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="7822a-128">Click **Configure**.</span></span>  

8. <span data-ttu-id="7822a-129">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。</span><span class="sxs-lookup"><span data-stu-id="7822a-129">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Binding** tab.</span></span>  

9. <span data-ttu-id="7822a-130">構成で指定されたバインド要素が有効であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7822a-130">Ensure that the binding elements specified in the configuration are valid.</span></span>
