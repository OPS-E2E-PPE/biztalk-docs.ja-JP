---
title: エラーの処理エラー |Microsoft ドキュメント
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
ms.openlocfilehash: dafc64afb24ce8bb7995e7852a778b17a556f018
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240826"
---
# <a name="error-handling-errors"></a><span data-ttu-id="28d16-102">エラー処理エラー</span><span class="sxs-lookup"><span data-stu-id="28d16-102">Error Handling Errors</span></span>
<span data-ttu-id="28d16-103">診断および WCF エラー処理のエラーを解決するための情報です。</span><span class="sxs-lookup"><span data-stu-id="28d16-103">Information for diagnosing and resolving WCF Error Handling errors.</span></span>  

## <a name="error-handling-options-disable-location-on-failure-and-suspend-request-message-on-failure-should-not-both-be-set-to-false"></a><span data-ttu-id="28d16-104">エラー処理オプションの "エラー発生時に場所を無効にする" と "エラー発生時に要求メッセージを保留する" を両方とも false に設定しないでください</span><span class="sxs-lookup"><span data-stu-id="28d16-104">Error handling options "Disable location on failure" and "Suspend request message on failure" should not both be set to false</span></span>    
||<span data-ttu-id="28d16-105">詳細</span><span class="sxs-lookup"><span data-stu-id="28d16-105">Details</span></span>|  
|-|-|  
|<span data-ttu-id="28d16-106">製品名</span><span class="sxs-lookup"><span data-stu-id="28d16-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="28d16-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="28d16-107">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="28d16-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="28d16-108">Event ID</span></span>|<span data-ttu-id="28d16-109">0</span><span class="sxs-lookup"><span data-stu-id="28d16-109">0</span></span>|  
|<span data-ttu-id="28d16-110">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="28d16-110">Event Source</span></span>|<span data-ttu-id="28d16-111">0</span><span class="sxs-lookup"><span data-stu-id="28d16-111">0</span></span>|  
|<span data-ttu-id="28d16-112">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="28d16-112">Component</span></span>|<span data-ttu-id="28d16-113">0</span><span class="sxs-lookup"><span data-stu-id="28d16-113">0</span></span>|  
|<span data-ttu-id="28d16-114">シンボル名</span><span class="sxs-lookup"><span data-stu-id="28d16-114">Symbolic Name</span></span>|<span data-ttu-id="28d16-115">0</span><span class="sxs-lookup"><span data-stu-id="28d16-115">0</span></span>|  
|<span data-ttu-id="28d16-116">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="28d16-116">Message Text</span></span>|<span data-ttu-id="28d16-117">エラー処理オプション「エラー発生時に場所を無効にする」および「中断エラー発生時に要求メッセージ」する必要があります両方 false に設定するため、メッセージの損失が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="28d16-117">The error handling options "Disable location on failure" and "Suspend request message on failure" should not both be set to false since message loss may occur.</span></span> <span data-ttu-id="28d16-118">いずれか、または両方のオプションを true に設定してください。</span><span class="sxs-lookup"><span data-stu-id="28d16-118">Please set one or both options to true</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="28d16-119">説明</span><span class="sxs-lookup"><span data-stu-id="28d16-119">Explanation</span></span>  
 <span data-ttu-id="28d16-120">Wcf-netmsmq アダプターで、オプション**エラー発生時に場所を無効にする**と**エラー発生時に要求メッセージを保留**両方を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28d16-120">In the WCF-NetMsmq adapter, the options **Disable location on failure** and **Suspend request message on failure** should not both be selected.</span></span> <span data-ttu-id="28d16-121">受信場所に無効なメッセージが継続して送信され、メッセージ ボックスに保留および保存されると、メッセージが失われることがあります。</span><span class="sxs-lookup"><span data-stu-id="28d16-121">Message loss may occur as the receive location continues to receive invalid messages, while these messages are not suspended and stored in the Message Box.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="28d16-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="28d16-122">User Action</span></span>  
 <span data-ttu-id="28d16-123">アダプター設定を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="28d16-123">Use the following procedure to configure adapter settings.</span></span>    

1. <span data-ttu-id="28d16-124">開いている**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="28d16-124">Open **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="28d16-125">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="28d16-125">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="28d16-126">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="28d16-126">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="28d16-127">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="28d16-127">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="28d16-128">選択**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="28d16-128">Select **Properties**.</span></span>  
  
6.  <span data-ttu-id="28d16-129">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="28d16-129">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="28d16-130">**[構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="28d16-130">Select **Configure**.</span></span>  
  
8.  <span data-ttu-id="28d16-131">**WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、**メッセージ**タブです。</span><span class="sxs-lookup"><span data-stu-id="28d16-131">In the **WCF [***transport type***] Transport Properties** dialog box, select the **Messages** tab.</span></span>  
  
9. <span data-ttu-id="28d16-132">**Error Handling**セクションで、いずれかを確認してください**エラー発生時に場所を無効にする**または**エラー発生時に要求メッセージを保留**がチェックします。</span><span class="sxs-lookup"><span data-stu-id="28d16-132">In the **Error Handling** section, ensure either **Disable location on failure** or **Suspend request message on failure** is checked.</span></span>