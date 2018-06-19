---
title: 証明書が見つかりません |。Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 629b199f-1884-4e88-beaa-a2e5c5e792e9
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1c18f112edc14375e6edc2aaa52c9e468d1bd39
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232610"
---
# <a name="certificate-not-found"></a><span data-ttu-id="fd7fd-102">証明書が見つかりません</span><span class="sxs-lookup"><span data-stu-id="fd7fd-102">Certificate not found</span></span>
## <a name="details"></a><span data-ttu-id="fd7fd-103">詳細</span><span class="sxs-lookup"><span data-stu-id="fd7fd-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fd7fd-104">製品名</span><span class="sxs-lookup"><span data-stu-id="fd7fd-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="fd7fd-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="fd7fd-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="fd7fd-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="fd7fd-106">Event ID</span></span>|<span data-ttu-id="fd7fd-107">0</span><span class="sxs-lookup"><span data-stu-id="fd7fd-107">0</span></span>|  
|<span data-ttu-id="fd7fd-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="fd7fd-108">Event Source</span></span>|<span data-ttu-id="fd7fd-109">0</span><span class="sxs-lookup"><span data-stu-id="fd7fd-109">0</span></span>|  
|<span data-ttu-id="fd7fd-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="fd7fd-110">Component</span></span>|<span data-ttu-id="fd7fd-111">0</span><span class="sxs-lookup"><span data-stu-id="fd7fd-111">0</span></span>|  
|<span data-ttu-id="fd7fd-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="fd7fd-112">Symbolic Name</span></span>|<span data-ttu-id="fd7fd-113">0</span><span class="sxs-lookup"><span data-stu-id="fd7fd-113">0</span></span>|  
|<span data-ttu-id="fd7fd-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="fd7fd-114">Message Text</span></span>|<span data-ttu-id="fd7fd-115">証明書が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="fd7fd-115">Certificate not found.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fd7fd-116">説明</span><span class="sxs-lookup"><span data-stu-id="fd7fd-116">Explanation</span></span>  
 <span data-ttu-id="fd7fd-117">指定した検索条件の証明書が見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="fd7fd-117">A certificate could not be found for the given search criteria.</span></span>  

#### <a name="user-action"></a><span data-ttu-id="fd7fd-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="fd7fd-118">User Action</span></span>
<span data-ttu-id="fd7fd-119">証明書の検索条件を確認します。</span><span class="sxs-lookup"><span data-stu-id="fd7fd-119">Verify search criteria for certificates.</span></span> 
  
## <a name="verify-search-criteria"></a><span data-ttu-id="fd7fd-120">検索条件を確認します</span><span class="sxs-lookup"><span data-stu-id="fd7fd-120">Verify search criteria</span></span>  
  
1.  <span data-ttu-id="fd7fd-121">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="fd7fd-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="fd7fd-122">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="fd7fd-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="fd7fd-123">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="fd7fd-123">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="fd7fd-124">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="fd7fd-124">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="fd7fd-125">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fd7fd-125">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="fd7fd-126">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="fd7fd-126">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="fd7fd-127">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="fd7fd-127">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="fd7fd-128">**WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブです。</span><span class="sxs-lookup"><span data-stu-id="fd7fd-128">In the **WCF [***transport type***] Transport Properties** dialog box, click the **General** tab.</span></span>  
  
9. <span data-ttu-id="fd7fd-129">**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fd7fd-129">Click **Edit**.</span></span>  
  
10. <span data-ttu-id="fd7fd-130">**Id エディター**  ダイアログ ボックスで、ことを確認して内の検索条件、**証明書参照**セクションが有効な証明書を示すために正しく構成されてです。</span><span class="sxs-lookup"><span data-stu-id="fd7fd-130">In the **Identity Editor** dialog box, make sure that the search criteria in the **Certificate Reference** section is configured properly to indicate valid certificates.</span></span>  
  
 <span data-ttu-id="fd7fd-131">Wcf-custom と Wcf-customisolated アダプターでは、確実に検索条件、**証明書参照**セクションでは、証明書の有効な証明書を示すために正しく構成されて**ストア名**.</span><span class="sxs-lookup"><span data-stu-id="fd7fd-131">For the WCF-Custom and the WCF-CustomIsolated adapters, ensure that the search criteria in the **Certificate Reference** section is configured properly to indicate a valid certificate in the certificate **Store name**.</span></span>  
  
## <a name="verify-search-criteria-for-standard-wcf-adapters"></a><span data-ttu-id="fd7fd-132">標準の WCF アダプタの検索条件を確認してください。</span><span class="sxs-lookup"><span data-stu-id="fd7fd-132">Verify search criteria for standard WCF adapters</span></span>  
  
1.  <span data-ttu-id="fd7fd-133">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="fd7fd-133">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="fd7fd-134">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="fd7fd-134">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="fd7fd-135">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="fd7fd-135">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="fd7fd-136">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="fd7fd-136">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="fd7fd-137">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fd7fd-137">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="fd7fd-138">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="fd7fd-138">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="fd7fd-139">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="fd7fd-139">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="fd7fd-140">**WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**セキュリティ**タブです。</span><span class="sxs-lookup"><span data-stu-id="fd7fd-140">In the **WCF [***transport type***] Transport Properties** dialog box, click the **Security** tab.</span></span>  
  
9. <span data-ttu-id="fd7fd-141">いることを確認、**拇印**サービスとクライアント証明書のプロパティが証明書ストアに有効な証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="fd7fd-141">Ensure that the **Thumbprint** properties for the service and client certificates indicate valid certificates in certificate stores.</span></span>  
  
10. <span data-ttu-id="fd7fd-142">証明書スナップインで、WCF トランスポート用の有効な証明書がインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fd7fd-142">In the Certificate snap-in, make sure that valid certificates are installed for the WCF transport.</span></span>  

## <a name="see-also"></a><span data-ttu-id="fd7fd-143">参照</span><span class="sxs-lookup"><span data-stu-id="fd7fd-143">See also</span></span> 
  
-   [<span data-ttu-id="fd7fd-144">WCF アダプターの証明書のインストール</span><span class="sxs-lookup"><span data-stu-id="fd7fd-144">Installing Certificates for the WCF Adapters</span></span>](../core/installing-certificates-for-the-wcf-adapters.md)  
  
