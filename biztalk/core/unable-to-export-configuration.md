---
title: 構成をエクスポートできません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 64f09af4-00a0-47cb-889e-d9aeb7266eb2
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5bb3eb733dcf7c7199282ad4e5512e8d590e8c41
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018784"
---
# <a name="unable-to-export-configuration"></a><span data-ttu-id="6f582-102">構成をエクスポートできません</span><span class="sxs-lookup"><span data-stu-id="6f582-102">Unable to export configuration</span></span>
## <a name="details"></a><span data-ttu-id="6f582-103">詳細</span><span class="sxs-lookup"><span data-stu-id="6f582-103">Details</span></span>  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="6f582-104">製品名</span><span class="sxs-lookup"><span data-stu-id="6f582-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="6f582-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="6f582-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="6f582-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="6f582-106">Event ID</span></span>     |                                         <span data-ttu-id="6f582-107">0</span><span class="sxs-lookup"><span data-stu-id="6f582-107">0</span></span>                                          |
|  <span data-ttu-id="6f582-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="6f582-108">Event Source</span></span>   |                                         <span data-ttu-id="6f582-109">0</span><span class="sxs-lookup"><span data-stu-id="6f582-109">0</span></span>                                          |
|    <span data-ttu-id="6f582-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6f582-110">Component</span></span>    |                                         <span data-ttu-id="6f582-111">0</span><span class="sxs-lookup"><span data-stu-id="6f582-111">0</span></span>                                          |
|  <span data-ttu-id="6f582-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="6f582-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="6f582-113">0</span><span class="sxs-lookup"><span data-stu-id="6f582-113">0</span></span>                                          |
|  <span data-ttu-id="6f582-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="6f582-114">Message Text</span></span>   |                    <span data-ttu-id="6f582-115">構成をファイルにエクスポートすることができません"{0}"</span><span class="sxs-lookup"><span data-stu-id="6f582-115">Unable to export configuration to file "{0}"</span></span>                    |

## <a name="explanation"></a><span data-ttu-id="6f582-116">説明</span><span class="sxs-lookup"><span data-stu-id="6f582-116">Explanation</span></span>  
 <span data-ttu-id="6f582-117">[アドレス (URI)] や [バインディングの種類] など、必要なプロパティの一部が適切に指定されませんでした。</span><span class="sxs-lookup"><span data-stu-id="6f582-117">Some required properties were not correctly specified, such as Address (URI) and Binding Type.</span></span>  

## <a name="user-action"></a><span data-ttu-id="6f582-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="6f582-118">User Action</span></span>  
 <span data-ttu-id="6f582-119">プロパティが正しいことを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6f582-119">Use the following procedure to verify properties are correct.</span></span>  

#### <a name="to-verify-properties"></a><span data-ttu-id="6f582-120">プロパティを確認するには</span><span class="sxs-lookup"><span data-stu-id="6f582-120">To verify properties</span></span>  

1. <span data-ttu-id="6f582-121">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="6f582-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="6f582-122">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="6f582-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="6f582-123">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="6f582-123">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="6f582-124">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="6f582-124">Right-click the transport name.</span></span>  

5. <span data-ttu-id="6f582-125">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f582-125">Click **Properties**.</span></span>  

6. <span data-ttu-id="6f582-126">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="6f582-126">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="6f582-127">クリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="6f582-127">Click **Configure**.</span></span>  

8. <span data-ttu-id="6f582-128">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**インポート/エクスポート**タブ。</span><span class="sxs-lookup"><span data-stu-id="6f582-128">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Import/Export** tab.</span></span>  

9. <span data-ttu-id="6f582-129">**[エクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f582-129">Click **Export**.</span></span>  

10. <span data-ttu-id="6f582-130">必要なプロパティが適切に指定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6f582-130">Ensure the required properties have been correctly specified.</span></span> <span data-ttu-id="6f582-131">[アドレス (URI)] のスキームは、[バインディングの種類] と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f582-131">The scheme of the Address (URI) must correctly match the Binding type.</span></span>
