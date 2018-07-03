---
title: 受信本文のパス式に一致することができません。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c0382348-96c4-414c-9dda-a390d491dee8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69ae115eef4440490fd4fc5ed4f40c5600b6cdb2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016975"
---
# <a name="unable-to-find-match-for-inbound-body-path-expression"></a><span data-ttu-id="cb97f-102">受信本文のパス式に一致する内容が見つかりません</span><span class="sxs-lookup"><span data-stu-id="cb97f-102">Unable to find match for inbound body path expression</span></span>
## <a name="details"></a><span data-ttu-id="cb97f-103">詳細</span><span class="sxs-lookup"><span data-stu-id="cb97f-103">Details</span></span>  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="cb97f-104">製品名</span><span class="sxs-lookup"><span data-stu-id="cb97f-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="cb97f-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="cb97f-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="cb97f-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="cb97f-106">Event ID</span></span>     |                                         <span data-ttu-id="cb97f-107">0</span><span class="sxs-lookup"><span data-stu-id="cb97f-107">0</span></span>                                          |
|  <span data-ttu-id="cb97f-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="cb97f-108">Event Source</span></span>   |                                         <span data-ttu-id="cb97f-109">0</span><span class="sxs-lookup"><span data-stu-id="cb97f-109">0</span></span>                                          |
|    <span data-ttu-id="cb97f-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="cb97f-110">Component</span></span>    |                                         <span data-ttu-id="cb97f-111">0</span><span class="sxs-lookup"><span data-stu-id="cb97f-111">0</span></span>                                          |
|  <span data-ttu-id="cb97f-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="cb97f-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="cb97f-113">0</span><span class="sxs-lookup"><span data-stu-id="cb97f-113">0</span></span>                                          |
|  <span data-ttu-id="cb97f-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="cb97f-114">Message Text</span></span>   |       <span data-ttu-id="cb97f-115">受信本文のパス式の一致が見つかりません"{0}"メッセージ</span><span class="sxs-lookup"><span data-stu-id="cb97f-115">Unable to find match for inbound body path expression "{0}" in message</span></span>       |

## <a name="explanation"></a><span data-ttu-id="cb97f-116">説明</span><span class="sxs-lookup"><span data-stu-id="cb97f-116">Explanation</span></span>  
 <span data-ttu-id="cb97f-117">受信メッセージで実行された本文のパス式は、一致が返されませんでした。</span><span class="sxs-lookup"><span data-stu-id="cb97f-117">The body path expression executed on the incoming message did not return any match.</span></span>  

## <a name="user-action"></a><span data-ttu-id="cb97f-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="cb97f-118">User Action</span></span>  
 <span data-ttu-id="cb97f-119">本文のパス式が正しいこと、および受信メッセージのデータが正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="cb97f-119">Make sure that body path expression is correct, and the incoming message has the correct data.</span></span>  

1. <span data-ttu-id="cb97f-120">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="cb97f-120">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="cb97f-121">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="cb97f-121">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="cb97f-122">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="cb97f-122">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="cb97f-123">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="cb97f-123">Right-click the transport name.</span></span>  

5. <span data-ttu-id="cb97f-124">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb97f-124">Click **Properties**.</span></span>  

6. <span data-ttu-id="cb97f-125">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="cb97f-125">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="cb97f-126">クリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="cb97f-126">Click **Configure**.</span></span>  

8. <span data-ttu-id="cb97f-127">Wcf **[**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**メッセージ**タブ。</span><span class="sxs-lookup"><span data-stu-id="cb97f-127">In the WCF **[**<em>transport type</em>**] Transport Properties** dialog box, click the **Messages** tab.</span></span>  

9. <span data-ttu-id="cb97f-128">**受信 BizTalk メッセージ本文**セクションでの情報を確認、**本文のパス式**します。</span><span class="sxs-lookup"><span data-stu-id="cb97f-128">In the **Inbound BizTalk message body** section, check the information for **Body path expression**.</span></span>
