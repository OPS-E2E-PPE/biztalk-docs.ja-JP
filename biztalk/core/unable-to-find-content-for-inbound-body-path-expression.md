---
title: 受信本文のパス式のコンテンツが見つかりません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed294662-a94e-4fbb-b125-878a27107eab
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d935044695d2e9f74e763196c08bd53f8f429d72
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243158"
---
# <a name="unable-to-find-content-for-inbound-body-path-expression"></a><span data-ttu-id="f1b25-102">受信本文のパス式のコンテンツが見つかりません</span><span class="sxs-lookup"><span data-stu-id="f1b25-102">Unable to find content for inbound body path expression</span></span>
## <a name="details"></a><span data-ttu-id="f1b25-103">詳細</span><span class="sxs-lookup"><span data-stu-id="f1b25-103">Details</span></span>  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="f1b25-104">製品名</span><span class="sxs-lookup"><span data-stu-id="f1b25-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="f1b25-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f1b25-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="f1b25-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f1b25-106">Event ID</span></span>     |                                         <span data-ttu-id="f1b25-107">0</span><span class="sxs-lookup"><span data-stu-id="f1b25-107">0</span></span>                                          |
|  <span data-ttu-id="f1b25-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f1b25-108">Event Source</span></span>   |                                         <span data-ttu-id="f1b25-109">0</span><span class="sxs-lookup"><span data-stu-id="f1b25-109">0</span></span>                                          |
|    <span data-ttu-id="f1b25-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f1b25-110">Component</span></span>    |                                         <span data-ttu-id="f1b25-111">0</span><span class="sxs-lookup"><span data-stu-id="f1b25-111">0</span></span>                                          |
|  <span data-ttu-id="f1b25-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f1b25-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="f1b25-113">0</span><span class="sxs-lookup"><span data-stu-id="f1b25-113">0</span></span>                                          |
|  <span data-ttu-id="f1b25-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f1b25-114">Message Text</span></span>   |      <span data-ttu-id="f1b25-115">受信本文のパス式のコンテンツが見つかりません"{0}"メッセージ</span><span class="sxs-lookup"><span data-stu-id="f1b25-115">Unable to find content for inbound body path expression "{0}" in message</span></span>      |

## <a name="explanation"></a><span data-ttu-id="f1b25-116">説明</span><span class="sxs-lookup"><span data-stu-id="f1b25-116">Explanation</span></span>  
 <span data-ttu-id="f1b25-117">ボディ パス式を実行することによって、受信メッセージから抽出されたコンテンツでは、すべてのデータは含まれません。</span><span class="sxs-lookup"><span data-stu-id="f1b25-117">The content extracted from the incoming message by executing the body path expression does not contain any data.</span></span>  

## <a name="user-action"></a><span data-ttu-id="f1b25-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f1b25-118">User Action</span></span>  
 <span data-ttu-id="f1b25-119">ボディ パス式が正しいことと、受信メッセージが適切なデータを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f1b25-119">Make sure that body path expression is correct, and the incoming message has the correct data.</span></span>  

1. <span data-ttu-id="f1b25-120">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="f1b25-120">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="f1b25-121">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="f1b25-121">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="f1b25-122">アプリケーションを見つけて、トランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="f1b25-122">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="f1b25-123">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="f1b25-123">Right-click the transport name.</span></span>  

5. <span data-ttu-id="f1b25-124">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f1b25-124">Click **Properties**.</span></span>  

6. <span data-ttu-id="f1b25-125">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="f1b25-125">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="f1b25-126">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="f1b25-126">Click **Configure**.</span></span>  

8. <span data-ttu-id="f1b25-127">Wcf **[**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**メッセージ**タブ。</span><span class="sxs-lookup"><span data-stu-id="f1b25-127">In the WCF **[**<em>transport type</em>**] Transport Properties** dialog box, click the **Messages** tab.</span></span>  

9. <span data-ttu-id="f1b25-128">**受信 BizTalk メッセージ本文**セクションでの情報を確認、**本文のパス式**します。</span><span class="sxs-lookup"><span data-stu-id="f1b25-128">In the **Inbound BizTalk message body** section, check the information for **Body path expression**.</span></span>
