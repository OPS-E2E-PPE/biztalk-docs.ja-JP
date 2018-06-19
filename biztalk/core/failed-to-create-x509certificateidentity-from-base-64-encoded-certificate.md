---
title: Base 64 エンコードされた証明書から X509CertificateIdentity を作成できませんでした |Microsoft ドキュメント
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
ms.openlocfilehash: 31cf07660b939beb3ea1a79fd0f34390f873d5cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246306"
---
# <a name="failed-to-create-x509certificateidentity-from-base-64-encoded-certificate"></a><span data-ttu-id="b3bce-102">Base-64 でエンコードされた証明書から X509CertificateIdentity を作成できませんでした</span><span class="sxs-lookup"><span data-stu-id="b3bce-102">Failed to create X509CertificateIdentity from base-64 encoded certificate</span></span>
## <a name="details"></a><span data-ttu-id="b3bce-103">詳細</span><span class="sxs-lookup"><span data-stu-id="b3bce-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b3bce-104">製品名</span><span class="sxs-lookup"><span data-stu-id="b3bce-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="b3bce-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="b3bce-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="b3bce-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="b3bce-106">Event ID</span></span>|<span data-ttu-id="b3bce-107">0</span><span class="sxs-lookup"><span data-stu-id="b3bce-107">0</span></span>|  
|<span data-ttu-id="b3bce-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="b3bce-108">Event Source</span></span>|<span data-ttu-id="b3bce-109">0</span><span class="sxs-lookup"><span data-stu-id="b3bce-109">0</span></span>|  
|<span data-ttu-id="b3bce-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b3bce-110">Component</span></span>|<span data-ttu-id="b3bce-111">0</span><span class="sxs-lookup"><span data-stu-id="b3bce-111">0</span></span>|  
|<span data-ttu-id="b3bce-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="b3bce-112">Symbolic Name</span></span>|<span data-ttu-id="b3bce-113">0</span><span class="sxs-lookup"><span data-stu-id="b3bce-113">0</span></span>|  
|<span data-ttu-id="b3bce-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="b3bce-114">Message Text</span></span>|<span data-ttu-id="b3bce-115">Base-64 でエンコードされた証明書から X509CertificateIdentity を作成できませんでした</span><span class="sxs-lookup"><span data-stu-id="b3bce-115">Failed to create X509CertificateIdentity from base-64 encoded certificate</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b3bce-116">説明</span><span class="sxs-lookup"><span data-stu-id="b3bce-116">Explanation</span></span>  
 <span data-ttu-id="b3bce-117">このエラーは、証明書設定が無効なために、アダプターで X509Certificate エンドポイント ID の作成に失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="b3bce-117">This error indicates the adapter failed to create the X509Certificate endpoint identity because of an invalid certificate setting.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b3bce-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="b3bce-118">User Action</span></span>  
 <span data-ttu-id="b3bce-119">証明書を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b3bce-119">Use the following procedure to configure certificates.</span></span>  
  
#### <a name="to-configure-certificates"></a><span data-ttu-id="b3bce-120">証明書を構成するには</span><span class="sxs-lookup"><span data-stu-id="b3bce-120">To configure certificates</span></span>  
  
1.  <span data-ttu-id="b3bce-121">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="b3bce-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="b3bce-122">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="b3bce-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="b3bce-123">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="b3bce-123">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="b3bce-124">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="b3bce-124">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="b3bce-125">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3bce-125">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="b3bce-126">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="b3bce-126">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="b3bce-127">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="b3bce-127">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="b3bce-128">**WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**セキュリティ**タブです。</span><span class="sxs-lookup"><span data-stu-id="b3bce-128">In the **WCF [***transport type***] Transport Properties** dialog box, click the **Security** tab.</span></span>  
  
9. <span data-ttu-id="b3bce-129">設定が正しいことを確認、**クライアント証明書の拇印**と**サービス証明書の拇印**です。</span><span class="sxs-lookup"><span data-stu-id="b3bce-129">Ensure that the settings are correct for the **Client Certificate Thumbprint** and the **Service Certificate Thumbprint**.</span></span>