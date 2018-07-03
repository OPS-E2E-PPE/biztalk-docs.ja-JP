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
ms.openlocfilehash: 2ac43f85b590ede746bbd14065d8e01701d1e91f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988835"
---
# <a name="ambiguous-certificate-reference"></a><span data-ttu-id="9890c-102">証明書の参照があいまいです</span><span class="sxs-lookup"><span data-stu-id="9890c-102">Ambiguous certificate reference</span></span>
## <a name="details"></a><span data-ttu-id="9890c-103">詳細</span><span class="sxs-lookup"><span data-stu-id="9890c-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="9890c-104">製品名</span><span class="sxs-lookup"><span data-stu-id="9890c-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="9890c-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="9890c-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="9890c-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="9890c-106">Event ID</span></span>     |                                         <span data-ttu-id="9890c-107">0</span><span class="sxs-lookup"><span data-stu-id="9890c-107">0</span></span>                                          |
|  <span data-ttu-id="9890c-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="9890c-108">Event Source</span></span>   |                                         <span data-ttu-id="9890c-109">0</span><span class="sxs-lookup"><span data-stu-id="9890c-109">0</span></span>                                          |
|    <span data-ttu-id="9890c-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9890c-110">Component</span></span>    |                                         <span data-ttu-id="9890c-111">0</span><span class="sxs-lookup"><span data-stu-id="9890c-111">0</span></span>                                          |
|  <span data-ttu-id="9890c-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="9890c-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="9890c-113">0</span><span class="sxs-lookup"><span data-stu-id="9890c-113">0</span></span>                                          |
|  <span data-ttu-id="9890c-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="9890c-114">Message Text</span></span>   |       <span data-ttu-id="9890c-115">証明書の参照があいまいです。有効な証明書が複数見つかりました。</span><span class="sxs-lookup"><span data-stu-id="9890c-115">Ambiguous certificate reference; more than one valid certificate found</span></span>       |
  
## <a name="explanation"></a><span data-ttu-id="9890c-116">説明</span><span class="sxs-lookup"><span data-stu-id="9890c-116">Explanation</span></span>  
 <span data-ttu-id="9890c-117">複数の有効な証明書が見つかりました。</span><span class="sxs-lookup"><span data-stu-id="9890c-117">More than one valid certificate was found.</span></span>  
  
#### <a name="user-action"></a><span data-ttu-id="9890c-118">ユーザーのアクション</span><span class="sxs-lookup"><span data-stu-id="9890c-118">User action</span></span>  
 <span data-ttu-id="9890c-119">1 つだけ有効な証明書が構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9890c-119">Verify only one valid certificate is configured.</span></span>  
  
## <a name="verify-certificate"></a><span data-ttu-id="9890c-120">証明書を確認します。</span><span class="sxs-lookup"><span data-stu-id="9890c-120">Verify certificate</span></span> 
  
1. <span data-ttu-id="9890c-121">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="9890c-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="9890c-122">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="9890c-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand **Applications**.</span></span>  
  
3. <span data-ttu-id="9890c-123">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="9890c-123">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="9890c-124">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="9890c-124">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="9890c-125">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9890c-125">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="9890c-126">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="9890c-126">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="9890c-127">クリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="9890c-127">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="9890c-128">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブ。</span><span class="sxs-lookup"><span data-stu-id="9890c-128">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **General** tab.</span></span>  
  
9. <span data-ttu-id="9890c-129">**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9890c-129">Click **Edit**.</span></span>  
  
10. <span data-ttu-id="9890c-130">**Id エディター**  ダイアログ ボックスで、検索条件の確認、**証明書参照**証明書の証明書を 1 つだけを示すセクションが正しく構成されて**ストア名前**します。</span><span class="sxs-lookup"><span data-stu-id="9890c-130">In the **Identity Editor** dialog box, make sure the search criteria in the **Certificate Reference** section is configured properly to indicate only one certificate in the certificate **Store name**.</span></span>  
  
## <a name="verify-a-certificate-for-the-wcf-custom-and-the-wcf-customisolated-adapters"></a><span data-ttu-id="9890c-131">Wcf-custom および Wcf-customisolated アダプターの証明書を確認します。</span><span class="sxs-lookup"><span data-stu-id="9890c-131">Verify a certificate for the WCF-Custom and the WCF-CustomIsolated adapters</span></span>  
  
1. <span data-ttu-id="9890c-132">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、 をクリック[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="9890c-132">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and click [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  
  
2. <span data-ttu-id="9890c-133">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="9890c-133">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand **Applications**.</span></span>  
  
3. <span data-ttu-id="9890c-134">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="9890c-134">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="9890c-135">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="9890c-135">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="9890c-136">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9890c-136">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="9890c-137">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="9890c-137">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="9890c-138">クリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="9890c-138">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="9890c-139">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**動作**タブ。</span><span class="sxs-lookup"><span data-stu-id="9890c-139">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Behavior** tab.</span></span>  
  
9. <span data-ttu-id="9890c-140">検索条件の確認、**証明書参照**証明書の証明書を 1 つだけを示すセクションが正しく構成されて**ストア名**。</span><span class="sxs-lookup"><span data-stu-id="9890c-140">Ensure the search criteria in the **Certificate Reference** section is configured properly to indicate only one certificate in the certificate **Store name**.</span></span>  
  
10. <span data-ttu-id="9890c-141">[証明書] スナップインで、WCF トランスポートに構成した検索条件で唯一の証明書がインストールされることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9890c-141">In the Certificate snap-in, make sure only one certificate is installed for the search criteria you configured to the WCF transport.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9890c-142">参照</span><span class="sxs-lookup"><span data-stu-id="9890c-142">See also</span></span>
[<span data-ttu-id="9890c-143">WCF アダプターの証明書のインストール</span><span class="sxs-lookup"><span data-stu-id="9890c-143">Installing Certificates for the WCF Adapters</span></span>](../core/installing-certificates-for-the-wcf-adapters.md)  
 