---
title: XML 構成からサービス動作の構成要素を作成できません |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6732e5d2-bb4b-48ec-af59-467eede80f36
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e1668e7e9159ef7c922c68b54893c604b84c560
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017341"
---
# <a name="unable-to-create-service-behavior-configuration-element-from-xml-configuration"></a><span data-ttu-id="3fdb4-102">XML 構成からサービス動作の構成要素を作成できません</span><span class="sxs-lookup"><span data-stu-id="3fdb4-102">Unable to create service behavior configuration element from XML configuration</span></span>
## <a name="details"></a><span data-ttu-id="3fdb4-103">詳細</span><span class="sxs-lookup"><span data-stu-id="3fdb4-103">Details</span></span>  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="3fdb4-104">製品名</span><span class="sxs-lookup"><span data-stu-id="3fdb4-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="3fdb4-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="3fdb4-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="3fdb4-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="3fdb4-106">Event ID</span></span>     |                                         <span data-ttu-id="3fdb4-107">0</span><span class="sxs-lookup"><span data-stu-id="3fdb4-107">0</span></span>                                          |
|  <span data-ttu-id="3fdb4-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="3fdb4-108">Event Source</span></span>   |                                         <span data-ttu-id="3fdb4-109">0</span><span class="sxs-lookup"><span data-stu-id="3fdb4-109">0</span></span>                                          |
|    <span data-ttu-id="3fdb4-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3fdb4-110">Component</span></span>    |                                         <span data-ttu-id="3fdb4-111">0</span><span class="sxs-lookup"><span data-stu-id="3fdb4-111">0</span></span>                                          |
|  <span data-ttu-id="3fdb4-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="3fdb4-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="3fdb4-113">0</span><span class="sxs-lookup"><span data-stu-id="3fdb4-113">0</span></span>                                          |
|  <span data-ttu-id="3fdb4-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="3fdb4-114">Message Text</span></span>   |  <span data-ttu-id="3fdb4-115">XML 構成からサービス動作の構成要素を作成できません。</span><span class="sxs-lookup"><span data-stu-id="3fdb4-115">Unable to create service behavior configuration element from XML configuration.</span></span>   |

## <a name="explanation"></a><span data-ttu-id="3fdb4-116">説明</span><span class="sxs-lookup"><span data-stu-id="3fdb4-116">Explanation</span></span>  
 <span data-ttu-id="3fdb4-117">このエラーは、アダプターにサービス動作の構成が読み込まれなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="3fdb4-117">This error indicates the adapter did not load the service behavior configuration.</span></span> <span data-ttu-id="3fdb4-118">この状況は、主に WCF-Custom アダプターおよび WCF-CustomIsolated アダプターで発生します。</span><span class="sxs-lookup"><span data-stu-id="3fdb4-118">This situation occurs primarily with the WCF-Custom and WCF-CustomIsolated adapters.</span></span>  

## <a name="user-action"></a><span data-ttu-id="3fdb4-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="3fdb4-119">User Action</span></span>  
 <span data-ttu-id="3fdb4-120">サービス動作を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3fdb4-120">Use the following procedure to configure the service behavior.</span></span>  

#### <a name="to-configure-the-service-behavior"></a><span data-ttu-id="3fdb4-121">サービス動作を構成するには</span><span class="sxs-lookup"><span data-stu-id="3fdb4-121">To configure the service behavior</span></span>  

1. <span data-ttu-id="3fdb4-122">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="3fdb4-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="3fdb4-123">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="3fdb4-123">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="3fdb4-124">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="3fdb4-124">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="3fdb4-125">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="3fdb4-125">Right-click the transport name.</span></span>  

5. <span data-ttu-id="3fdb4-126">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3fdb4-126">Click **Properties**.</span></span>  

6. <span data-ttu-id="3fdb4-127">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="3fdb4-127">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="3fdb4-128">クリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="3fdb4-128">Click **Configure**.</span></span>  

8. <span data-ttu-id="3fdb4-129">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**動作**タブ。</span><span class="sxs-lookup"><span data-stu-id="3fdb4-129">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Behavior** tab.</span></span>  

9. <span data-ttu-id="3fdb4-130">**動作** セクションで、チェック、 **ServiceBehavior**構成します。</span><span class="sxs-lookup"><span data-stu-id="3fdb4-130">In the **Behavior** section, check the **ServiceBehavior** configuration.</span></span>
