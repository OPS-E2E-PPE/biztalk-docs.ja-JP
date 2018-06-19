---
title: あいまいな証明書参照 |Microsoft ドキュメント
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
ms.openlocfilehash: 304ded9572ba6598f7f2132a678a14b2b3301c10
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230706"
---
# <a name="ambiguous-certificate-reference"></a><span data-ttu-id="91ea5-102">証明書の参照があいまいです</span><span class="sxs-lookup"><span data-stu-id="91ea5-102">Ambiguous certificate reference</span></span>
## <a name="details"></a><span data-ttu-id="91ea5-103">詳細</span><span class="sxs-lookup"><span data-stu-id="91ea5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="91ea5-104">製品名</span><span class="sxs-lookup"><span data-stu-id="91ea5-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="91ea5-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="91ea5-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="91ea5-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="91ea5-106">Event ID</span></span>|<span data-ttu-id="91ea5-107">0</span><span class="sxs-lookup"><span data-stu-id="91ea5-107">0</span></span>|  
|<span data-ttu-id="91ea5-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="91ea5-108">Event Source</span></span>|<span data-ttu-id="91ea5-109">0</span><span class="sxs-lookup"><span data-stu-id="91ea5-109">0</span></span>|  
|<span data-ttu-id="91ea5-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="91ea5-110">Component</span></span>|<span data-ttu-id="91ea5-111">0</span><span class="sxs-lookup"><span data-stu-id="91ea5-111">0</span></span>|  
|<span data-ttu-id="91ea5-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="91ea5-112">Symbolic Name</span></span>|<span data-ttu-id="91ea5-113">0</span><span class="sxs-lookup"><span data-stu-id="91ea5-113">0</span></span>|  
|<span data-ttu-id="91ea5-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="91ea5-114">Message Text</span></span>|<span data-ttu-id="91ea5-115">証明書の参照があいまいです。有効な証明書が複数見つかりました。</span><span class="sxs-lookup"><span data-stu-id="91ea5-115">Ambiguous certificate reference; more than one valid certificate found</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="91ea5-116">説明</span><span class="sxs-lookup"><span data-stu-id="91ea5-116">Explanation</span></span>  
 <span data-ttu-id="91ea5-117">複数の有効な証明書が見つかりました。</span><span class="sxs-lookup"><span data-stu-id="91ea5-117">More than one valid certificate was found.</span></span>  
  
#### <a name="user-action"></a><span data-ttu-id="91ea5-118">ユーザーのアクション</span><span class="sxs-lookup"><span data-stu-id="91ea5-118">User action</span></span>  
 <span data-ttu-id="91ea5-119">1 つだけ有効な証明書が構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="91ea5-119">Verify only one valid certificate is configured.</span></span>  
  
## <a name="verify-certificate"></a><span data-ttu-id="91ea5-120">証明書を確認します。</span><span class="sxs-lookup"><span data-stu-id="91ea5-120">Verify certificate</span></span> 
  
1.  <span data-ttu-id="91ea5-121">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="91ea5-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="91ea5-122">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="91ea5-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="91ea5-123">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="91ea5-123">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="91ea5-124">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="91ea5-124">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="91ea5-125">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="91ea5-125">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="91ea5-126">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="91ea5-126">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="91ea5-127">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="91ea5-127">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="91ea5-128">**WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブです。</span><span class="sxs-lookup"><span data-stu-id="91ea5-128">In the **WCF [***transport type***] Transport Properties** dialog box, click the **General** tab.</span></span>  
  
9. <span data-ttu-id="91ea5-129">**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="91ea5-129">Click **Edit**.</span></span>  
  
10. <span data-ttu-id="91ea5-130">**Id エディター**  ダイアログ ボックスでの検索条件の確認、**証明書参照**セクションは、証明書の証明書を 1 つだけを示すために正しく構成されて**ストア名前**です。</span><span class="sxs-lookup"><span data-stu-id="91ea5-130">In the **Identity Editor** dialog box, make sure the search criteria in the **Certificate Reference** section is configured properly to indicate only one certificate in the certificate **Store name**.</span></span>  
  
## <a name="verify-a-certificate-for-the-wcf-custom-and-the-wcf-customisolated-adapters"></a><span data-ttu-id="91ea5-131">Wcf-custom および Wcf-customisolated アダプターの証明書を確認してください。</span><span class="sxs-lookup"><span data-stu-id="91ea5-131">Verify a certificate for the WCF-Custom and the WCF-CustomIsolated adapters</span></span>  
  
1.  <span data-ttu-id="91ea5-132">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、 をクリック[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="91ea5-132">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and click [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  
  
2.  <span data-ttu-id="91ea5-133">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="91ea5-133">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="91ea5-134">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="91ea5-134">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="91ea5-135">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="91ea5-135">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="91ea5-136">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="91ea5-136">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="91ea5-137">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="91ea5-137">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="91ea5-138">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="91ea5-138">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="91ea5-139">**WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**動作**タブです。</span><span class="sxs-lookup"><span data-stu-id="91ea5-139">In the **WCF [***transport type***] Transport Properties** dialog box, click the **Behavior** tab.</span></span>  
  
9. <span data-ttu-id="91ea5-140">内の検索条件を確認してください、**証明書参照**セクションは、証明書の証明書を 1 つだけを示すために正しく構成されて**ストア名**です。</span><span class="sxs-lookup"><span data-stu-id="91ea5-140">Ensure the search criteria in the **Certificate Reference** section is configured properly to indicate only one certificate in the certificate **Store name**.</span></span>  
  
10. <span data-ttu-id="91ea5-141">[証明書] スナップインで、WCF トランスポートに構成した検索条件で唯一の証明書がインストールされることを確認します。</span><span class="sxs-lookup"><span data-stu-id="91ea5-141">In the Certificate snap-in, make sure only one certificate is installed for the search criteria you configured to the WCF transport.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91ea5-142">参照</span><span class="sxs-lookup"><span data-stu-id="91ea5-142">See also</span></span>
[<span data-ttu-id="91ea5-143">WCF アダプターの証明書のインストール</span><span class="sxs-lookup"><span data-stu-id="91ea5-143">Installing Certificates for the WCF Adapters</span></span>](../core/installing-certificates-for-the-wcf-adapters.md)  
 