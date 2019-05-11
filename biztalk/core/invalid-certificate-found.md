---
title: 無効な証明書が見つかりました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1b3a9ae8-a9d7-4025-bacd-443e136ff980
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9194267eecdbf2247155df297dffeedbf2cac3a8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381360"
---
# <a name="invalid-certificate-found"></a><span data-ttu-id="8046e-102">無効な証明書が見つかりました</span><span class="sxs-lookup"><span data-stu-id="8046e-102">Invalid certificate found</span></span>
## <a name="details"></a><span data-ttu-id="8046e-103">詳細</span><span class="sxs-lookup"><span data-stu-id="8046e-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="8046e-104">製品名</span><span class="sxs-lookup"><span data-stu-id="8046e-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="8046e-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="8046e-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="8046e-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="8046e-106">Event ID</span></span>     |                                         <span data-ttu-id="8046e-107">0</span><span class="sxs-lookup"><span data-stu-id="8046e-107">0</span></span>                                          |
|  <span data-ttu-id="8046e-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="8046e-108">Event Source</span></span>   |                                         <span data-ttu-id="8046e-109">0</span><span class="sxs-lookup"><span data-stu-id="8046e-109">0</span></span>                                          |
|    <span data-ttu-id="8046e-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8046e-110">Component</span></span>    |                                         <span data-ttu-id="8046e-111">0</span><span class="sxs-lookup"><span data-stu-id="8046e-111">0</span></span>                                          |
|  <span data-ttu-id="8046e-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="8046e-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="8046e-113">0</span><span class="sxs-lookup"><span data-stu-id="8046e-113">0</span></span>                                          |
|  <span data-ttu-id="8046e-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="8046e-114">Message Text</span></span>   |                             <span data-ttu-id="8046e-115">無効な証明書が見つかりました</span><span class="sxs-lookup"><span data-stu-id="8046e-115">Invalid certificate found</span></span>                              |
  
## <a name="explanation"></a><span data-ttu-id="8046e-116">説明</span><span class="sxs-lookup"><span data-stu-id="8046e-116">Explanation</span></span>  
 <span data-ttu-id="8046e-117">WCF トランスポートの有効な証明書を提供しませんでした。</span><span class="sxs-lookup"><span data-stu-id="8046e-117">You did not provide a valid certificate for a WCF transport.</span></span>  

#### <a name="user-action"></a><span data-ttu-id="8046e-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="8046e-118">User Action</span></span>
<span data-ttu-id="8046e-119">証明書を追加します。</span><span class="sxs-lookup"><span data-stu-id="8046e-119">Add a certificate.</span></span> 
  
## <a name="add-a-certificate"></a><span data-ttu-id="8046e-120">証明書を追加します。</span><span class="sxs-lookup"><span data-stu-id="8046e-120">Add a certificate</span></span>  
  
1. <span data-ttu-id="8046e-121">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="8046e-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="8046e-122">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="8046e-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="8046e-123">アプリケーションを見つけて、トランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="8046e-123">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="8046e-124">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="8046e-124">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="8046e-125">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8046e-125">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="8046e-126">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="8046e-126">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="8046e-127">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="8046e-127">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="8046e-128">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブ。</span><span class="sxs-lookup"><span data-stu-id="8046e-128">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **General** tab.</span></span>  
  
9. <span data-ttu-id="8046e-129">**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8046e-129">Click **Edit**.</span></span>  
  
10. <span data-ttu-id="8046e-130">**Id エディター**  ダイアログ ボックスで、検索条件の確認、**証明書参照**有効な証明書を示すセクションが正しく構成されてです。</span><span class="sxs-lookup"><span data-stu-id="8046e-130">In the **Identity Editor** dialog box, make sure the search criteria in the **Certificate Reference** section is configured properly to indicate valid certificates.</span></span>  
  
    <span data-ttu-id="8046e-131">Wcf-custom と Wcf-customisolated アダプターでは、確実に検索条件、**証明書参照**証明書の有効な証明書を示すセクションが正しく構成されて**ストア名**.</span><span class="sxs-lookup"><span data-stu-id="8046e-131">For the WCF-Custom and the WCF-CustomIsolated adapters, ensure that the search criteria in the **Certificate Reference** section is configured properly to indicate a valid certificate in the certificate **Store name**.</span></span>  
  
## <a name="add-a-certificate-for-standard-wcf-adapters"></a><span data-ttu-id="8046e-132">標準の WCF アダプター用の証明書を追加します。</span><span class="sxs-lookup"><span data-stu-id="8046e-132">Add a certificate for standard WCF adapters</span></span>  
  
1. <span data-ttu-id="8046e-133">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="8046e-133">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="8046e-134">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="8046e-134">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="8046e-135">アプリケーションを見つけて、トランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="8046e-135">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="8046e-136">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="8046e-136">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="8046e-137">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8046e-137">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="8046e-138">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="8046e-138">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="8046e-139">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="8046e-139">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="8046e-140">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**セキュリティ**タブ。</span><span class="sxs-lookup"><span data-stu-id="8046e-140">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Security** tab.</span></span>  
  
9. <span data-ttu-id="8046e-141">いることを確認、**拇印**サービスとクライアント証明書のプロパティは、証明書の有効な証明書を示す**ストア名**します。</span><span class="sxs-lookup"><span data-stu-id="8046e-141">Ensure that the **Thumbprint** properties for the service and client certificates indicate valid certificates in the certificate **Store name**.</span></span>  
  
   <span data-ttu-id="8046e-142">証明書スナップインでは、WCF トランスポートのため、有効な証明書がインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8046e-142">In the Certificate snap-in, make sure that valid certificates are installed for the WCF transport.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8046e-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="8046e-143">See also</span></span> 
  
[<span data-ttu-id="8046e-144">WCF アダプターの証明書のインストール</span><span class="sxs-lookup"><span data-stu-id="8046e-144">Installing Certificates for the WCF Adapters</span></span>](../core/installing-certificates-for-the-wcf-adapters.md)  