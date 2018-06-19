---
title: BizTalk メッセージ本文要素のエンコードが正しくありません |Microsoft ドキュメント
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
ms.openlocfilehash: 1b1835371e5c042d3ddc46558cbf97970f6bfc6c
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
ms.locfileid: "25964816"
---
# <a name="biztalk-message-body-element-encoding-is-invalid"></a><span data-ttu-id="9a9e2-102">BizTalk メッセージ本文要素のエンコードは無効です</span><span class="sxs-lookup"><span data-stu-id="9a9e2-102">BizTalk message body element encoding is invalid</span></span>
## <a name="details"></a><span data-ttu-id="9a9e2-103">詳細</span><span class="sxs-lookup"><span data-stu-id="9a9e2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9a9e2-104">製品名</span><span class="sxs-lookup"><span data-stu-id="9a9e2-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="9a9e2-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="9a9e2-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="9a9e2-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="9a9e2-106">Event ID</span></span>|<span data-ttu-id="9a9e2-107">0</span><span class="sxs-lookup"><span data-stu-id="9a9e2-107">0</span></span>|  
|<span data-ttu-id="9a9e2-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="9a9e2-108">Event Source</span></span>|<span data-ttu-id="9a9e2-109">0</span><span class="sxs-lookup"><span data-stu-id="9a9e2-109">0</span></span>|  
|<span data-ttu-id="9a9e2-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9a9e2-110">Component</span></span>|<span data-ttu-id="9a9e2-111">0</span><span class="sxs-lookup"><span data-stu-id="9a9e2-111">0</span></span>|  
|<span data-ttu-id="9a9e2-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="9a9e2-112">Symbolic Name</span></span>|<span data-ttu-id="9a9e2-113">0</span><span class="sxs-lookup"><span data-stu-id="9a9e2-113">0</span></span>|  
|<span data-ttu-id="9a9e2-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="9a9e2-114">Message Text</span></span>|<span data-ttu-id="9a9e2-115">BizTalk メッセージ本文要素のエンコード "{0}" は無効です。</span><span class="sxs-lookup"><span data-stu-id="9a9e2-115">BizTalk message body element encoding "{0}" is invalid.</span></span> <span data-ttu-id="9a9e2-116">エンコード:"xml"、"base64"、"hex"、または"文字列 string"</span><span class="sxs-lookup"><span data-stu-id="9a9e2-116">Expected encoding: "xml", "base64", "hex", or "string"</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9a9e2-117">説明</span><span class="sxs-lookup"><span data-stu-id="9a9e2-117">Explanation</span></span>  
 <span data-ttu-id="9a9e2-118">このエラーは、送信メッセージには BizTalk 本文テンプレート オプションが使用されていますが、BizTalk 本文に指定されたエンコーディングの種類は無効であることを示します。</span><span class="sxs-lookup"><span data-stu-id="9a9e2-118">This error indicates the use of the BizTalk body template option for the outgoing messages; however, the encoding type specified for the BizTalk body is invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9a9e2-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="9a9e2-119">User Action</span></span>  
 <span data-ttu-id="9a9e2-120">エンコーディングの種類を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9a9e2-120">Use the following procedure to configure the encoding type.</span></span>  
  
#### <a name="to-configure-the-encoding-type"></a><span data-ttu-id="9a9e2-121">エンコーディングの種類を構成するには</span><span class="sxs-lookup"><span data-stu-id="9a9e2-121">To configure the encoding type</span></span>  
  
1.  <span data-ttu-id="9a9e2-122">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="9a9e2-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="9a9e2-123">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="9a9e2-123">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="9a9e2-124">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="9a9e2-124">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="9a9e2-125">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="9a9e2-125">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="9a9e2-126">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a9e2-126">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="9a9e2-127">ポートに **型** 一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="9a9e2-127">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="9a9e2-128">クリックして **構成**します。</span><span class="sxs-lookup"><span data-stu-id="9a9e2-128">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="9a9e2-129">**WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**メッセージ**タブです。</span><span class="sxs-lookup"><span data-stu-id="9a9e2-129">In the **WCF [***transport type***] Transport Properties** dialog box, click the **Messages** tab.</span></span>  
  
9. <span data-ttu-id="9a9e2-130">**送信 WCF メッセージ本文**  をクリックして、 **テンプレート-テンプレートで指定されたコンテンツ** オプション ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a9e2-130">In the **Outbound WCF message body** section, click the **Template – Content specified by template** radio button.</span></span> <span data-ttu-id="9a9e2-131">**XML** テキスト ボックスで、BizTalk 本文の形式である必要があります</span><span class="sxs-lookup"><span data-stu-id="9a9e2-131">In the **XML** text box, the format of the BizTalk body should be</span></span>   
    <span data-ttu-id="9a9e2-132">\<**bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="[xml&#124;base64&#124;hex&#124;string]"/**\>  (valid values, which are case-sensitive, for encoding are xml&#124;base64&#124;hex&#124;string)</span><span class="sxs-lookup"><span data-stu-id="9a9e2-132">\<**bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="[xml&#124;base64&#124;hex&#124;string]"/**\>  (valid values, which are case-sensitive, for encoding are xml&#124;base64&#124;hex&#124;string)</span></span>