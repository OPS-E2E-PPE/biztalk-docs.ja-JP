---
title: クライアント証明書の拇印が指定されていないために必要な |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 19307bdb-29d7-4a79-9472-dda24dd8b263
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ec653bcfaf3316d0c41c21395a711fa88793df4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65268084"
---
# <a name="required-client-certificate-thumbprint-not-specified"></a><span data-ttu-id="6fda7-102">必要なクライアント証明書の拇印が指定されていません</span><span class="sxs-lookup"><span data-stu-id="6fda7-102">Required client certificate thumbprint not specified</span></span>
## <a name="details"></a><span data-ttu-id="6fda7-103">詳細</span><span class="sxs-lookup"><span data-stu-id="6fda7-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="6fda7-104">製品名</span><span class="sxs-lookup"><span data-stu-id="6fda7-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="6fda7-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="6fda7-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="6fda7-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="6fda7-106">Event ID</span></span>     |                                         <span data-ttu-id="6fda7-107">0</span><span class="sxs-lookup"><span data-stu-id="6fda7-107">0</span></span>                                          |
|  <span data-ttu-id="6fda7-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="6fda7-108">Event Source</span></span>   |                                         <span data-ttu-id="6fda7-109">0</span><span class="sxs-lookup"><span data-stu-id="6fda7-109">0</span></span>                                          |
|    <span data-ttu-id="6fda7-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6fda7-110">Component</span></span>    |                                         <span data-ttu-id="6fda7-111">0</span><span class="sxs-lookup"><span data-stu-id="6fda7-111">0</span></span>                                          |
|  <span data-ttu-id="6fda7-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="6fda7-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="6fda7-113">0</span><span class="sxs-lookup"><span data-stu-id="6fda7-113">0</span></span>                                          |
|  <span data-ttu-id="6fda7-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="6fda7-114">Message Text</span></span>   |               <span data-ttu-id="6fda7-115">必要なクライアント証明書の拇印が指定されていません。</span><span class="sxs-lookup"><span data-stu-id="6fda7-115">Required client certificate thumbprint not specified.</span></span>                |
  
## <a name="explanation"></a><span data-ttu-id="6fda7-116">説明</span><span class="sxs-lookup"><span data-stu-id="6fda7-116">Explanation</span></span>  
 <span data-ttu-id="6fda7-117">クライアントが WCF 送信ポートのセキュリティ設定に必要な証明書プロパティしない設定でした。</span><span class="sxs-lookup"><span data-stu-id="6fda7-117">You did not set the Client certificate property required for the security settings of a WCF send port.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6fda7-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="6fda7-118">User Action</span></span>  
 <span data-ttu-id="6fda7-119">WCF のセキュリティ設定を構成する次の手順に従っては送信ポートです。</span><span class="sxs-lookup"><span data-stu-id="6fda7-119">Use the following procedure to configure security settings of a WCF send port.</span></span>  
  
#### <a name="to-configure-security-settings"></a><span data-ttu-id="6fda7-120">セキュリティ設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="6fda7-120">To configure security settings</span></span>  
  
1. <span data-ttu-id="6fda7-121">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="6fda7-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="6fda7-122">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="6fda7-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="6fda7-123">アプリケーションを見つけて、トランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="6fda7-123">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="6fda7-124">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="6fda7-124">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="6fda7-125">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6fda7-125">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="6fda7-126">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="6fda7-126">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="6fda7-127">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="6fda7-127">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="6fda7-128">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**セキュリティ**タブ。</span><span class="sxs-lookup"><span data-stu-id="6fda7-128">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Security** tab.</span></span>  
  
9. <span data-ttu-id="6fda7-129">いることを確認、**クライアント証明書**プロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="6fda7-129">Ensure that the **Client certificate** property is configured.</span></span>  
  
   <span data-ttu-id="6fda7-130">証明書の詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fda7-130">For additional information on certificates, see the following resource:</span></span>  
  
-   [<span data-ttu-id="6fda7-131">WCF アダプターの証明書のインストール</span><span class="sxs-lookup"><span data-stu-id="6fda7-131">Installing Certificates for the WCF Adapters</span></span>](../core/installing-certificates-for-the-wcf-adapters.md)