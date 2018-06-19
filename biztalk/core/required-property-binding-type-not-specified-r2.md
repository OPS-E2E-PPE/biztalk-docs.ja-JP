---
title: 必須のプロパティ バインディングの種類指定されていません (R2) |Microsoft ドキュメント
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
ms.openlocfilehash: 3a34de62453bd252e110edd0caf8a71996f25ae3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268810"
---
# <a name="required-property-binding-type-not-specified-r2"></a><span data-ttu-id="15594-102">必要な "バインドの種類" プロパティが指定されていません (R2)</span><span class="sxs-lookup"><span data-stu-id="15594-102">Required property binding type not specified (R2)</span></span>
## <a name="details"></a><span data-ttu-id="15594-103">詳細</span><span class="sxs-lookup"><span data-stu-id="15594-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="15594-104">製品名</span><span class="sxs-lookup"><span data-stu-id="15594-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="15594-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="15594-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="15594-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="15594-106">Event ID</span></span>|<span data-ttu-id="15594-107">0</span><span class="sxs-lookup"><span data-stu-id="15594-107">0</span></span>|  
|<span data-ttu-id="15594-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="15594-108">Event Source</span></span>|<span data-ttu-id="15594-109">0</span><span class="sxs-lookup"><span data-stu-id="15594-109">0</span></span>|  
|<span data-ttu-id="15594-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="15594-110">Component</span></span>|<span data-ttu-id="15594-111">0</span><span class="sxs-lookup"><span data-stu-id="15594-111">0</span></span>|  
|<span data-ttu-id="15594-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="15594-112">Symbolic Name</span></span>|<span data-ttu-id="15594-113">0</span><span class="sxs-lookup"><span data-stu-id="15594-113">0</span></span>|  
|<span data-ttu-id="15594-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="15594-114">Message Text</span></span>|<span data-ttu-id="15594-115">必須のプロパティ バインディングの種類が指定されていません</span><span class="sxs-lookup"><span data-stu-id="15594-115">Required property Binding Type not specified</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="15594-116">説明</span><span class="sxs-lookup"><span data-stu-id="15594-116">Explanation</span></span>  
 <span data-ttu-id="15594-117">WCF-Custom または WCF-CustomIsolated トランスポートを構成するときに、"バインドの種類" プロパティが設定されませんでした。</span><span class="sxs-lookup"><span data-stu-id="15594-117">You did not set the Binding Type property when configuring a WCF-Custom or a WCF-CustomIsolated transport.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="15594-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="15594-118">User Action</span></span>  
 <span data-ttu-id="15594-119">バインドの種類のプロパティを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="15594-119">Use the following procedure to configure the binding type property.</span></span>  
  
#### <a name="to-configure-the-binding-type-property"></a><span data-ttu-id="15594-120">バインドの種類のプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="15594-120">To configure the binding type property</span></span>  
  
1.  <span data-ttu-id="15594-121">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="15594-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="15594-122">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="15594-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="15594-123">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="15594-123">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="15594-124">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="15594-124">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="15594-125">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15594-125">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="15594-126">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="15594-126">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="15594-127">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="15594-127">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="15594-128">**WCF--[***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブです。</span><span class="sxs-lookup"><span data-stu-id="15594-128">In the **WCF--[***transport type***] Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="15594-129">値を指定して、**バインディングの種類** ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="15594-129">Specify a value in the **Binding Type** list.</span></span>  
  
 <span data-ttu-id="15594-130">バインドの構成の詳細については、次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15594-130">For additional information on configuring binding, see the following resources:</span></span>  
  
-   [<span data-ttu-id="15594-131">Wcf-customisolated 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="15594-131">How to Configure a WCF-CustomIsolated Receive Location</span></span>](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [<span data-ttu-id="15594-132">Wcf-custom 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="15594-132">How to Configure a WCF-Custom Receive Location</span></span>](../core/how-to-configure-a-wcf-custom-receive-location.md)  
  
-   [<span data-ttu-id="15594-133">Wcf-custom 送信ポートを構成する方法</span><span class="sxs-lookup"><span data-stu-id="15594-133">How to Configure a WCF-Custom Send Port</span></span>](../core/how-to-configure-a-wcf-custom-send-port.md)