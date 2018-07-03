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
ms.openlocfilehash: 4bea510fba1a9c4ab972229042e7af1e22cc2ad8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993475"
---
# <a name="required-client-certificate-thumbprint-not-specified"></a><span data-ttu-id="63d2b-102">必要なクライアント証明書の拇印が指定されていません</span><span class="sxs-lookup"><span data-stu-id="63d2b-102">Required client certificate thumbprint not specified</span></span>
## <a name="details"></a><span data-ttu-id="63d2b-103">詳細</span><span class="sxs-lookup"><span data-stu-id="63d2b-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="63d2b-104">製品名</span><span class="sxs-lookup"><span data-stu-id="63d2b-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="63d2b-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="63d2b-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="63d2b-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="63d2b-106">Event ID</span></span>     |                                         <span data-ttu-id="63d2b-107">0</span><span class="sxs-lookup"><span data-stu-id="63d2b-107">0</span></span>                                          |
|  <span data-ttu-id="63d2b-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="63d2b-108">Event Source</span></span>   |                                         <span data-ttu-id="63d2b-109">0</span><span class="sxs-lookup"><span data-stu-id="63d2b-109">0</span></span>                                          |
|    <span data-ttu-id="63d2b-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="63d2b-110">Component</span></span>    |                                         <span data-ttu-id="63d2b-111">0</span><span class="sxs-lookup"><span data-stu-id="63d2b-111">0</span></span>                                          |
|  <span data-ttu-id="63d2b-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="63d2b-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="63d2b-113">0</span><span class="sxs-lookup"><span data-stu-id="63d2b-113">0</span></span>                                          |
|  <span data-ttu-id="63d2b-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="63d2b-114">Message Text</span></span>   |               <span data-ttu-id="63d2b-115">必要なクライアント証明書の拇印が指定されていません。</span><span class="sxs-lookup"><span data-stu-id="63d2b-115">Required client certificate thumbprint not specified.</span></span>                |
  
## <a name="explanation"></a><span data-ttu-id="63d2b-116">説明</span><span class="sxs-lookup"><span data-stu-id="63d2b-116">Explanation</span></span>  
 <span data-ttu-id="63d2b-117">WCF 送信ポートのセキュリティ設定に必要なクライアント証明書のプロパティが設定されていませんでした。</span><span class="sxs-lookup"><span data-stu-id="63d2b-117">You did not set the Client certificate property required for the security settings of a WCF send port.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="63d2b-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="63d2b-118">User Action</span></span>  
 <span data-ttu-id="63d2b-119">WCF 送信ポートのセキュリティ設定を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="63d2b-119">Use the following procedure to configure security settings of a WCF send port.</span></span>  
  
#### <a name="to-configure-security-settings"></a><span data-ttu-id="63d2b-120">セキュリティ設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="63d2b-120">To configure security settings</span></span>  
  
1. <span data-ttu-id="63d2b-121">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="63d2b-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="63d2b-122">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="63d2b-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="63d2b-123">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="63d2b-123">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="63d2b-124">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="63d2b-124">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="63d2b-125">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63d2b-125">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="63d2b-126">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="63d2b-126">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="63d2b-127">クリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="63d2b-127">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="63d2b-128">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**セキュリティ**タブ。</span><span class="sxs-lookup"><span data-stu-id="63d2b-128">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Security** tab.</span></span>  
  
9. <span data-ttu-id="63d2b-129">いることを確認、**クライアント証明書**プロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="63d2b-129">Ensure that the **Client certificate** property is configured.</span></span>  
  
   <span data-ttu-id="63d2b-130">証明書の詳細については、次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63d2b-130">For additional information on certificates, see the following resource:</span></span>  
  
-   [<span data-ttu-id="63d2b-131">WCF アダプターの証明書のインストール</span><span class="sxs-lookup"><span data-stu-id="63d2b-131">Installing Certificates for the WCF Adapters</span></span>](../core/installing-certificates-for-the-wcf-adapters.md)