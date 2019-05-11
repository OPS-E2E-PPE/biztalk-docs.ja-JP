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
ms.openlocfilehash: 02203fcdde41ff078e3fcd9a5e71516f11599732
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388834"
---
# <a name="error-handling-errors"></a><span data-ttu-id="cdff7-102">エラー処理エラー</span><span class="sxs-lookup"><span data-stu-id="cdff7-102">Error Handling Errors</span></span>
<span data-ttu-id="cdff7-103">診断および WCF エラー処理のエラーを解決するための情報です。</span><span class="sxs-lookup"><span data-stu-id="cdff7-103">Information for diagnosing and resolving WCF Error Handling errors.</span></span>  

## <a name="error-handling-options-disable-location-on-failure-and-suspend-request-message-on-failure-should-not-both-be-set-to-false"></a><span data-ttu-id="cdff7-104">エラー処理オプションの "エラー発生時に場所を無効にする" と "エラー発生時に要求メッセージを保留する" を両方とも false に設定しないでください</span><span class="sxs-lookup"><span data-stu-id="cdff7-104">Error handling options "Disable location on failure" and "Suspend request message on failure" should not both be set to false</span></span>    

|                 |                                                                                                <span data-ttu-id="cdff7-105">詳細</span><span class="sxs-lookup"><span data-stu-id="cdff7-105">Details</span></span>                                                                                                 |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="cdff7-106">製品名</span><span class="sxs-lookup"><span data-stu-id="cdff7-106">Product Name</span></span>   |                                                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                           |
| <span data-ttu-id="cdff7-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="cdff7-107">Product Version</span></span> |                                                                       [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                                       |
|    <span data-ttu-id="cdff7-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="cdff7-108">Event ID</span></span>     |                                                                                                   <span data-ttu-id="cdff7-109">0</span><span class="sxs-lookup"><span data-stu-id="cdff7-109">0</span></span>                                                                                                    |
|  <span data-ttu-id="cdff7-110">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="cdff7-110">Event Source</span></span>   |                                                                                                   <span data-ttu-id="cdff7-111">0</span><span class="sxs-lookup"><span data-stu-id="cdff7-111">0</span></span>                                                                                                    |
|    <span data-ttu-id="cdff7-112">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="cdff7-112">Component</span></span>    |                                                                                                   <span data-ttu-id="cdff7-113">0</span><span class="sxs-lookup"><span data-stu-id="cdff7-113">0</span></span>                                                                                                    |
|  <span data-ttu-id="cdff7-114">シンボル名</span><span class="sxs-lookup"><span data-stu-id="cdff7-114">Symbolic Name</span></span>  |                                                                                                   <span data-ttu-id="cdff7-115">0</span><span class="sxs-lookup"><span data-stu-id="cdff7-115">0</span></span>                                                                                                    |
|  <span data-ttu-id="cdff7-116">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="cdff7-116">Message Text</span></span>   | <span data-ttu-id="cdff7-117">エラーの処理オプション「エラー発生時の場所を無効にする」および「中断要求メッセージをエラー」が両方では false に設定するため、メッセージの損失が発生すます。</span><span class="sxs-lookup"><span data-stu-id="cdff7-117">The error handling options "Disable location on failure" and "Suspend request message on failure" should not both be set to false since message loss may occur.</span></span> <span data-ttu-id="cdff7-118">1 つまたは両方のオプションを true に設定してください。</span><span class="sxs-lookup"><span data-stu-id="cdff7-118">Please set one or both options to true</span></span> |

## <a name="explanation"></a><span data-ttu-id="cdff7-119">説明</span><span class="sxs-lookup"><span data-stu-id="cdff7-119">Explanation</span></span>  
 <span data-ttu-id="cdff7-120">Wcf-netmsmq アダプターは、オプションで**エラー上の場所を無効にする**と**エラー発生時に要求メッセージを保留**両方を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdff7-120">In the WCF-NetMsmq adapter, the options **Disable location on failure** and **Suspend request message on failure** should not both be selected.</span></span> <span data-ttu-id="cdff7-121">これらのメッセージが中断され、メッセージ ボックスに格納されているないときに、無効なメッセージを受信する受信場所では、メッセージの損失が発生します。</span><span class="sxs-lookup"><span data-stu-id="cdff7-121">Message loss may occur as the receive location continues to receive invalid messages, while these messages are not suspended and stored in the Message Box.</span></span>  

## <a name="user-action"></a><span data-ttu-id="cdff7-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="cdff7-122">User Action</span></span>  
 <span data-ttu-id="cdff7-123">アダプター設定を構成するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="cdff7-123">Use the following procedure to configure adapter settings.</span></span>    

1. <span data-ttu-id="cdff7-124">開いている**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="cdff7-124">Open **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="cdff7-125">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="cdff7-125">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand **Applications**.</span></span>  

3. <span data-ttu-id="cdff7-126">アプリケーションを見つけて、トランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="cdff7-126">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="cdff7-127">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="cdff7-127">Right-click the transport name.</span></span>  

5. <span data-ttu-id="cdff7-128">選択**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="cdff7-128">Select **Properties**.</span></span>  

6. <span data-ttu-id="cdff7-129">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="cdff7-129">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="cdff7-130">**[構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdff7-130">Select **Configure**.</span></span>  

8. <span data-ttu-id="cdff7-131">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、**メッセージ**タブ。</span><span class="sxs-lookup"><span data-stu-id="cdff7-131">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, select the **Messages** tab.</span></span>  

9. <span data-ttu-id="cdff7-132">**エラー処理**セクションで、いずれかを確認します**エラー上の場所を無効にする**または**エラー発生時に要求メッセージを保留**がチェックされます。</span><span class="sxs-lookup"><span data-stu-id="cdff7-132">In the **Error Handling** section, ensure either **Disable location on failure** or **Suspend request message on failure** is checked.</span></span>
