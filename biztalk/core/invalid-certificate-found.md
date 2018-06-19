---
title: 無効な証明書が見つかりました |Microsoft ドキュメント
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
ms.openlocfilehash: 8fdf1d80818dd8e7dba349ea1dec9b69fa66a2fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257850"
---
# <a name="invalid-certificate-found"></a><span data-ttu-id="b5342-102">無効な証明書が見つかりました</span><span class="sxs-lookup"><span data-stu-id="b5342-102">Invalid certificate found</span></span>
## <a name="details"></a><span data-ttu-id="b5342-103">詳細</span><span class="sxs-lookup"><span data-stu-id="b5342-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b5342-104">製品名</span><span class="sxs-lookup"><span data-stu-id="b5342-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="b5342-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="b5342-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="b5342-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="b5342-106">Event ID</span></span>|<span data-ttu-id="b5342-107">0</span><span class="sxs-lookup"><span data-stu-id="b5342-107">0</span></span>|  
|<span data-ttu-id="b5342-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="b5342-108">Event Source</span></span>|<span data-ttu-id="b5342-109">0</span><span class="sxs-lookup"><span data-stu-id="b5342-109">0</span></span>|  
|<span data-ttu-id="b5342-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b5342-110">Component</span></span>|<span data-ttu-id="b5342-111">0</span><span class="sxs-lookup"><span data-stu-id="b5342-111">0</span></span>|  
|<span data-ttu-id="b5342-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="b5342-112">Symbolic Name</span></span>|<span data-ttu-id="b5342-113">0</span><span class="sxs-lookup"><span data-stu-id="b5342-113">0</span></span>|  
|<span data-ttu-id="b5342-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="b5342-114">Message Text</span></span>|<span data-ttu-id="b5342-115">無効な証明書が見つかりました</span><span class="sxs-lookup"><span data-stu-id="b5342-115">Invalid certificate found</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b5342-116">説明</span><span class="sxs-lookup"><span data-stu-id="b5342-116">Explanation</span></span>  
 <span data-ttu-id="b5342-117">WCF トランスポートの有効な証明書が指定されていませんでした。</span><span class="sxs-lookup"><span data-stu-id="b5342-117">You did not provide a valid certificate for a WCF transport.</span></span>  

#### <a name="user-action"></a><span data-ttu-id="b5342-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="b5342-118">User Action</span></span>
<span data-ttu-id="b5342-119">証明書を追加します。</span><span class="sxs-lookup"><span data-stu-id="b5342-119">Add a certificate.</span></span> 
  
## <a name="add-a-certificate"></a><span data-ttu-id="b5342-120">証明書の追加します。</span><span class="sxs-lookup"><span data-stu-id="b5342-120">Add a certificate</span></span>  
  
1.  <span data-ttu-id="b5342-121">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="b5342-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="b5342-122">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="b5342-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="b5342-123">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="b5342-123">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="b5342-124">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="b5342-124">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="b5342-125">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b5342-125">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="b5342-126">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="b5342-126">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="b5342-127">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="b5342-127">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="b5342-128">**WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブです。</span><span class="sxs-lookup"><span data-stu-id="b5342-128">In the **WCF [***transport type***] Transport Properties** dialog box, click the **General** tab.</span></span>  
  
9. <span data-ttu-id="b5342-129">**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b5342-129">Click **Edit**.</span></span>  
  
10. <span data-ttu-id="b5342-130">**Id エディター**  ダイアログ ボックスでの検索条件の確認、**証明書参照**セクションが有効な証明書を示すために正しく構成されてです。</span><span class="sxs-lookup"><span data-stu-id="b5342-130">In the **Identity Editor** dialog box, make sure the search criteria in the **Certificate Reference** section is configured properly to indicate valid certificates.</span></span>  
  
 <span data-ttu-id="b5342-131">Wcf-custom と Wcf-customisolated アダプターでは、確実に検索条件、**証明書参照**セクションでは、証明書の有効な証明書を示すために正しく構成されて**ストア名**.</span><span class="sxs-lookup"><span data-stu-id="b5342-131">For the WCF-Custom and the WCF-CustomIsolated adapters, ensure that the search criteria in the **Certificate Reference** section is configured properly to indicate a valid certificate in the certificate **Store name**.</span></span>  
  
## <a name="add-a-certificate-for-standard-wcf-adapters"></a><span data-ttu-id="b5342-132">標準の WCF アダプター用の証明書を追加します。</span><span class="sxs-lookup"><span data-stu-id="b5342-132">Add a certificate for standard WCF adapters</span></span>  
  
1.  <span data-ttu-id="b5342-133">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="b5342-133">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="b5342-134">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="b5342-134">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="b5342-135">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="b5342-135">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="b5342-136">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="b5342-136">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="b5342-137">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b5342-137">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="b5342-138">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="b5342-138">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="b5342-139">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="b5342-139">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="b5342-140">**WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**セキュリティ**タブです。</span><span class="sxs-lookup"><span data-stu-id="b5342-140">In the **WCF [***transport type***] Transport Properties** dialog box, click the **Security** tab.</span></span>  
  
9. <span data-ttu-id="b5342-141">いることを確認、**拇印**サービスとクライアント証明書のプロパティが証明書の有効な証明書を示す**ストア名**です。</span><span class="sxs-lookup"><span data-stu-id="b5342-141">Ensure that the **Thumbprint** properties for the service and client certificates indicate valid certificates in the certificate **Store name**.</span></span>  
  
 <span data-ttu-id="b5342-142">証明書スナップインで、WCF トランスポート用の有効な証明書がインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b5342-142">In the Certificate snap-in, make sure that valid certificates are installed for the WCF transport.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5342-143">参照</span><span class="sxs-lookup"><span data-stu-id="b5342-143">See also</span></span> 
  
[<span data-ttu-id="b5342-144">WCF アダプターの証明書のインストール</span><span class="sxs-lookup"><span data-stu-id="b5342-144">Installing Certificates for the WCF Adapters</span></span>](../core/installing-certificates-for-the-wcf-adapters.md)  