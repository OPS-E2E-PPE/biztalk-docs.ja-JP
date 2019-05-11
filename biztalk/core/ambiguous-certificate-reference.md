---
title: あいまいな証明書参照 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a7a6a60d-97e6-4c60-86be-83efb4a50f99
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c61b28ff583486efbb475eff51f6292ecc8a0367
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359253"
---
# <a name="ambiguous-certificate-reference"></a><span data-ttu-id="4f96f-102">証明書の参照があいまいです</span><span class="sxs-lookup"><span data-stu-id="4f96f-102">Ambiguous certificate reference</span></span>
## <a name="details"></a><span data-ttu-id="4f96f-103">詳細</span><span class="sxs-lookup"><span data-stu-id="4f96f-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="4f96f-104">製品名</span><span class="sxs-lookup"><span data-stu-id="4f96f-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="4f96f-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="4f96f-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="4f96f-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4f96f-106">Event ID</span></span>     |                                         <span data-ttu-id="4f96f-107">0</span><span class="sxs-lookup"><span data-stu-id="4f96f-107">0</span></span>                                          |
|  <span data-ttu-id="4f96f-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="4f96f-108">Event Source</span></span>   |                                         <span data-ttu-id="4f96f-109">0</span><span class="sxs-lookup"><span data-stu-id="4f96f-109">0</span></span>                                          |
|    <span data-ttu-id="4f96f-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="4f96f-110">Component</span></span>    |                                         <span data-ttu-id="4f96f-111">0</span><span class="sxs-lookup"><span data-stu-id="4f96f-111">0</span></span>                                          |
|  <span data-ttu-id="4f96f-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="4f96f-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="4f96f-113">0</span><span class="sxs-lookup"><span data-stu-id="4f96f-113">0</span></span>                                          |
|  <span data-ttu-id="4f96f-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="4f96f-114">Message Text</span></span>   |       <span data-ttu-id="4f96f-115">あいまいな証明書の参照。1 つ以上の有効な証明書が見つかりません</span><span class="sxs-lookup"><span data-stu-id="4f96f-115">Ambiguous certificate reference; more than one valid certificate found</span></span>       |
  
## <a name="explanation"></a><span data-ttu-id="4f96f-116">説明</span><span class="sxs-lookup"><span data-stu-id="4f96f-116">Explanation</span></span>  
 <span data-ttu-id="4f96f-117">1 つ以上の有効な証明書が見つかりました。</span><span class="sxs-lookup"><span data-stu-id="4f96f-117">More than one valid certificate was found.</span></span>  
  
#### <a name="user-action"></a><span data-ttu-id="4f96f-118">ユーザーのアクション</span><span class="sxs-lookup"><span data-stu-id="4f96f-118">User action</span></span>  
 <span data-ttu-id="4f96f-119">1 つだけ有効な証明書が構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4f96f-119">Verify only one valid certificate is configured.</span></span>  
  
## <a name="verify-certificate"></a><span data-ttu-id="4f96f-120">証明書を確認します。</span><span class="sxs-lookup"><span data-stu-id="4f96f-120">Verify certificate</span></span> 
  
1. <span data-ttu-id="4f96f-121">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="4f96f-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="4f96f-122">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="4f96f-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand **Applications**.</span></span>  
  
3. <span data-ttu-id="4f96f-123">アプリケーションを見つけて、トランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="4f96f-123">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="4f96f-124">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="4f96f-124">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="4f96f-125">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f96f-125">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="4f96f-126">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="4f96f-126">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="4f96f-127">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="4f96f-127">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="4f96f-128">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブ。</span><span class="sxs-lookup"><span data-stu-id="4f96f-128">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **General** tab.</span></span>  
  
9. <span data-ttu-id="4f96f-129">**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f96f-129">Click **Edit**.</span></span>  
  
10. <span data-ttu-id="4f96f-130">**Id エディター**  ダイアログ ボックスで、検索条件の確認、**証明書参照**証明書の証明書を 1 つだけを示すセクションが正しく構成されて**ストア名前**します。</span><span class="sxs-lookup"><span data-stu-id="4f96f-130">In the **Identity Editor** dialog box, make sure the search criteria in the **Certificate Reference** section is configured properly to indicate only one certificate in the certificate **Store name**.</span></span>  
  
## <a name="verify-a-certificate-for-the-wcf-custom-and-the-wcf-customisolated-adapters"></a><span data-ttu-id="4f96f-131">Wcf-custom および Wcf-customisolated アダプターの証明書を確認します。</span><span class="sxs-lookup"><span data-stu-id="4f96f-131">Verify a certificate for the WCF-Custom and the WCF-CustomIsolated adapters</span></span>  
  
1. <span data-ttu-id="4f96f-132">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、 をクリック[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="4f96f-132">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and click [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  
  
2. <span data-ttu-id="4f96f-133">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="4f96f-133">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand **Applications**.</span></span>  
  
3. <span data-ttu-id="4f96f-134">アプリケーションを見つけて、トランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="4f96f-134">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="4f96f-135">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="4f96f-135">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="4f96f-136">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f96f-136">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="4f96f-137">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="4f96f-137">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="4f96f-138">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="4f96f-138">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="4f96f-139">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**動作**タブ。</span><span class="sxs-lookup"><span data-stu-id="4f96f-139">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Behavior** tab.</span></span>  
  
9. <span data-ttu-id="4f96f-140">検索条件の確認、**証明書参照**証明書の証明書を 1 つだけを示すセクションが正しく構成されて**ストア名**。</span><span class="sxs-lookup"><span data-stu-id="4f96f-140">Ensure the search criteria in the **Certificate Reference** section is configured properly to indicate only one certificate in the certificate **Store name**.</span></span>  
  
10. <span data-ttu-id="4f96f-141">証明書スナップインで、WCF トランスポートに構成した検索条件の 1 つだけの証明書がインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4f96f-141">In the Certificate snap-in, make sure only one certificate is installed for the search criteria you configured to the WCF transport.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f96f-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="4f96f-142">See also</span></span>
[<span data-ttu-id="4f96f-143">WCF アダプターの証明書のインストール</span><span class="sxs-lookup"><span data-stu-id="4f96f-143">Installing Certificates for the WCF Adapters</span></span>](../core/installing-certificates-for-the-wcf-adapters.md)  
 