---
title: 証明書参照から X509CertificateIdentity を作成できませんでした |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a3acee8e-c035-4e58-8bfc-397885b4d185
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c6bb03698010d667b27334f17fa7270de845c68
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246066"
---
# <a name="failed-to-create-x509certificateidentity-from-certificate-reference"></a><span data-ttu-id="64912-102">証明書参照から X509CertificateIdentity を作成できませんでした</span><span class="sxs-lookup"><span data-stu-id="64912-102">Failed to create X509CertificateIdentity from certificate reference</span></span>
## <a name="details"></a><span data-ttu-id="64912-103">詳細</span><span class="sxs-lookup"><span data-stu-id="64912-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="64912-104">製品名</span><span class="sxs-lookup"><span data-stu-id="64912-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="64912-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="64912-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="64912-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="64912-106">Event ID</span></span>|<span data-ttu-id="64912-107">0</span><span class="sxs-lookup"><span data-stu-id="64912-107">0</span></span>|  
|<span data-ttu-id="64912-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="64912-108">Event Source</span></span>|<span data-ttu-id="64912-109">0</span><span class="sxs-lookup"><span data-stu-id="64912-109">0</span></span>|  
|<span data-ttu-id="64912-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="64912-110">Component</span></span>|<span data-ttu-id="64912-111">0</span><span class="sxs-lookup"><span data-stu-id="64912-111">0</span></span>|  
|<span data-ttu-id="64912-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="64912-112">Symbolic Name</span></span>|<span data-ttu-id="64912-113">0</span><span class="sxs-lookup"><span data-stu-id="64912-113">0</span></span>|  
|<span data-ttu-id="64912-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="64912-114">Message Text</span></span>|<span data-ttu-id="64912-115">証明書参照から X509CertificateIdentity を作成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="64912-115">Failed to create X509CertificateIdentity from certificate reference.</span></span> <span data-ttu-id="64912-116">(StoreName = {0}、StoreLocation = \  X509FindType = \ {2 \}、FindValue ="\ {3\}")</span><span class="sxs-lookup"><span data-stu-id="64912-116">(StoreName={0}, StoreLocation={1}, X509FindType={2}, FindValue="{3}")</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="64912-117">説明</span><span class="sxs-lookup"><span data-stu-id="64912-117">Explanation</span></span>  
 <span data-ttu-id="64912-118">このエラーは、アダプターで、エンドポイント ID 構成に指定されている X509Certificate の作成に失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="64912-118">This error indicates the adapter failed to create the X509Certificate specified in the endpoint identity configuration.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="64912-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="64912-119">User Action</span></span>  
 <span data-ttu-id="64912-120">証明書参照設定を確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="64912-120">Use the following procedure to verify the certificate reference settings.</span></span>  
  
#### <a name="to-configure-the-certificate-reference-settings"></a><span data-ttu-id="64912-121">証明書参照設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="64912-121">To configure the certificate reference settings</span></span>  
  
1.  <span data-ttu-id="64912-122">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="64912-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="64912-123">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="64912-123">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="64912-124">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="64912-124">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="64912-125">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="64912-125">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="64912-126">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64912-126">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="64912-127">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="64912-127">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="64912-128">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="64912-128">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="64912-129">**WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブです。</span><span class="sxs-lookup"><span data-stu-id="64912-129">In the **WCF [***transport type***] Transport Properties** dialog box, click the **General** tab.</span></span>  
  
9. <span data-ttu-id="64912-130">**エンドポイント Id**セクションで、**を編集します。**</span><span class="sxs-lookup"><span data-stu-id="64912-130">In the **Endpoint Identity** section, click **Edit.**</span></span>  
  
10. <span data-ttu-id="64912-131">**Id エディター**  ダイアログ ボックスで、いることを確認、**証明書参照**設定が有効です。</span><span class="sxs-lookup"><span data-stu-id="64912-131">In the **Identity Editor** dialog box, ensure that the **Certificate Reference** settings are valid.</span></span>