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
ms.openlocfilehash: f7910cf4c6e16d5af75e49bb829f1418a5e1455c
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528213"
---
# <a name="cannot-create-binding"></a><span data-ttu-id="a9b03-102">バインドを作成できません</span><span class="sxs-lookup"><span data-stu-id="a9b03-102">Cannot create binding</span></span>
## <a name="details"></a><span data-ttu-id="a9b03-103">詳細</span><span class="sxs-lookup"><span data-stu-id="a9b03-103">Details</span></span>  
  
|                 |                                                                                                                                                |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="a9b03-104">製品名</span><span class="sxs-lookup"><span data-stu-id="a9b03-104">Product Name</span></span>   |                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                               |
| <span data-ttu-id="a9b03-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="a9b03-105">Product Version</span></span> |                                           [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                           |
|    <span data-ttu-id="a9b03-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="a9b03-106">Event ID</span></span>     |                                                                       <span data-ttu-id="a9b03-107">0</span><span class="sxs-lookup"><span data-stu-id="a9b03-107">0</span></span>                                                                        |
|  <span data-ttu-id="a9b03-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="a9b03-108">Event Source</span></span>   |                                                                       <span data-ttu-id="a9b03-109">0</span><span class="sxs-lookup"><span data-stu-id="a9b03-109">0</span></span>                                                                        |
|    <span data-ttu-id="a9b03-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a9b03-110">Component</span></span>    |                                                                       <span data-ttu-id="a9b03-111">0</span><span class="sxs-lookup"><span data-stu-id="a9b03-111">0</span></span>                                                                        |
|  <span data-ttu-id="a9b03-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="a9b03-112">Symbolic Name</span></span>  |                                                                       <span data-ttu-id="a9b03-113">0</span><span class="sxs-lookup"><span data-stu-id="a9b03-113">0</span></span>                                                                        |
|  <span data-ttu-id="a9b03-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="a9b03-114">Message Text</span></span>   | <span data-ttu-id="a9b03-115">バインドの種類が指定されていないために、バインドを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="a9b03-115">Cannot create binding since binding type was not specified.</span></span> <span data-ttu-id="a9b03-116">"BasicHttpBinding"、"wsHttpBinding"または"customBinding のようなバインドの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="a9b03-116">Specify a binding type like "basicHttpBinding", "wsHttpBinding", or "customBinding</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="a9b03-117">説明</span><span class="sxs-lookup"><span data-stu-id="a9b03-117">Explanation</span></span>  
 <span data-ttu-id="a9b03-118">BindingType プロパティを Wcf-custom または Wcf-customisolated トランスポートを構成した後、コードで設定されませんでした。</span><span class="sxs-lookup"><span data-stu-id="a9b03-118">You did not set the BindingType property in the code after configuring a WCF-Custom or a WCF-CustomIsolated transport.</span></span> <span data-ttu-id="a9b03-119">または、他のコード パスで問題になります。</span><span class="sxs-lookup"><span data-stu-id="a9b03-119">Or the problem could be in other code paths.</span></span> <span data-ttu-id="a9b03-120">値は、バインド設定のユーザー インターフェイスが必要です。</span><span class="sxs-lookup"><span data-stu-id="a9b03-120">You must have a value in the user interface for binding setting.</span></span> <span data-ttu-id="a9b03-121">構成を確認し、受信場所のプロパティ 領域で、ドロップダウン リストからバインドの種類が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a9b03-121">Review your configuration and ensure that a binding type was chosen from the drop-down list in the receive location Properties area.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a9b03-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="a9b03-122">User Action</span></span>  
 <span data-ttu-id="a9b03-123">このエラーを解決するには、Wcf-custom または Wcf-customisolated トランスポートを構成するコードを確認します。</span><span class="sxs-lookup"><span data-stu-id="a9b03-123">To resolve this error, review the code configuring the WCF-Custom or WCF-CustomIsolated transport.</span></span> <span data-ttu-id="a9b03-124">いることを確認、 **BindingType**プロパティの XML データで、 **TransportTypeData** ITransportInfo インターフェイスのプロパティが適切に設定します。</span><span class="sxs-lookup"><span data-stu-id="a9b03-124">Ensure that the **BindingType** property in the XML data for the **TransportTypeData** property of the ITransportInfo interface is set properly.</span></span>  
  
 <span data-ttu-id="a9b03-125">また、ようにバインドの種類を指定**basicHttpBinding**、 **wsHttpBinding**、または**customBinding**します。</span><span class="sxs-lookup"><span data-stu-id="a9b03-125">Also, specify a binding type like **basicHttpBinding**, **wsHttpBinding**, or **customBinding**.</span></span>  
  
1. <span data-ttu-id="a9b03-126">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="a9b03-126">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="a9b03-127">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="a9b03-127">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="a9b03-128">アプリケーションを見つけて、トランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="a9b03-128">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="a9b03-129">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="a9b03-129">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="a9b03-130">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a9b03-130">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="a9b03-131">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="a9b03-131">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="a9b03-132">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="a9b03-132">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="a9b03-133">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。</span><span class="sxs-lookup"><span data-stu-id="a9b03-133">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="a9b03-134">値が指定されていることを確認、**バインドの種類**一覧。</span><span class="sxs-lookup"><span data-stu-id="a9b03-134">Ensure that a value is specified in the **Binding Type** list.</span></span>  
  
   <span data-ttu-id="a9b03-135">バインディングの構成の詳細については、の次のリソースを参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。</span><span class="sxs-lookup"><span data-stu-id="a9b03-135">For additional information on configuring binding, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="a9b03-136">Wcf-customisolated 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="a9b03-136">How to Configure a WCF-CustomIsolated Receive Location</span></span>](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [<span data-ttu-id="a9b03-137">Wcf-custom 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="a9b03-137">How to Configure a WCF-Custom Receive Location</span></span>](../core/how-to-configure-a-wcf-custom-receive-location.md)  
  
-   [<span data-ttu-id="a9b03-138">Wcf-custom 送信ポートを構成する方法</span><span class="sxs-lookup"><span data-stu-id="a9b03-138">How to Configure a WCF-Custom Send Port</span></span>](../core/how-to-configure-a-wcf-custom-send-port.md)