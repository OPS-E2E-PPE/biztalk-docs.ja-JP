---
title: サービス証明書の拇印が指定されていないために必要な |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ca853667-83b5-41f2-9b54-8117b87e27d3
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6dc43d9ed50aaacd108b275063cf00d18aea743
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268562"
---
# <a name="required-service-certificate-thumbprint-not-specified"></a><span data-ttu-id="9f822-102">必要なサービス証明書の拇印が指定されていません</span><span class="sxs-lookup"><span data-stu-id="9f822-102">Required service certificate thumbprint not specified</span></span>
## <a name="details"></a><span data-ttu-id="9f822-103">詳細</span><span class="sxs-lookup"><span data-stu-id="9f822-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9f822-104">製品名</span><span class="sxs-lookup"><span data-stu-id="9f822-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="9f822-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="9f822-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="9f822-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="9f822-106">Event ID</span></span>|<span data-ttu-id="9f822-107">0</span><span class="sxs-lookup"><span data-stu-id="9f822-107">0</span></span>|  
|<span data-ttu-id="9f822-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="9f822-108">Event Source</span></span>|<span data-ttu-id="9f822-109">0</span><span class="sxs-lookup"><span data-stu-id="9f822-109">0</span></span>|  
|<span data-ttu-id="9f822-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9f822-110">Component</span></span>|<span data-ttu-id="9f822-111">0</span><span class="sxs-lookup"><span data-stu-id="9f822-111">0</span></span>|  
|<span data-ttu-id="9f822-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="9f822-112">Symbolic Name</span></span>|<span data-ttu-id="9f822-113">0</span><span class="sxs-lookup"><span data-stu-id="9f822-113">0</span></span>|  
|<span data-ttu-id="9f822-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="9f822-114">Message Text</span></span>|<span data-ttu-id="9f822-115">必要なサービス証明書の拇印が指定されていません</span><span class="sxs-lookup"><span data-stu-id="9f822-115">Required service certificate thumbprint not specified</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9f822-116">説明</span><span class="sxs-lookup"><span data-stu-id="9f822-116">Explanation</span></span>  
 <span data-ttu-id="9f822-117">WCF 送信ポートのセキュリティ設定に必要なサービス証明書のプロパティが設定されていませんでした。</span><span class="sxs-lookup"><span data-stu-id="9f822-117">You did not set the Service certificate property required for the security settings of a WCF send port.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9f822-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="9f822-118">User Action</span></span>  
 <span data-ttu-id="9f822-119">サービス証明書のプロパティを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9f822-119">Use the following procedure to configure the Service certificate property.</span></span>  
  
#### <a name="to-configure-the-service-certificate-property"></a><span data-ttu-id="9f822-120">サービス証明書プロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="9f822-120">To configure the Service certificate property</span></span>  
  
1.  <span data-ttu-id="9f822-121">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="9f822-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="9f822-122">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="9f822-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="9f822-123">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="9f822-123">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="9f822-124">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="9f822-124">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="9f822-125">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9f822-125">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="9f822-126">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="9f822-126">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="9f822-127">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="9f822-127">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="9f822-128">**WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**セキュリティ**タブです。</span><span class="sxs-lookup"><span data-stu-id="9f822-128">In the **WCF [***transport type***] Transport Properties** dialog box, click the **Security** tab.</span></span>  
  
9. <span data-ttu-id="9f822-129">いることを確認、**サービス証明書**プロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="9f822-129">Ensure that the **Service certificate** property is configured.</span></span>  
  
 <span data-ttu-id="9f822-130">証明書の詳細については、次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f822-130">For additional information on certificates, see the following resource:</span></span>  
  
-   [<span data-ttu-id="9f822-131">WCF アダプターの証明書のインストール</span><span class="sxs-lookup"><span data-stu-id="9f822-131">Installing Certificates for the WCF Adapters</span></span>](../core/installing-certificates-for-the-wcf-adapters.md)