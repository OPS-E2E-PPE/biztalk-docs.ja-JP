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
ms.openlocfilehash: fa8ea6b0eb9b1b6b308206dc2488a5aaf4276e0a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388143"
---
# <a name="failed-to-create-x509certificateidentity-from-base-64-encoded-certificate"></a><span data-ttu-id="feb29-102">Base-64 でエンコードされた証明書から X509CertificateIdentity を作成できませんでした</span><span class="sxs-lookup"><span data-stu-id="feb29-102">Failed to create X509CertificateIdentity from base-64 encoded certificate</span></span>
## <a name="details"></a><span data-ttu-id="feb29-103">詳細</span><span class="sxs-lookup"><span data-stu-id="feb29-103">Details</span></span>  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="feb29-104">製品名</span><span class="sxs-lookup"><span data-stu-id="feb29-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="feb29-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="feb29-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="feb29-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="feb29-106">Event ID</span></span>     |                                         <span data-ttu-id="feb29-107">0</span><span class="sxs-lookup"><span data-stu-id="feb29-107">0</span></span>                                          |
|  <span data-ttu-id="feb29-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="feb29-108">Event Source</span></span>   |                                         <span data-ttu-id="feb29-109">0</span><span class="sxs-lookup"><span data-stu-id="feb29-109">0</span></span>                                          |
|    <span data-ttu-id="feb29-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="feb29-110">Component</span></span>    |                                         <span data-ttu-id="feb29-111">0</span><span class="sxs-lookup"><span data-stu-id="feb29-111">0</span></span>                                          |
|  <span data-ttu-id="feb29-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="feb29-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="feb29-113">0</span><span class="sxs-lookup"><span data-stu-id="feb29-113">0</span></span>                                          |
|  <span data-ttu-id="feb29-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="feb29-114">Message Text</span></span>   |     <span data-ttu-id="feb29-115">Base-64 でエンコードされた証明書から X509CertificateIdentity を作成できませんでした</span><span class="sxs-lookup"><span data-stu-id="feb29-115">Failed to create X509CertificateIdentity from base-64 encoded certificate</span></span>      |

## <a name="explanation"></a><span data-ttu-id="feb29-116">説明</span><span class="sxs-lookup"><span data-stu-id="feb29-116">Explanation</span></span>  
 <span data-ttu-id="feb29-117">このエラーは、アダプターが、無効な証明書の設定が原因で X509Certificate エンドポイント id を作成できませんでしたを示します。</span><span class="sxs-lookup"><span data-stu-id="feb29-117">This error indicates the adapter failed to create the X509Certificate endpoint identity because of an invalid certificate setting.</span></span>  

## <a name="user-action"></a><span data-ttu-id="feb29-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="feb29-118">User Action</span></span>  
 <span data-ttu-id="feb29-119">証明書を構成するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="feb29-119">Use the following procedure to configure certificates.</span></span>  

#### <a name="to-configure-certificates"></a><span data-ttu-id="feb29-120">証明書の構成</span><span class="sxs-lookup"><span data-stu-id="feb29-120">To configure certificates</span></span>  

1. <span data-ttu-id="feb29-121">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="feb29-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="feb29-122">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="feb29-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="feb29-123">アプリケーションを見つけて、トランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="feb29-123">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="feb29-124">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="feb29-124">Right-click the transport name.</span></span>  

5. <span data-ttu-id="feb29-125">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="feb29-125">Click **Properties**.</span></span>  

6. <span data-ttu-id="feb29-126">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="feb29-126">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="feb29-127">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="feb29-127">Click **Configure**.</span></span>  

8. <span data-ttu-id="feb29-128">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**セキュリティ**タブ。</span><span class="sxs-lookup"><span data-stu-id="feb29-128">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Security** tab.</span></span>  

9. <span data-ttu-id="feb29-129">設定が正しいことを確認、**クライアント証明書の拇印**と**サービス証明書の拇印**します。</span><span class="sxs-lookup"><span data-stu-id="feb29-129">Ensure that the settings are correct for the **Client Certificate Thumbprint** and the **Service Certificate Thumbprint**.</span></span>
