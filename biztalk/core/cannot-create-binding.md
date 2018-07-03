---
title: バインディングを作成することはできません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fbe1bd54-6031-4f90-a445-c1647b382a1a
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 567b3d88ced85f427fde492cd3e68cefaaf47394
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999205"
---
# <a name="cannot-create-binding"></a><span data-ttu-id="68285-102">バインドを作成できません</span><span class="sxs-lookup"><span data-stu-id="68285-102">Cannot create binding</span></span>
## <a name="details"></a><span data-ttu-id="68285-103">詳細</span><span class="sxs-lookup"><span data-stu-id="68285-103">Details</span></span>  
  
|                 |                                                                                                                                                |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="68285-104">製品名</span><span class="sxs-lookup"><span data-stu-id="68285-104">Product Name</span></span>   |                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                               |
| <span data-ttu-id="68285-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="68285-105">Product Version</span></span> |                                           [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                           |
|    <span data-ttu-id="68285-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="68285-106">Event ID</span></span>     |                                                                       <span data-ttu-id="68285-107">0</span><span class="sxs-lookup"><span data-stu-id="68285-107">0</span></span>                                                                        |
|  <span data-ttu-id="68285-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="68285-108">Event Source</span></span>   |                                                                       <span data-ttu-id="68285-109">0</span><span class="sxs-lookup"><span data-stu-id="68285-109">0</span></span>                                                                        |
|    <span data-ttu-id="68285-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="68285-110">Component</span></span>    |                                                                       <span data-ttu-id="68285-111">0</span><span class="sxs-lookup"><span data-stu-id="68285-111">0</span></span>                                                                        |
|  <span data-ttu-id="68285-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="68285-112">Symbolic Name</span></span>  |                                                                       <span data-ttu-id="68285-113">0</span><span class="sxs-lookup"><span data-stu-id="68285-113">0</span></span>                                                                        |
|  <span data-ttu-id="68285-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="68285-114">Message Text</span></span>   | <span data-ttu-id="68285-115">バインドの種類が指定されていないため、バインドを作成できません。</span><span class="sxs-lookup"><span data-stu-id="68285-115">Cannot create binding since binding type was not specified.</span></span> <span data-ttu-id="68285-116">"basicHttpBinding"、"wsHttpBinding"、または "customBinding" のようなバインドの種類を指定してください。</span><span class="sxs-lookup"><span data-stu-id="68285-116">Specify a binding type like "basicHttpBinding", "wsHttpBinding", or "customBinding</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="68285-117">説明</span><span class="sxs-lookup"><span data-stu-id="68285-117">Explanation</span></span>  
 <span data-ttu-id="68285-118">WCF-Custom または WCF-CustomIsolated トランスポートを構成した後に、BindingType プロパティが設定されませんでした。</span><span class="sxs-lookup"><span data-stu-id="68285-118">You did not set the BindingType property in the code after configuring a WCF-Custom or a WCF-CustomIsolated transport.</span></span> <span data-ttu-id="68285-119">または、他のコード パスに問題がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="68285-119">Or the problem could be in other code paths.</span></span> <span data-ttu-id="68285-120">バインド設定のユーザー インターフェイスで値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68285-120">You must have a value in the user interface for binding setting.</span></span> <span data-ttu-id="68285-121">構成を見直し、受信場所のプロパティ領域のドロップダウン リストからバインドの種類を選択したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="68285-121">Review your configuration and ensure that a binding type was chosen from the drop-down list in the receive location Properties area.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="68285-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="68285-122">User Action</span></span>  
 <span data-ttu-id="68285-123">このエラーを解決するには、WCF-Custom または WCF-CustomIsolated トランスポートを構成するコードを見直します。</span><span class="sxs-lookup"><span data-stu-id="68285-123">To resolve this error, review the code configuring the WCF-Custom or WCF-CustomIsolated transport.</span></span> <span data-ttu-id="68285-124">いることを確認、 **BindingType**プロパティの XML データで、 **TransportTypeData** ITransportInfo インターフェイスのプロパティが適切に設定します。</span><span class="sxs-lookup"><span data-stu-id="68285-124">Ensure that the **BindingType** property in the XML data for the **TransportTypeData** property of the ITransportInfo interface is set properly.</span></span>  
  
 <span data-ttu-id="68285-125">また、ようにバインドの種類を指定**basicHttpBinding**、 **wsHttpBinding**、または**customBinding**します。</span><span class="sxs-lookup"><span data-stu-id="68285-125">Also, specify a binding type like **basicHttpBinding**, **wsHttpBinding**, or **customBinding**.</span></span>  
  
1. <span data-ttu-id="68285-126">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="68285-126">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="68285-127">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="68285-127">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="68285-128">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="68285-128">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="68285-129">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="68285-129">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="68285-130">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68285-130">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="68285-131">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="68285-131">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="68285-132">クリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="68285-132">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="68285-133">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。</span><span class="sxs-lookup"><span data-stu-id="68285-133">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="68285-134">値が指定されていることを確認、**バインドの種類**一覧。</span><span class="sxs-lookup"><span data-stu-id="68285-134">Ensure that a value is specified in the **Binding Type** list.</span></span>  
  
   <span data-ttu-id="68285-135">バインド構成の詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプで次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68285-135">For additional information on configuring binding, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="68285-136">Wcf-customisolated 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="68285-136">How to Configure a WCF-CustomIsolated Receive Location</span></span>](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [<span data-ttu-id="68285-137">Wcf-custom 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="68285-137">How to Configure a WCF-Custom Receive Location</span></span>](../core/how-to-configure-a-wcf-custom-receive-location.md)  
  
-   [<span data-ttu-id="68285-138">Wcf-custom 送信ポートを構成する方法</span><span class="sxs-lookup"><span data-stu-id="68285-138">How to Configure a WCF-Custom Send Port</span></span>](../core/how-to-configure-a-wcf-custom-send-port.md)