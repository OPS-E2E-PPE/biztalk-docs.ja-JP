---
title: 必須のプロパティ バインド種類が指定されていません (R2) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c8e45783-6454-44e2-867e-e30092725f51
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e959b7e3e0a48dea0d18a73a898d2c39bfd576e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267597"
---
# <a name="required-property-binding-type-not-specified-r2"></a><span data-ttu-id="970b5-102">必要なプロパティのバインドの種類が指定されていません (R2)</span><span class="sxs-lookup"><span data-stu-id="970b5-102">Required property binding type not specified (R2)</span></span>
## <a name="details"></a><span data-ttu-id="970b5-103">詳細</span><span class="sxs-lookup"><span data-stu-id="970b5-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="970b5-104">製品名</span><span class="sxs-lookup"><span data-stu-id="970b5-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="970b5-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="970b5-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="970b5-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="970b5-106">Event ID</span></span>     |                                         <span data-ttu-id="970b5-107">0</span><span class="sxs-lookup"><span data-stu-id="970b5-107">0</span></span>                                          |
|  <span data-ttu-id="970b5-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="970b5-108">Event Source</span></span>   |                                         <span data-ttu-id="970b5-109">0</span><span class="sxs-lookup"><span data-stu-id="970b5-109">0</span></span>                                          |
|    <span data-ttu-id="970b5-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="970b5-110">Component</span></span>    |                                         <span data-ttu-id="970b5-111">0</span><span class="sxs-lookup"><span data-stu-id="970b5-111">0</span></span>                                          |
|  <span data-ttu-id="970b5-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="970b5-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="970b5-113">0</span><span class="sxs-lookup"><span data-stu-id="970b5-113">0</span></span>                                          |
|  <span data-ttu-id="970b5-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="970b5-114">Message Text</span></span>   |                    <span data-ttu-id="970b5-115">必要なプロパティが指定されていないバインドの種類</span><span class="sxs-lookup"><span data-stu-id="970b5-115">Required property Binding Type not specified</span></span>                    |
  
## <a name="explanation"></a><span data-ttu-id="970b5-116">説明</span><span class="sxs-lookup"><span data-stu-id="970b5-116">Explanation</span></span>  
 <span data-ttu-id="970b5-117">Wcf-custom または Wcf-customisolated トランスポートを構成するときに、バインドの種類プロパティは設定されませんでした。</span><span class="sxs-lookup"><span data-stu-id="970b5-117">You did not set the Binding Type property when configuring a WCF-Custom or a WCF-CustomIsolated transport.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="970b5-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="970b5-118">User Action</span></span>  
 <span data-ttu-id="970b5-119">バインドの種類のプロパティを構成するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="970b5-119">Use the following procedure to configure the binding type property.</span></span>  
  
#### <a name="to-configure-the-binding-type-property"></a><span data-ttu-id="970b5-120">バインドの種類のプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="970b5-120">To configure the binding type property</span></span>  
  
1. <span data-ttu-id="970b5-121">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="970b5-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="970b5-122">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="970b5-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="970b5-123">アプリケーションを見つけて、トランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="970b5-123">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="970b5-124">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="970b5-124">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="970b5-125">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="970b5-125">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="970b5-126">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="970b5-126">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="970b5-127">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="970b5-127">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="970b5-128">**WCF--[**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。</span><span class="sxs-lookup"><span data-stu-id="970b5-128">In the **WCF--[**<em>transport type</em>**] Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="970b5-129">値を指定、**バインドの種類**一覧。</span><span class="sxs-lookup"><span data-stu-id="970b5-129">Specify a value in the **Binding Type** list.</span></span>  
  
   <span data-ttu-id="970b5-130">バインディングの構成の詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="970b5-130">For additional information on configuring binding, see the following resources:</span></span>  
  
-   [<span data-ttu-id="970b5-131">Wcf-customisolated 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="970b5-131">How to Configure a WCF-CustomIsolated Receive Location</span></span>](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [<span data-ttu-id="970b5-132">Wcf-custom 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="970b5-132">How to Configure a WCF-Custom Receive Location</span></span>](../core/how-to-configure-a-wcf-custom-receive-location.md)  
  
-   [<span data-ttu-id="970b5-133">Wcf-custom 送信ポートを構成する方法</span><span class="sxs-lookup"><span data-stu-id="970b5-133">How to Configure a WCF-Custom Send Port</span></span>](../core/how-to-configure-a-wcf-custom-send-port.md)