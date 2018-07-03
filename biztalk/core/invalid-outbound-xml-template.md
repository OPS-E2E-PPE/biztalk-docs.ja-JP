---
title: 送信 XML テンプレートが無効な |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f29bb60-8c04-4921-84bf-c629540a1c83
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 92b48f40ad758d61b802ed7e514e2e687a005842
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011907"
---
# <a name="invalid-outbound-xml-template"></a><span data-ttu-id="905df-102">送信 XML テンプレートが無効です</span><span class="sxs-lookup"><span data-stu-id="905df-102">Invalid outbound XML template</span></span>
## <a name="details"></a><span data-ttu-id="905df-103">詳細</span><span class="sxs-lookup"><span data-stu-id="905df-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="905df-104">製品名</span><span class="sxs-lookup"><span data-stu-id="905df-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="905df-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="905df-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="905df-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="905df-106">Event ID</span></span>     |                                         <span data-ttu-id="905df-107">0</span><span class="sxs-lookup"><span data-stu-id="905df-107">0</span></span>                                          |
|  <span data-ttu-id="905df-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="905df-108">Event Source</span></span>   |                                         <span data-ttu-id="905df-109">0</span><span class="sxs-lookup"><span data-stu-id="905df-109">0</span></span>                                          |
|    <span data-ttu-id="905df-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="905df-110">Component</span></span>    |                                         <span data-ttu-id="905df-111">0</span><span class="sxs-lookup"><span data-stu-id="905df-111">0</span></span>                                          |
|  <span data-ttu-id="905df-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="905df-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="905df-113">0</span><span class="sxs-lookup"><span data-stu-id="905df-113">0</span></span>                                          |
|  <span data-ttu-id="905df-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="905df-114">Message Text</span></span>   |                           <span data-ttu-id="905df-115">送信 XML テンプレートが無効です</span><span class="sxs-lookup"><span data-stu-id="905df-115">Invalid outbound XML template</span></span>                            |
  
## <a name="explanation"></a><span data-ttu-id="905df-116">説明</span><span class="sxs-lookup"><span data-stu-id="905df-116">Explanation</span></span>  
 <span data-ttu-id="905df-117">複数の理由があります。</span><span class="sxs-lookup"><span data-stu-id="905df-117">There could be multiple reasons.</span></span> <span data-ttu-id="905df-118">送信 WCF メッセージ本文テンプレートが有効な XML ではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="905df-118">The outbound WCF message body template may not be valid XML.</span></span> <span data-ttu-id="905df-119">指定したエンコーディングでは無効な文字が含まれる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="905df-119">It may contain invalid characters in the given encoding.</span></span> <span data-ttu-id="905df-120">ルート要素が欠落している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="905df-120">The root element may be missing.</span></span> <span data-ttu-id="905df-121">ルート レベルのデータが無効な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="905df-121">The data at the root level may be invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="905df-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="905df-122">User Action</span></span>  
 <span data-ttu-id="905df-123">テンプレートの表現を有効な XML コードにします。</span><span class="sxs-lookup"><span data-stu-id="905df-123">Ensure that template expression has valid XML code.</span></span> <span data-ttu-id="905df-124">無効な文字が含まれないこと、およびルート要素が 1 つのみであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="905df-124">Ensure that It doesn’t contain any invalid characters and that there is only one root element.</span></span>  
  
1. <span data-ttu-id="905df-125">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="905df-125">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="905df-126">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="905df-126">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="905df-127">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="905df-127">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="905df-128">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="905df-128">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="905df-129">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="905df-129">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="905df-130">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="905df-130">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="905df-131">クリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="905df-131">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="905df-132">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**メッセージ**タブ。</span><span class="sxs-lookup"><span data-stu-id="905df-132">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Messages** tab.</span></span>  
  
9. <span data-ttu-id="905df-133">**送信 WCF メッセージ本文**セクションで、**テンプレート--テンプレートで指定されたコンテンツ**します。</span><span class="sxs-lookup"><span data-stu-id="905df-133">In the **Outbound WCF message body** section, select **Template--content specified by template**.</span></span>  
  
10. <span data-ttu-id="905df-134">**XML**テキスト ボックスに、XML コードが有効であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="905df-134">In the **XML** text box, ensure that the XML code is valid.</span></span>  
  
    <span data-ttu-id="905df-135">テンプレートの詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="905df-135">For additional information on templates, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="905df-136">WCF アダプターのメッセージ本文の指定</span><span class="sxs-lookup"><span data-stu-id="905df-136">Specifying the Message Body for the WCF Adapters</span></span>](../core/specifying-the-message-body-for-the-wcf-adapters.md)