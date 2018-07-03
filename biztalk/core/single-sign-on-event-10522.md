---
title: 'シングル サインオン: イベント 10522 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd634a57-01dc-44bd-bcf9-668689db7b77
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f8bb97c8c537cca8b2f9c6e9176409d7da4dd3e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972131"
---
# <a name="single-sign-on-event-10522"></a><span data-ttu-id="76ad2-102">シングル サインオン: イベント 10522</span><span class="sxs-lookup"><span data-stu-id="76ad2-102">Single Sign-On: Event 10522</span></span>
## <a name="details"></a><span data-ttu-id="76ad2-103">詳細</span><span class="sxs-lookup"><span data-stu-id="76ad2-103">Details</span></span>  

|                 |                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------|
|  <span data-ttu-id="76ad2-104">製品名</span><span class="sxs-lookup"><span data-stu-id="76ad2-104">Product Name</span></span>   |                                   <span data-ttu-id="76ad2-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="76ad2-105">Enterprise Single Sign-On</span></span>                                   |
| <span data-ttu-id="76ad2-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="76ad2-106">Product Version</span></span> |                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                   |
|    <span data-ttu-id="76ad2-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="76ad2-107">Event ID</span></span>     |                                             <span data-ttu-id="76ad2-108">10522</span><span class="sxs-lookup"><span data-stu-id="76ad2-108">10522</span></span>                                             |
|  <span data-ttu-id="76ad2-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="76ad2-109">Event Source</span></span>   |                                            <span data-ttu-id="76ad2-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="76ad2-110">ENTSSO</span></span>                                             |
|    <span data-ttu-id="76ad2-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="76ad2-111">Component</span></span>    |                                              <span data-ttu-id="76ad2-112">N\A</span><span class="sxs-lookup"><span data-stu-id="76ad2-112">N\A</span></span>                                              |
|  <span data-ttu-id="76ad2-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="76ad2-113">Symbolic Name</span></span>  |                                      <span data-ttu-id="76ad2-114">SSO_ERROR_REENCRYPT</span><span class="sxs-lookup"><span data-stu-id="76ad2-114">SSO_ERROR_REENCRYPT</span></span>                                      |
|  <span data-ttu-id="76ad2-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="76ad2-115">Message Text</span></span>   | <span data-ttu-id="76ad2-116">SSO データベースの再暗号化が失敗しました。</span><span class="sxs-lookup"><span data-stu-id="76ad2-116">SSO database re-encryption failed.</span></span> <span data-ttu-id="76ad2-117">%1 分後に再試行されます。%r</span><span class="sxs-lookup"><span data-stu-id="76ad2-117">Will try again in %1 minutes.%r</span></span><br /><br /> <span data-ttu-id="76ad2-118">エラー コード: %2</span><span class="sxs-lookup"><span data-stu-id="76ad2-118">Error Code: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="76ad2-119">説明</span><span class="sxs-lookup"><span data-stu-id="76ad2-119">Explanation</span></span>  
 <span data-ttu-id="76ad2-120">このエラー イベントは、SSO データベースの再暗号化が失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="76ad2-120">This Error event indicates that the SSO database re-encryption failed.</span></span> <span data-ttu-id="76ad2-121">SSO サービスは、マスター シークレット サーバーで開始すると、最初に、以前のマスター シークレットで暗号化されているものがまだ SSO データベースに存在するかどうかを調べます。</span><span class="sxs-lookup"><span data-stu-id="76ad2-121">When the SSO service starts on the master secret server, the first thing it does is to check if there is anything in the SSO database still encrypted with the previous master secret.</span></span> <span data-ttu-id="76ad2-122">該当するものが見つかると、(以前のシークレットを使用して) その情報を暗号化解除し、現在のマスター シークレットを使用して再暗号化します。</span><span class="sxs-lookup"><span data-stu-id="76ad2-122">If it finds anything, it decrypts that information (using the previous secret) and re-encrypts it using the current master secret.</span></span> <span data-ttu-id="76ad2-123">何らかの理由でこの処理が失敗すると、このイベント メッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="76ad2-123">If for any reason this process fails, then this event message is issued.</span></span>  

## <a name="user-action"></a><span data-ttu-id="76ad2-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="76ad2-124">User Action</span></span>  
 <span data-ttu-id="76ad2-125">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="76ad2-125">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="76ad2-126">エラー コードを調べて、エラーの根本原因を特定します。</span><span class="sxs-lookup"><span data-stu-id="76ad2-126">Check the error code to determine what the underlying cause of the error might be.</span></span> <span data-ttu-id="76ad2-127">ネットワークまたはデータベースの問題である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="76ad2-127">This could be a network or database issue.</span></span> <span data-ttu-id="76ad2-128">断続的なものである場合は、すぐに再暗号化が再び試みられるので、操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="76ad2-128">If it is intermittent, then no action is required because re-encryption will be attempted again after a short delay.</span></span> <span data-ttu-id="76ad2-129">問題が断続的でない場合は、SSO サービスを停止し、問題の解決を試みます。</span><span class="sxs-lookup"><span data-stu-id="76ad2-129">If the issue is not intermittent, stop the SSO service and attempt to resolve the issue.</span></span> <span data-ttu-id="76ad2-130">問題を解決したら SSO サービスを再起動します。SSO サービスを再起動すると、再暗号化が自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="76ad2-130">Once the issue is resolved then restart the SSO service, Restarting the SSO service will automatically perform the re-encryption.</span></span>  

  <span data-ttu-id="76ad2-131">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="76ad2-131">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="76ad2-132">SSO データベース情報を表示する方法</span><span class="sxs-lookup"><span data-stu-id="76ad2-132">How to Display the SSO Database Information</span></span>](../core/how-to-display-the-sso-database-information.md)  

- [<span data-ttu-id="76ad2-133">マスター シークレット サーバー</span><span class="sxs-lookup"><span data-stu-id="76ad2-133">Master Secret Server</span></span>](../core/master-secret-server.md)
