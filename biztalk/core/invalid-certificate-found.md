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
ms.openlocfilehash: e9a069ee0c934f9a7636646a07bd5a7f777d88c5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020586"
---
# <a name="invalid-certificate-found"></a><span data-ttu-id="f91e9-102">無効な証明書が見つかりました</span><span class="sxs-lookup"><span data-stu-id="f91e9-102">Invalid certificate found</span></span>
## <a name="details"></a><span data-ttu-id="f91e9-103">詳細</span><span class="sxs-lookup"><span data-stu-id="f91e9-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="f91e9-104">製品名</span><span class="sxs-lookup"><span data-stu-id="f91e9-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="f91e9-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f91e9-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="f91e9-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f91e9-106">Event ID</span></span>     |                                         <span data-ttu-id="f91e9-107">0</span><span class="sxs-lookup"><span data-stu-id="f91e9-107">0</span></span>                                          |
|  <span data-ttu-id="f91e9-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f91e9-108">Event Source</span></span>   |                                         <span data-ttu-id="f91e9-109">0</span><span class="sxs-lookup"><span data-stu-id="f91e9-109">0</span></span>                                          |
|    <span data-ttu-id="f91e9-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f91e9-110">Component</span></span>    |                                         <span data-ttu-id="f91e9-111">0</span><span class="sxs-lookup"><span data-stu-id="f91e9-111">0</span></span>                                          |
|  <span data-ttu-id="f91e9-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f91e9-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="f91e9-113">0</span><span class="sxs-lookup"><span data-stu-id="f91e9-113">0</span></span>                                          |
|  <span data-ttu-id="f91e9-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f91e9-114">Message Text</span></span>   |                             <span data-ttu-id="f91e9-115">無効な証明書が見つかりました</span><span class="sxs-lookup"><span data-stu-id="f91e9-115">Invalid certificate found</span></span>                              |
  
## <a name="explanation"></a><span data-ttu-id="f91e9-116">説明</span><span class="sxs-lookup"><span data-stu-id="f91e9-116">Explanation</span></span>  
 <span data-ttu-id="f91e9-117">WCF トランスポートの有効な証明書が指定されていませんでした。</span><span class="sxs-lookup"><span data-stu-id="f91e9-117">You did not provide a valid certificate for a WCF transport.</span></span>  

#### <a name="user-action"></a><span data-ttu-id="f91e9-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f91e9-118">User Action</span></span>
<span data-ttu-id="f91e9-119">証明書を追加します。</span><span class="sxs-lookup"><span data-stu-id="f91e9-119">Add a certificate.</span></span> 
  
## <a name="add-a-certificate"></a><span data-ttu-id="f91e9-120">証明書を追加します。</span><span class="sxs-lookup"><span data-stu-id="f91e9-120">Add a certificate</span></span>  
  
1. <span data-ttu-id="f91e9-121">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="f91e9-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="f91e9-122">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="f91e9-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="f91e9-123">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="f91e9-123">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="f91e9-124">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="f91e9-124">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="f91e9-125">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f91e9-125">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="f91e9-126">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="f91e9-126">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="f91e9-127">クリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="f91e9-127">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="f91e9-128">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブ。</span><span class="sxs-lookup"><span data-stu-id="f91e9-128">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **General** tab.</span></span>  
  
9. <span data-ttu-id="f91e9-129">**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f91e9-129">Click **Edit**.</span></span>  
  
10. <span data-ttu-id="f91e9-130">**Id エディター**  ダイアログ ボックスで、検索条件の確認、**証明書参照**有効な証明書を示すセクションが正しく構成されてです。</span><span class="sxs-lookup"><span data-stu-id="f91e9-130">In the **Identity Editor** dialog box, make sure the search criteria in the **Certificate Reference** section is configured properly to indicate valid certificates.</span></span>  
  
    <span data-ttu-id="f91e9-131">Wcf-custom と Wcf-customisolated アダプターでは、確実に検索条件、**証明書参照**証明書の有効な証明書を示すセクションが正しく構成されて**ストア名**.</span><span class="sxs-lookup"><span data-stu-id="f91e9-131">For the WCF-Custom and the WCF-CustomIsolated adapters, ensure that the search criteria in the **Certificate Reference** section is configured properly to indicate a valid certificate in the certificate **Store name**.</span></span>  
  
## <a name="add-a-certificate-for-standard-wcf-adapters"></a><span data-ttu-id="f91e9-132">標準の WCF アダプター用の証明書を追加します。</span><span class="sxs-lookup"><span data-stu-id="f91e9-132">Add a certificate for standard WCF adapters</span></span>  
  
1. <span data-ttu-id="f91e9-133">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="f91e9-133">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="f91e9-134">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="f91e9-134">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="f91e9-135">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="f91e9-135">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="f91e9-136">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="f91e9-136">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="f91e9-137">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f91e9-137">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="f91e9-138">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="f91e9-138">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="f91e9-139">クリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="f91e9-139">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="f91e9-140">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**セキュリティ**タブ。</span><span class="sxs-lookup"><span data-stu-id="f91e9-140">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Security** tab.</span></span>  
  
9. <span data-ttu-id="f91e9-141">いることを確認、**拇印**サービスとクライアント証明書のプロパティは、証明書の有効な証明書を示す**ストア名**します。</span><span class="sxs-lookup"><span data-stu-id="f91e9-141">Ensure that the **Thumbprint** properties for the service and client certificates indicate valid certificates in the certificate **Store name**.</span></span>  
  
   <span data-ttu-id="f91e9-142">証明書スナップインで、WCF トランスポート用の有効な証明書がインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f91e9-142">In the Certificate snap-in, make sure that valid certificates are installed for the WCF transport.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f91e9-143">参照</span><span class="sxs-lookup"><span data-stu-id="f91e9-143">See also</span></span> 
  
[<span data-ttu-id="f91e9-144">WCF アダプターの証明書のインストール</span><span class="sxs-lookup"><span data-stu-id="f91e9-144">Installing Certificates for the WCF Adapters</span></span>](../core/installing-certificates-for-the-wcf-adapters.md)  