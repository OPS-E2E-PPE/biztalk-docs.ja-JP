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
ms.openlocfilehash: 4e2966a905ea57ed0867a3c3f4c333e88416be9c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292812"
---
# <a name="unable-to-export-configuration"></a><span data-ttu-id="e5151-102">構成をエクスポートできません</span><span class="sxs-lookup"><span data-stu-id="e5151-102">Unable to export configuration</span></span>
## <a name="details"></a><span data-ttu-id="e5151-103">詳細</span><span class="sxs-lookup"><span data-stu-id="e5151-103">Details</span></span>  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="e5151-104">製品名</span><span class="sxs-lookup"><span data-stu-id="e5151-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="e5151-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="e5151-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="e5151-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e5151-106">Event ID</span></span>     |                                         <span data-ttu-id="e5151-107">0</span><span class="sxs-lookup"><span data-stu-id="e5151-107">0</span></span>                                          |
|  <span data-ttu-id="e5151-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="e5151-108">Event Source</span></span>   |                                         <span data-ttu-id="e5151-109">0</span><span class="sxs-lookup"><span data-stu-id="e5151-109">0</span></span>                                          |
|    <span data-ttu-id="e5151-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e5151-110">Component</span></span>    |                                         <span data-ttu-id="e5151-111">0</span><span class="sxs-lookup"><span data-stu-id="e5151-111">0</span></span>                                          |
|  <span data-ttu-id="e5151-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="e5151-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="e5151-113">0</span><span class="sxs-lookup"><span data-stu-id="e5151-113">0</span></span>                                          |
|  <span data-ttu-id="e5151-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="e5151-114">Message Text</span></span>   |                    <span data-ttu-id="e5151-115">構成をファイルにエクスポートすることができません"{0}"</span><span class="sxs-lookup"><span data-stu-id="e5151-115">Unable to export configuration to file "{0}"</span></span>                    |

## <a name="explanation"></a><span data-ttu-id="e5151-116">説明</span><span class="sxs-lookup"><span data-stu-id="e5151-116">Explanation</span></span>  
 <span data-ttu-id="e5151-117">いくつか必要なプロパティが正しく指定されていない、アドレス (URI) およびバインドの種類など。</span><span class="sxs-lookup"><span data-stu-id="e5151-117">Some required properties were not correctly specified, such as Address (URI) and Binding Type.</span></span>  

## <a name="user-action"></a><span data-ttu-id="e5151-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="e5151-118">User Action</span></span>  
 <span data-ttu-id="e5151-119">プロパティが正しいことを確認するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="e5151-119">Use the following procedure to verify properties are correct.</span></span>  

#### <a name="to-verify-properties"></a><span data-ttu-id="e5151-120">プロパティを確認するには</span><span class="sxs-lookup"><span data-stu-id="e5151-120">To verify properties</span></span>  

1. <span data-ttu-id="e5151-121">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="e5151-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="e5151-122">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="e5151-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="e5151-123">アプリケーションを見つけて、トランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="e5151-123">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="e5151-124">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="e5151-124">Right-click the transport name.</span></span>  

5. <span data-ttu-id="e5151-125">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5151-125">Click **Properties**.</span></span>  

6. <span data-ttu-id="e5151-126">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="e5151-126">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="e5151-127">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="e5151-127">Click **Configure**.</span></span>  

8. <span data-ttu-id="e5151-128">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**インポート/エクスポート**タブ。</span><span class="sxs-lookup"><span data-stu-id="e5151-128">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Import/Export** tab.</span></span>  

9. <span data-ttu-id="e5151-129">**[エクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5151-129">Click **Export**.</span></span>  

10. <span data-ttu-id="e5151-130">必要なプロパティが正しく指定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e5151-130">Ensure the required properties have been correctly specified.</span></span> <span data-ttu-id="e5151-131">アドレス (URI) のスキームでは、バインドの種類を正しく一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5151-131">The scheme of the Address (URI) must correctly match the Binding type.</span></span>
