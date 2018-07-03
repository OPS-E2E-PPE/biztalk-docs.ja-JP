---
title: エラーのエラー処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 602be8a5-1f28-457d-8e12-ba06cff65491
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c494614465df4faeead9ec30d79dfdf47cc321c1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999083"
---
# <a name="error-handling-errors"></a><span data-ttu-id="da8b9-102">エラー処理エラー</span><span class="sxs-lookup"><span data-stu-id="da8b9-102">Error Handling Errors</span></span>
<span data-ttu-id="da8b9-103">診断および WCF エラー処理のエラーを解決するための情報です。</span><span class="sxs-lookup"><span data-stu-id="da8b9-103">Information for diagnosing and resolving WCF Error Handling errors.</span></span>  

## <a name="error-handling-options-disable-location-on-failure-and-suspend-request-message-on-failure-should-not-both-be-set-to-false"></a><span data-ttu-id="da8b9-104">エラー処理オプションの "エラー発生時に場所を無効にする" と "エラー発生時に要求メッセージを保留する" を両方とも false に設定しないでください</span><span class="sxs-lookup"><span data-stu-id="da8b9-104">Error handling options "Disable location on failure" and "Suspend request message on failure" should not both be set to false</span></span>    

|                 |                                                                                                <span data-ttu-id="da8b9-105">詳細</span><span class="sxs-lookup"><span data-stu-id="da8b9-105">Details</span></span>                                                                                                 |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="da8b9-106">製品名</span><span class="sxs-lookup"><span data-stu-id="da8b9-106">Product Name</span></span>   |                                                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                           |
| <span data-ttu-id="da8b9-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="da8b9-107">Product Version</span></span> |                                                                       [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                                       |
|    <span data-ttu-id="da8b9-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="da8b9-108">Event ID</span></span>     |                                                                                                   <span data-ttu-id="da8b9-109">0</span><span class="sxs-lookup"><span data-stu-id="da8b9-109">0</span></span>                                                                                                    |
|  <span data-ttu-id="da8b9-110">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="da8b9-110">Event Source</span></span>   |                                                                                                   <span data-ttu-id="da8b9-111">0</span><span class="sxs-lookup"><span data-stu-id="da8b9-111">0</span></span>                                                                                                    |
|    <span data-ttu-id="da8b9-112">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="da8b9-112">Component</span></span>    |                                                                                                   <span data-ttu-id="da8b9-113">0</span><span class="sxs-lookup"><span data-stu-id="da8b9-113">0</span></span>                                                                                                    |
|  <span data-ttu-id="da8b9-114">シンボル名</span><span class="sxs-lookup"><span data-stu-id="da8b9-114">Symbolic Name</span></span>  |                                                                                                   <span data-ttu-id="da8b9-115">0</span><span class="sxs-lookup"><span data-stu-id="da8b9-115">0</span></span>                                                                                                    |
|  <span data-ttu-id="da8b9-116">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="da8b9-116">Message Text</span></span>   | <span data-ttu-id="da8b9-117">エラーの処理オプション「エラー発生時の場所を無効にする」および「中断要求メッセージをエラー」が両方では false に設定するため、メッセージの損失が発生すます。</span><span class="sxs-lookup"><span data-stu-id="da8b9-117">The error handling options "Disable location on failure" and "Suspend request message on failure" should not both be set to false since message loss may occur.</span></span> <span data-ttu-id="da8b9-118">いずれか、または両方のオプションを true に設定してください。</span><span class="sxs-lookup"><span data-stu-id="da8b9-118">Please set one or both options to true</span></span> |

## <a name="explanation"></a><span data-ttu-id="da8b9-119">説明</span><span class="sxs-lookup"><span data-stu-id="da8b9-119">Explanation</span></span>  
 <span data-ttu-id="da8b9-120">Wcf-netmsmq アダプターは、オプションで**エラー上の場所を無効にする**と**エラー発生時に要求メッセージを保留**両方を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da8b9-120">In the WCF-NetMsmq adapter, the options **Disable location on failure** and **Suspend request message on failure** should not both be selected.</span></span> <span data-ttu-id="da8b9-121">受信場所に無効なメッセージが継続して送信され、メッセージ ボックスに保留および保存されると、メッセージが失われることがあります。</span><span class="sxs-lookup"><span data-stu-id="da8b9-121">Message loss may occur as the receive location continues to receive invalid messages, while these messages are not suspended and stored in the Message Box.</span></span>  

## <a name="user-action"></a><span data-ttu-id="da8b9-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="da8b9-122">User Action</span></span>  
 <span data-ttu-id="da8b9-123">アダプター設定を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="da8b9-123">Use the following procedure to configure adapter settings.</span></span>    

1. <span data-ttu-id="da8b9-124">開いている**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="da8b9-124">Open **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="da8b9-125">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="da8b9-125">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand **Applications**.</span></span>  

3. <span data-ttu-id="da8b9-126">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="da8b9-126">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="da8b9-127">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="da8b9-127">Right-click the transport name.</span></span>  

5. <span data-ttu-id="da8b9-128">選択**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="da8b9-128">Select **Properties**.</span></span>  

6. <span data-ttu-id="da8b9-129">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="da8b9-129">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="da8b9-130">**[構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="da8b9-130">Select **Configure**.</span></span>  

8. <span data-ttu-id="da8b9-131">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、**メッセージ**タブ。</span><span class="sxs-lookup"><span data-stu-id="da8b9-131">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, select the **Messages** tab.</span></span>  

9. <span data-ttu-id="da8b9-132">**エラー処理**セクションで、いずれかを確認します**エラー上の場所を無効にする**または**エラー発生時に要求メッセージを保留**がチェックされます。</span><span class="sxs-lookup"><span data-stu-id="da8b9-132">In the **Error Handling** section, ensure either **Disable location on failure** or **Suspend request message on failure** is checked.</span></span>
