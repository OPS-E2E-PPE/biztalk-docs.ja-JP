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
ms.openlocfilehash: b2b294b67f066c0c3ff61232afd1aa81382363c1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292835"
---
# <a name="unable-to-create-endpoint-behavior-configuration-element-from-xml-configuration"></a><span data-ttu-id="51c00-102">XML 構成からエンドポイント動作の構成要素を作成できません。</span><span class="sxs-lookup"><span data-stu-id="51c00-102">Unable to create endpoint behavior configuration element from XML configuration</span></span>
## <a name="details"></a><span data-ttu-id="51c00-103">詳細</span><span class="sxs-lookup"><span data-stu-id="51c00-103">Details</span></span>  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="51c00-104">製品名</span><span class="sxs-lookup"><span data-stu-id="51c00-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="51c00-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="51c00-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="51c00-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="51c00-106">Event ID</span></span>     |                                         <span data-ttu-id="51c00-107">0</span><span class="sxs-lookup"><span data-stu-id="51c00-107">0</span></span>                                          |
|  <span data-ttu-id="51c00-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="51c00-108">Event Source</span></span>   |                                         <span data-ttu-id="51c00-109">0</span><span class="sxs-lookup"><span data-stu-id="51c00-109">0</span></span>                                          |
|    <span data-ttu-id="51c00-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="51c00-110">Component</span></span>    |                                         <span data-ttu-id="51c00-111">0</span><span class="sxs-lookup"><span data-stu-id="51c00-111">0</span></span>                                          |
|  <span data-ttu-id="51c00-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="51c00-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="51c00-113">0</span><span class="sxs-lookup"><span data-stu-id="51c00-113">0</span></span>                                          |
|  <span data-ttu-id="51c00-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="51c00-114">Message Text</span></span>   |  <span data-ttu-id="51c00-115">XML 構成からエンドポイント動作の構成要素を作成できません。</span><span class="sxs-lookup"><span data-stu-id="51c00-115">Unable to create endpoint behavior configuration element from XML configuration</span></span>   |

## <a name="explanation"></a><span data-ttu-id="51c00-116">説明</span><span class="sxs-lookup"><span data-stu-id="51c00-116">Explanation</span></span>  
 <span data-ttu-id="51c00-117">このエラーは、アダプターでは、エンドポイント動作の構成は読み込まれませんでしたを示します。</span><span class="sxs-lookup"><span data-stu-id="51c00-117">This error indicates the adapter did not load the endpoint behavior configuration.</span></span> <span data-ttu-id="51c00-118">Wcf-custom および Wcf-customisolated アダプターで主に、このような状況が発生します。</span><span class="sxs-lookup"><span data-stu-id="51c00-118">This situation occurs primarily with the WCF-Custom and WCF-CustomIsolated adapters.</span></span>  

## <a name="user-action"></a><span data-ttu-id="51c00-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="51c00-119">User Action</span></span>  
 <span data-ttu-id="51c00-120">エンドポイントの動作を構成するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="51c00-120">Use the following procedure to configure the endpoint behavior.</span></span>  

#### <a name="to-configure-the-endpoint-behavior"></a><span data-ttu-id="51c00-121">エンドポイントの動作を構成するには</span><span class="sxs-lookup"><span data-stu-id="51c00-121">To configure the endpoint behavior</span></span>  

1. <span data-ttu-id="51c00-122">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="51c00-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="51c00-123">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="51c00-123">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="51c00-124">アプリケーションを見つけて、トランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="51c00-124">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="51c00-125">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="51c00-125">Right-click the transport name.</span></span>  

5. <span data-ttu-id="51c00-126">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51c00-126">Click **Properties**.</span></span>  

6. <span data-ttu-id="51c00-127">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="51c00-127">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="51c00-128">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="51c00-128">Click **Configure**.</span></span>  

8. <span data-ttu-id="51c00-129">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**動作**タブ。</span><span class="sxs-lookup"><span data-stu-id="51c00-129">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Behavior** tab.</span></span>  

9. <span data-ttu-id="51c00-130">**動作** セクションで、チェック、 **EndpointBehavior**構成します。</span><span class="sxs-lookup"><span data-stu-id="51c00-130">In the **Behavior** section, check the **EndpointBehavior** configuration.</span></span>
