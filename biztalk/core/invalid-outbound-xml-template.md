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
ms.openlocfilehash: 1b0978c88e1392c506970b11bac9774c1f48eb5a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330766"
---
# <a name="invalid-outbound-xml-template"></a><span data-ttu-id="b71c4-102">送信 XML テンプレートが無効です</span><span class="sxs-lookup"><span data-stu-id="b71c4-102">Invalid outbound XML template</span></span>
## <a name="details"></a><span data-ttu-id="b71c4-103">詳細</span><span class="sxs-lookup"><span data-stu-id="b71c4-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="b71c4-104">製品名</span><span class="sxs-lookup"><span data-stu-id="b71c4-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="b71c4-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="b71c4-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="b71c4-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="b71c4-106">Event ID</span></span>     |                                         <span data-ttu-id="b71c4-107">0</span><span class="sxs-lookup"><span data-stu-id="b71c4-107">0</span></span>                                          |
|  <span data-ttu-id="b71c4-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="b71c4-108">Event Source</span></span>   |                                         <span data-ttu-id="b71c4-109">0</span><span class="sxs-lookup"><span data-stu-id="b71c4-109">0</span></span>                                          |
|    <span data-ttu-id="b71c4-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b71c4-110">Component</span></span>    |                                         <span data-ttu-id="b71c4-111">0</span><span class="sxs-lookup"><span data-stu-id="b71c4-111">0</span></span>                                          |
|  <span data-ttu-id="b71c4-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="b71c4-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="b71c4-113">0</span><span class="sxs-lookup"><span data-stu-id="b71c4-113">0</span></span>                                          |
|  <span data-ttu-id="b71c4-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="b71c4-114">Message Text</span></span>   |                           <span data-ttu-id="b71c4-115">送信 XML テンプレートが無効です</span><span class="sxs-lookup"><span data-stu-id="b71c4-115">Invalid outbound XML template</span></span>                            |
  
## <a name="explanation"></a><span data-ttu-id="b71c4-116">説明</span><span class="sxs-lookup"><span data-stu-id="b71c4-116">Explanation</span></span>  
 <span data-ttu-id="b71c4-117">複数の理由が考えられます。</span><span class="sxs-lookup"><span data-stu-id="b71c4-117">There could be multiple reasons.</span></span> <span data-ttu-id="b71c4-118">送信 WCF メッセージ本文のテンプレートは、有効な XML をできない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b71c4-118">The outbound WCF message body template may not be valid XML.</span></span> <span data-ttu-id="b71c4-119">指定されたエンコードに無効な文字に含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b71c4-119">It may contain invalid characters in the given encoding.</span></span> <span data-ttu-id="b71c4-120">ルート要素がない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b71c4-120">The root element may be missing.</span></span> <span data-ttu-id="b71c4-121">ルート レベルのデータは、有効でない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b71c4-121">The data at the root level may be invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b71c4-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="b71c4-122">User Action</span></span>  
 <span data-ttu-id="b71c4-123">テンプレート式に有効な XML コードがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b71c4-123">Ensure that template expression has valid XML code.</span></span> <span data-ttu-id="b71c4-124">無効な文字が含まれていないことと、1 つだけのルート要素があることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b71c4-124">Ensure that It doesn’t contain any invalid characters and that there is only one root element.</span></span>  
  
1. <span data-ttu-id="b71c4-125">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="b71c4-125">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="b71c4-126">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="b71c4-126">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="b71c4-127">アプリケーションを見つけて、トランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="b71c4-127">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="b71c4-128">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="b71c4-128">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="b71c4-129">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b71c4-129">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="b71c4-130">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="b71c4-130">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="b71c4-131">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="b71c4-131">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="b71c4-132">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**メッセージ**タブ。</span><span class="sxs-lookup"><span data-stu-id="b71c4-132">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Messages** tab.</span></span>  
  
9. <span data-ttu-id="b71c4-133">**送信 WCF メッセージ本文**セクションで、**テンプレート--テンプレートで指定されたコンテンツ**します。</span><span class="sxs-lookup"><span data-stu-id="b71c4-133">In the **Outbound WCF message body** section, select **Template--content specified by template**.</span></span>  
  
10. <span data-ttu-id="b71c4-134">**XML**テキスト ボックスに、XML コードが有効であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b71c4-134">In the **XML** text box, ensure that the XML code is valid.</span></span>  
  
    <span data-ttu-id="b71c4-135">テンプレートの詳細については、の次のリソースを参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。</span><span class="sxs-lookup"><span data-stu-id="b71c4-135">For additional information on templates, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="b71c4-136">WCF アダプターのメッセージ本文の指定</span><span class="sxs-lookup"><span data-stu-id="b71c4-136">Specifying the Message Body for the WCF Adapters</span></span>](../core/specifying-the-message-body-for-the-wcf-adapters.md)