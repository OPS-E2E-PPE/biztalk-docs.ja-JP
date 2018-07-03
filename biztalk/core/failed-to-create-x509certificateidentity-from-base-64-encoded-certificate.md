---
title: Base 64 でエンコードされた証明書から X509CertificateIdentity を作成できませんでした |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a13112bd-e0e8-4b49-ad2f-ea82b2e8162f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00d92c9ca3f7de567de915241d5950f5b93c06da
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995243"
---
# <a name="failed-to-create-x509certificateidentity-from-base-64-encoded-certificate"></a><span data-ttu-id="3afe9-102">Base-64 でエンコードされた証明書から X509CertificateIdentity を作成できませんでした</span><span class="sxs-lookup"><span data-stu-id="3afe9-102">Failed to create X509CertificateIdentity from base-64 encoded certificate</span></span>
## <a name="details"></a><span data-ttu-id="3afe9-103">詳細</span><span class="sxs-lookup"><span data-stu-id="3afe9-103">Details</span></span>  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="3afe9-104">製品名</span><span class="sxs-lookup"><span data-stu-id="3afe9-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="3afe9-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="3afe9-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="3afe9-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="3afe9-106">Event ID</span></span>     |                                         <span data-ttu-id="3afe9-107">0</span><span class="sxs-lookup"><span data-stu-id="3afe9-107">0</span></span>                                          |
|  <span data-ttu-id="3afe9-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="3afe9-108">Event Source</span></span>   |                                         <span data-ttu-id="3afe9-109">0</span><span class="sxs-lookup"><span data-stu-id="3afe9-109">0</span></span>                                          |
|    <span data-ttu-id="3afe9-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3afe9-110">Component</span></span>    |                                         <span data-ttu-id="3afe9-111">0</span><span class="sxs-lookup"><span data-stu-id="3afe9-111">0</span></span>                                          |
|  <span data-ttu-id="3afe9-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="3afe9-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="3afe9-113">0</span><span class="sxs-lookup"><span data-stu-id="3afe9-113">0</span></span>                                          |
|  <span data-ttu-id="3afe9-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="3afe9-114">Message Text</span></span>   |     <span data-ttu-id="3afe9-115">Base-64 でエンコードされた証明書から X509CertificateIdentity を作成できませんでした</span><span class="sxs-lookup"><span data-stu-id="3afe9-115">Failed to create X509CertificateIdentity from base-64 encoded certificate</span></span>      |

## <a name="explanation"></a><span data-ttu-id="3afe9-116">説明</span><span class="sxs-lookup"><span data-stu-id="3afe9-116">Explanation</span></span>  
 <span data-ttu-id="3afe9-117">このエラーは、証明書設定が無効なために、アダプターで X509Certificate エンドポイント ID の作成に失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="3afe9-117">This error indicates the adapter failed to create the X509Certificate endpoint identity because of an invalid certificate setting.</span></span>  

## <a name="user-action"></a><span data-ttu-id="3afe9-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="3afe9-118">User Action</span></span>  
 <span data-ttu-id="3afe9-119">証明書を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3afe9-119">Use the following procedure to configure certificates.</span></span>  

#### <a name="to-configure-certificates"></a><span data-ttu-id="3afe9-120">証明書を構成するには</span><span class="sxs-lookup"><span data-stu-id="3afe9-120">To configure certificates</span></span>  

1. <span data-ttu-id="3afe9-121">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="3afe9-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="3afe9-122">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="3afe9-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="3afe9-123">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="3afe9-123">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="3afe9-124">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="3afe9-124">Right-click the transport name.</span></span>  

5. <span data-ttu-id="3afe9-125">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3afe9-125">Click **Properties**.</span></span>  

6. <span data-ttu-id="3afe9-126">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="3afe9-126">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="3afe9-127">クリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="3afe9-127">Click **Configure**.</span></span>  

8. <span data-ttu-id="3afe9-128">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**セキュリティ**タブ。</span><span class="sxs-lookup"><span data-stu-id="3afe9-128">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Security** tab.</span></span>  

9. <span data-ttu-id="3afe9-129">設定が正しいことを確認、**クライアント証明書の拇印**と**サービス証明書の拇印**します。</span><span class="sxs-lookup"><span data-stu-id="3afe9-129">Ensure that the settings are correct for the **Client Certificate Thumbprint** and the **Service Certificate Thumbprint**.</span></span>
