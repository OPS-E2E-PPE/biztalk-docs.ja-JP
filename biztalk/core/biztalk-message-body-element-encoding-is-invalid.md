---
title: "BizTalk メッセージ本文要素のエンコードが正しくありません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b407e5c3-4655-4b2f-8ecc-30eb080ec47c
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b1835371e5c042d3ddc46558cbf97970f6bfc6c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="biztalk-message-body-element-encoding-is-invalid"></a><span data-ttu-id="4e7d1-102">BizTalk メッセージ本文要素のエンコードは無効です</span><span class="sxs-lookup"><span data-stu-id="4e7d1-102">BizTalk message body element encoding is invalid</span></span>
## <a name="details"></a><span data-ttu-id="4e7d1-103">詳細</span><span class="sxs-lookup"><span data-stu-id="4e7d1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4e7d1-104">製品名</span><span class="sxs-lookup"><span data-stu-id="4e7d1-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="4e7d1-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="4e7d1-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="4e7d1-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4e7d1-106">Event ID</span></span>|<span data-ttu-id="4e7d1-107">0</span><span class="sxs-lookup"><span data-stu-id="4e7d1-107">0</span></span>|  
|<span data-ttu-id="4e7d1-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="4e7d1-108">Event Source</span></span>|<span data-ttu-id="4e7d1-109">0</span><span class="sxs-lookup"><span data-stu-id="4e7d1-109">0</span></span>|  
|<span data-ttu-id="4e7d1-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="4e7d1-110">Component</span></span>|<span data-ttu-id="4e7d1-111">0</span><span class="sxs-lookup"><span data-stu-id="4e7d1-111">0</span></span>|  
|<span data-ttu-id="4e7d1-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="4e7d1-112">Symbolic Name</span></span>|<span data-ttu-id="4e7d1-113">0</span><span class="sxs-lookup"><span data-stu-id="4e7d1-113">0</span></span>|  
|<span data-ttu-id="4e7d1-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="4e7d1-114">Message Text</span></span>|<span data-ttu-id="4e7d1-115">BizTalk メッセージ本文要素のエンコード "{0}" は無効です。</span><span class="sxs-lookup"><span data-stu-id="4e7d1-115">BizTalk message body element encoding "{0}" is invalid.</span></span> <span data-ttu-id="4e7d1-116">エンコーディングが必要です"xml"、"base64"、"hex"、または"string"。</span><span class="sxs-lookup"><span data-stu-id="4e7d1-116">Expected encoding: "xml", "base64", "hex", or "string"</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4e7d1-117">説明</span><span class="sxs-lookup"><span data-stu-id="4e7d1-117">Explanation</span></span>  
 <span data-ttu-id="4e7d1-118">このエラーは、送信メッセージには BizTalk 本文テンプレート オプションが使用されていますが、BizTalk 本文に指定されたエンコーディングの種類は無効であることを示します。</span><span class="sxs-lookup"><span data-stu-id="4e7d1-118">This error indicates the use of the BizTalk body template option for the outgoing messages; however, the encoding type specified for the BizTalk body is invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4e7d1-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="4e7d1-119">User Action</span></span>  
 <span data-ttu-id="4e7d1-120">エンコーディングの種類を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4e7d1-120">Use the following procedure to configure the encoding type.</span></span>  
  
#### <a name="to-configure-the-encoding-type"></a><span data-ttu-id="4e7d1-121">エンコーディングの種類を構成するには</span><span class="sxs-lookup"><span data-stu-id="4e7d1-121">To configure the encoding type</span></span>  
  
1.  <span data-ttu-id="4e7d1-122">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="4e7d1-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="4e7d1-123">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="4e7d1-123">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="4e7d1-124">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="4e7d1-124">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="4e7d1-125">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="4e7d1-125">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="4e7d1-126">**[プロパティ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e7d1-126">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="4e7d1-127">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="4e7d1-127">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="4e7d1-128">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="4e7d1-128">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="4e7d1-129">**WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**メッセージ**タブです。</span><span class="sxs-lookup"><span data-stu-id="4e7d1-129">In the **WCF [***transport type***] Transport Properties** dialog box, click the **Messages** tab.</span></span>  
  
9. <span data-ttu-id="4e7d1-130">**送信 WCF メッセージ本文**セクションで、をクリックして、**テンプレート--テンプレートで指定されたコンテンツ**ラジオ ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e7d1-130">In the **Outbound WCF message body** section, click the **Template – Content specified by template** radio button.</span></span> <span data-ttu-id="4e7d1-131">**XML**テキスト ボックスで、BizTalk 本文の形式である必要があります</span><span class="sxs-lookup"><span data-stu-id="4e7d1-131">In the **XML** text box, the format of the BizTalk body should be</span></span>   
    <span data-ttu-id="4e7d1-132">\<**bts メッセージ本文の xmlns ="http://www.microsoft.com/schemas/bts2007"encoding =「[xml &#124; base64 &#124; 16 進数 &#124; 文字列]」/** \> (有効な値、xml &#124; base64 & # は、エンコード、大文字小文字が区別されます。#124; 16 進数 (&) #124 です。 文字列)</span><span class="sxs-lookup"><span data-stu-id="4e7d1-132">\<**bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="[xml&#124;base64&#124;hex&#124;string]"/**\>  (valid values, which are case-sensitive, for encoding are xml&#124;base64&#124;hex&#124;string)</span></span>