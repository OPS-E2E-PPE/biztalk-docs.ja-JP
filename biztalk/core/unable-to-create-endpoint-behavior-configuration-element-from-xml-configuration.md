---
title: XML 構成からエンドポイント動作の構成要素を作成できません |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 89d906a4-ea85-42d8-8e9e-0a3a7774bcd8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d1f014463bbbd12de856d20b37332c912b3ce22
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987243"
---
# <a name="unable-to-create-endpoint-behavior-configuration-element-from-xml-configuration"></a><span data-ttu-id="cd067-102">XML 構成からエンドポイント動作の構成要素を作成できません</span><span class="sxs-lookup"><span data-stu-id="cd067-102">Unable to create endpoint behavior configuration element from XML configuration</span></span>
## <a name="details"></a><span data-ttu-id="cd067-103">詳細</span><span class="sxs-lookup"><span data-stu-id="cd067-103">Details</span></span>  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="cd067-104">製品名</span><span class="sxs-lookup"><span data-stu-id="cd067-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="cd067-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="cd067-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="cd067-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="cd067-106">Event ID</span></span>     |                                         <span data-ttu-id="cd067-107">0</span><span class="sxs-lookup"><span data-stu-id="cd067-107">0</span></span>                                          |
|  <span data-ttu-id="cd067-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="cd067-108">Event Source</span></span>   |                                         <span data-ttu-id="cd067-109">0</span><span class="sxs-lookup"><span data-stu-id="cd067-109">0</span></span>                                          |
|    <span data-ttu-id="cd067-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="cd067-110">Component</span></span>    |                                         <span data-ttu-id="cd067-111">0</span><span class="sxs-lookup"><span data-stu-id="cd067-111">0</span></span>                                          |
|  <span data-ttu-id="cd067-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="cd067-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="cd067-113">0</span><span class="sxs-lookup"><span data-stu-id="cd067-113">0</span></span>                                          |
|  <span data-ttu-id="cd067-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="cd067-114">Message Text</span></span>   |  <span data-ttu-id="cd067-115">XML 構成からエンドポイント動作の構成要素を作成できません</span><span class="sxs-lookup"><span data-stu-id="cd067-115">Unable to create endpoint behavior configuration element from XML configuration</span></span>   |

## <a name="explanation"></a><span data-ttu-id="cd067-116">説明</span><span class="sxs-lookup"><span data-stu-id="cd067-116">Explanation</span></span>  
 <span data-ttu-id="cd067-117">このエラーは、アダプターにエンドポイント動作の構成が読み込まれなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="cd067-117">This error indicates the adapter did not load the endpoint behavior configuration.</span></span> <span data-ttu-id="cd067-118">この状況は、主に WCF-Custom アダプターおよび WCF-CustomIsolated アダプターで発生します。</span><span class="sxs-lookup"><span data-stu-id="cd067-118">This situation occurs primarily with the WCF-Custom and WCF-CustomIsolated adapters.</span></span>  

## <a name="user-action"></a><span data-ttu-id="cd067-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="cd067-119">User Action</span></span>  
 <span data-ttu-id="cd067-120">エンドポイント動作を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cd067-120">Use the following procedure to configure the endpoint behavior.</span></span>  

#### <a name="to-configure-the-endpoint-behavior"></a><span data-ttu-id="cd067-121">エンドポイント動作を構成するには</span><span class="sxs-lookup"><span data-stu-id="cd067-121">To configure the endpoint behavior</span></span>  

1. <span data-ttu-id="cd067-122">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="cd067-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="cd067-123">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="cd067-123">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="cd067-124">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="cd067-124">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="cd067-125">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="cd067-125">Right-click the transport name.</span></span>  

5. <span data-ttu-id="cd067-126">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd067-126">Click **Properties**.</span></span>  

6. <span data-ttu-id="cd067-127">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="cd067-127">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="cd067-128">クリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="cd067-128">Click **Configure**.</span></span>  

8. <span data-ttu-id="cd067-129">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**動作**タブ。</span><span class="sxs-lookup"><span data-stu-id="cd067-129">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Behavior** tab.</span></span>  

9. <span data-ttu-id="cd067-130">**動作** セクションで、チェック、 **EndpointBehavior**構成します。</span><span class="sxs-lookup"><span data-stu-id="cd067-130">In the **Behavior** section, check the **EndpointBehavior** configuration.</span></span>
