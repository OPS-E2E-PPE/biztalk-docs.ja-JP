---
title: 証明書参照から X509CertificateIdentity を作成できませんでした |。Microsoft Docs
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
ms.openlocfilehash: b991f9acb2b5cc193d24d36e1a5de8650e7af72b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988931"
---
# <a name="failed-to-create-x509certificateidentity-from-certificate-reference"></a><span data-ttu-id="4ee66-102">証明書参照から X509CertificateIdentity を作成できませんでした</span><span class="sxs-lookup"><span data-stu-id="4ee66-102">Failed to create X509CertificateIdentity from certificate reference</span></span>
## <a name="details"></a><span data-ttu-id="4ee66-103">詳細</span><span class="sxs-lookup"><span data-stu-id="4ee66-103">Details</span></span>  

|                 |                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="4ee66-104">製品名</span><span class="sxs-lookup"><span data-stu-id="4ee66-104">Product Name</span></span>   |                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                             |
| <span data-ttu-id="4ee66-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="4ee66-105">Product Version</span></span> |                                         [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                         |
|    <span data-ttu-id="4ee66-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4ee66-106">Event ID</span></span>     |                                                                     <span data-ttu-id="4ee66-107">0</span><span class="sxs-lookup"><span data-stu-id="4ee66-107">0</span></span>                                                                      |
|  <span data-ttu-id="4ee66-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="4ee66-108">Event Source</span></span>   |                                                                     <span data-ttu-id="4ee66-109">0</span><span class="sxs-lookup"><span data-stu-id="4ee66-109">0</span></span>                                                                      |
|    <span data-ttu-id="4ee66-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="4ee66-110">Component</span></span>    |                                                                     <span data-ttu-id="4ee66-111">0</span><span class="sxs-lookup"><span data-stu-id="4ee66-111">0</span></span>                                                                      |
|  <span data-ttu-id="4ee66-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="4ee66-112">Symbolic Name</span></span>  |                                                                     <span data-ttu-id="4ee66-113">0</span><span class="sxs-lookup"><span data-stu-id="4ee66-113">0</span></span>                                                                      |
|  <span data-ttu-id="4ee66-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="4ee66-114">Message Text</span></span>   | <span data-ttu-id="4ee66-115">証明書参照から X509CertificateIdentity を作成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="4ee66-115">Failed to create X509CertificateIdentity from certificate reference.</span></span> <span data-ttu-id="4ee66-116">(StoreName ={0}、StoreLocation ={1}、X509FindType ={2}、FindValue ="{3}")</span><span class="sxs-lookup"><span data-stu-id="4ee66-116">(StoreName={0}, StoreLocation={1}, X509FindType={2}, FindValue="{3}")</span></span> |

## <a name="explanation"></a><span data-ttu-id="4ee66-117">説明</span><span class="sxs-lookup"><span data-stu-id="4ee66-117">Explanation</span></span>  
 <span data-ttu-id="4ee66-118">このエラーは、アダプターで、エンドポイント ID 構成に指定されている X509Certificate の作成に失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="4ee66-118">This error indicates the adapter failed to create the X509Certificate specified in the endpoint identity configuration.</span></span>  

## <a name="user-action"></a><span data-ttu-id="4ee66-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="4ee66-119">User Action</span></span>  
 <span data-ttu-id="4ee66-120">証明書参照設定を確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4ee66-120">Use the following procedure to verify the certificate reference settings.</span></span>  

#### <a name="to-configure-the-certificate-reference-settings"></a><span data-ttu-id="4ee66-121">証明書参照設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="4ee66-121">To configure the certificate reference settings</span></span>  

1. <span data-ttu-id="4ee66-122">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="4ee66-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="4ee66-123">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="4ee66-123">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="4ee66-124">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="4ee66-124">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="4ee66-125">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="4ee66-125">Right-click the transport name.</span></span>  

5. <span data-ttu-id="4ee66-126">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ee66-126">Click **Properties**.</span></span>  

6. <span data-ttu-id="4ee66-127">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="4ee66-127">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="4ee66-128">クリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="4ee66-128">Click **Configure**.</span></span>  

8. <span data-ttu-id="4ee66-129">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブ。</span><span class="sxs-lookup"><span data-stu-id="4ee66-129">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **General** tab.</span></span>  

9. <span data-ttu-id="4ee66-130">**エンドポイント Id**セクションで、**を編集します。**</span><span class="sxs-lookup"><span data-stu-id="4ee66-130">In the **Endpoint Identity** section, click **Edit.**</span></span>  

10. <span data-ttu-id="4ee66-131">**Id エディター**  ダイアログ ボックスで、いることを確認、**証明書参照**設定が無効です。</span><span class="sxs-lookup"><span data-stu-id="4ee66-131">In the **Identity Editor** dialog box, ensure that the **Certificate Reference** settings are valid.</span></span>
