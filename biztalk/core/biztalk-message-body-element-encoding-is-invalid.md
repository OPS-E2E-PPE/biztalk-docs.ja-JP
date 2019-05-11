---
title: BizTalk メッセージ本文要素のエンコードが無効です |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b407e5c3-4655-4b2f-8ecc-30eb080ec47c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c468679853f450695f6fa2194c303be5438a4e90
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357985"
---
# <a name="biztalk-message-body-element-encoding-is-invalid"></a><span data-ttu-id="3bafe-102">BizTalk メッセージ本文要素のエンコードは無効です</span><span class="sxs-lookup"><span data-stu-id="3bafe-102">BizTalk message body element encoding is invalid</span></span>
## <a name="details"></a><span data-ttu-id="3bafe-103">詳細</span><span class="sxs-lookup"><span data-stu-id="3bafe-103">Details</span></span>  
  
|                 |                                                                                                                |
|-----------------|----------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="3bafe-104">製品名</span><span class="sxs-lookup"><span data-stu-id="3bafe-104">Product Name</span></span>   |               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]               |
| <span data-ttu-id="3bafe-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="3bafe-105">Product Version</span></span> |                           [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                           |
|    <span data-ttu-id="3bafe-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="3bafe-106">Event ID</span></span>     |                                                       <span data-ttu-id="3bafe-107">0</span><span class="sxs-lookup"><span data-stu-id="3bafe-107">0</span></span>                                                        |
|  <span data-ttu-id="3bafe-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="3bafe-108">Event Source</span></span>   |                                                       <span data-ttu-id="3bafe-109">0</span><span class="sxs-lookup"><span data-stu-id="3bafe-109">0</span></span>                                                        |
|    <span data-ttu-id="3bafe-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3bafe-110">Component</span></span>    |                                                       <span data-ttu-id="3bafe-111">0</span><span class="sxs-lookup"><span data-stu-id="3bafe-111">0</span></span>                                                        |
|  <span data-ttu-id="3bafe-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="3bafe-112">Symbolic Name</span></span>  |                                                       <span data-ttu-id="3bafe-113">0</span><span class="sxs-lookup"><span data-stu-id="3bafe-113">0</span></span>                                                        |
|  <span data-ttu-id="3bafe-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="3bafe-114">Message Text</span></span>   | <span data-ttu-id="3bafe-115">BizTalk メッセージ本文要素のエンコード"{0}"が無効です。</span><span class="sxs-lookup"><span data-stu-id="3bafe-115">BizTalk message body element encoding "{0}" is invalid.</span></span> <span data-ttu-id="3bafe-116">エンコードが必要です"xml"、"base64"、"hex"、または"string"。</span><span class="sxs-lookup"><span data-stu-id="3bafe-116">Expected encoding: "xml", "base64", "hex", or "string"</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="3bafe-117">説明</span><span class="sxs-lookup"><span data-stu-id="3bafe-117">Explanation</span></span>  
 <span data-ttu-id="3bafe-118">このエラーは、送信メッセージは BizTalk 本文テンプレート オプションの使用を示します。ただし、BizTalk 本文に指定したエンコードの種類が無効です。</span><span class="sxs-lookup"><span data-stu-id="3bafe-118">This error indicates the use of the BizTalk body template option for the outgoing messages; however, the encoding type specified for the BizTalk body is invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3bafe-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="3bafe-119">User Action</span></span>  
 <span data-ttu-id="3bafe-120">エンコードの種類を構成するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="3bafe-120">Use the following procedure to configure the encoding type.</span></span>  
  
#### <a name="to-configure-the-encoding-type"></a><span data-ttu-id="3bafe-121">エンコードの種類を構成するには</span><span class="sxs-lookup"><span data-stu-id="3bafe-121">To configure the encoding type</span></span>  
  
1. <span data-ttu-id="3bafe-122">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="3bafe-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="3bafe-123">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="3bafe-123">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="3bafe-124">アプリケーションを見つけて、トランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="3bafe-124">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="3bafe-125">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="3bafe-125">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="3bafe-126">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3bafe-126">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="3bafe-127">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="3bafe-127">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="3bafe-128">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="3bafe-128">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="3bafe-129">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**メッセージ**タブ。</span><span class="sxs-lookup"><span data-stu-id="3bafe-129">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Messages** tab.</span></span>  
  
9. <span data-ttu-id="3bafe-130">**送信 WCF メッセージ本文**セクションで、、**テンプレート--テンプレートで指定されたコンテンツ**ラジオ ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3bafe-130">In the **Outbound WCF message body** section, click the **Template – Content specified by template** radio button.</span></span> <span data-ttu-id="3bafe-131">**XML**テキスト ボックスに、BizTalk 本文の形式である必要があります</span><span class="sxs-lookup"><span data-stu-id="3bafe-131">In the **XML** text box, the format of the BizTalk body should be</span></span>   
    <span data-ttu-id="3bafe-132">\<**bts-msg-body xmlns="<http://www.microsoft.com/schemas/bts2007>" encoding="[xml&#124;base64&#124;hex&#124;string]"/**\>  (valid values, which are case-sensitive, for encoding are xml&#124;base64&#124;hex&#124;string)</span><span class="sxs-lookup"><span data-stu-id="3bafe-132">\<**bts-msg-body xmlns="<http://www.microsoft.com/schemas/bts2007>" encoding="[xml&#124;base64&#124;hex&#124;string]"/**\>  (valid values, which are case-sensitive, for encoding are xml&#124;base64&#124;hex&#124;string)</span></span>