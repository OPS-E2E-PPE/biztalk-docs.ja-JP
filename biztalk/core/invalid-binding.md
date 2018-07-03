---
title: バインドが無効です |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e851f7f-ffc8-4f55-b06e-501a7f41b32a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 589d55d4ffccadf277f586104f8d5b9b1bf36b00
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996227"
---
# <a name="invalid-binding"></a><span data-ttu-id="c7625-102">バインドが無効です</span><span class="sxs-lookup"><span data-stu-id="c7625-102">Invalid binding</span></span>
## <a name="details"></a><span data-ttu-id="c7625-103">詳細</span><span class="sxs-lookup"><span data-stu-id="c7625-103">Details</span></span>  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="c7625-104">製品名</span><span class="sxs-lookup"><span data-stu-id="c7625-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="c7625-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c7625-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="c7625-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c7625-106">Event ID</span></span>     |                                         <span data-ttu-id="c7625-107">0</span><span class="sxs-lookup"><span data-stu-id="c7625-107">0</span></span>                                          |
|  <span data-ttu-id="c7625-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c7625-108">Event Source</span></span>   |                                         <span data-ttu-id="c7625-109">0</span><span class="sxs-lookup"><span data-stu-id="c7625-109">0</span></span>                                          |
|    <span data-ttu-id="c7625-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c7625-110">Component</span></span>    |                                         <span data-ttu-id="c7625-111">0</span><span class="sxs-lookup"><span data-stu-id="c7625-111">0</span></span>                                          |
|  <span data-ttu-id="c7625-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c7625-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="c7625-113">0</span><span class="sxs-lookup"><span data-stu-id="c7625-113">0</span></span>                                          |
|  <span data-ttu-id="c7625-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c7625-114">Message Text</span></span>   |                                  <span data-ttu-id="c7625-115">バインドが無効です</span><span class="sxs-lookup"><span data-stu-id="c7625-115">Invalid binding</span></span>                                   |

## <a name="explanation"></a><span data-ttu-id="c7625-116">説明</span><span class="sxs-lookup"><span data-stu-id="c7625-116">Explanation</span></span>  
 <span data-ttu-id="c7625-117">このエラーは、受信場所または送信ポートのバインディング構成に指定されたバインディングを、アダプターが作成できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="c7625-117">This error indicates the adapter cannot create the binding specified in the binding configuration of the receive location or send port.</span></span>  

## <a name="user-action"></a><span data-ttu-id="c7625-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c7625-118">User Action</span></span>  
 <span data-ttu-id="c7625-119">バインディング要素を確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c7625-119">Use the following procedure to verify binding elements.</span></span>  

#### <a name="to-verify-binding-elements"></a><span data-ttu-id="c7625-120">バインド要素を検証するには</span><span class="sxs-lookup"><span data-stu-id="c7625-120">To verify binding elements</span></span>  

1. <span data-ttu-id="c7625-121">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="c7625-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="c7625-122">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="c7625-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="c7625-123">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="c7625-123">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="c7625-124">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="c7625-124">Right-click the transport name.</span></span>  

5. <span data-ttu-id="c7625-125">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7625-125">Click **Properties**.</span></span>  

6. <span data-ttu-id="c7625-126">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="c7625-126">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="c7625-127">クリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="c7625-127">Click **Configure**.</span></span>  

8. <span data-ttu-id="c7625-128">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。</span><span class="sxs-lookup"><span data-stu-id="c7625-128">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Binding** tab.</span></span>  

9. <span data-ttu-id="c7625-129">構成に指定されているバインディング要素が有効であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c7625-129">Ensure the binding elements specified in the configuration are valid.</span></span>
