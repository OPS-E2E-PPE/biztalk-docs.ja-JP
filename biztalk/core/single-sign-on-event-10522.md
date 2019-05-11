---
title: シングル サインオン:イベント 10522 |Microsoft Docs
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
ms.openlocfilehash: ac9347492793170faed39be91f2925e0ffdc1cdc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393019"
---
# <a name="single-sign-on-event-10522"></a><span data-ttu-id="1b971-102">シングル サインオン:イベント 10522</span><span class="sxs-lookup"><span data-stu-id="1b971-102">Single Sign-On: Event 10522</span></span>
## <a name="details"></a><span data-ttu-id="1b971-103">詳細</span><span class="sxs-lookup"><span data-stu-id="1b971-103">Details</span></span>  

|                 |                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------|
|  <span data-ttu-id="1b971-104">製品名</span><span class="sxs-lookup"><span data-stu-id="1b971-104">Product Name</span></span>   |                                   <span data-ttu-id="1b971-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="1b971-105">Enterprise Single Sign-On</span></span>                                   |
| <span data-ttu-id="1b971-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="1b971-106">Product Version</span></span> |                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                   |
|    <span data-ttu-id="1b971-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="1b971-107">Event ID</span></span>     |                                             <span data-ttu-id="1b971-108">10522</span><span class="sxs-lookup"><span data-stu-id="1b971-108">10522</span></span>                                             |
|  <span data-ttu-id="1b971-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="1b971-109">Event Source</span></span>   |                                            <span data-ttu-id="1b971-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="1b971-110">ENTSSO</span></span>                                             |
|    <span data-ttu-id="1b971-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1b971-111">Component</span></span>    |                                              <span data-ttu-id="1b971-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="1b971-112">N\A</span></span>                                              |
|  <span data-ttu-id="1b971-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="1b971-113">Symbolic Name</span></span>  |                                      <span data-ttu-id="1b971-114">SSO_ERROR_REENCRYPT</span><span class="sxs-lookup"><span data-stu-id="1b971-114">SSO_ERROR_REENCRYPT</span></span>                                      |
|  <span data-ttu-id="1b971-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="1b971-115">Message Text</span></span>   | <span data-ttu-id="1b971-116">SSO データベースを再暗号化に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="1b971-116">SSO database re-encryption failed.</span></span> <span data-ttu-id="1b971-117">%1 minutes.%r にもう一度します。</span><span class="sxs-lookup"><span data-stu-id="1b971-117">Will try again in %1 minutes.%r</span></span><br /><br /> <span data-ttu-id="1b971-118">エラー コード: %2</span><span class="sxs-lookup"><span data-stu-id="1b971-118">Error Code: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="1b971-119">説明</span><span class="sxs-lookup"><span data-stu-id="1b971-119">Explanation</span></span>  
 <span data-ttu-id="1b971-120">このエラー イベントは、SSO データベースの再暗号化が失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="1b971-120">This Error event indicates that the SSO database re-encryption failed.</span></span> <span data-ttu-id="1b971-121">マスタ シークレット サーバーで SSO サービスの起動時かどうかがありますが、SSO データベースを以前のマスター シークレットで暗号化されたままでを確認するは、まずことです。</span><span class="sxs-lookup"><span data-stu-id="1b971-121">When the SSO service starts on the master secret server, the first thing it does is to check if there is anything in the SSO database still encrypted with the previous master secret.</span></span> <span data-ttu-id="1b971-122">ものが見つかると、(以前のシークレットを使用して) その情報を復号化し、現在のマスター シークレットを使用して再暗号化します。</span><span class="sxs-lookup"><span data-stu-id="1b971-122">If it finds anything, it decrypts that information (using the previous secret) and re-encrypts it using the current master secret.</span></span> <span data-ttu-id="1b971-123">何らかの理由でこの処理に失敗した場合は、このイベント メッセージが発行されます。</span><span class="sxs-lookup"><span data-stu-id="1b971-123">If for any reason this process fails, then this event message is issued.</span></span>  

## <a name="user-action"></a><span data-ttu-id="1b971-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="1b971-124">User Action</span></span>  
 <span data-ttu-id="1b971-125">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1b971-125">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="1b971-126">エラーの根本原因の特定にエラー コードを確認します。</span><span class="sxs-lookup"><span data-stu-id="1b971-126">Check the error code to determine what the underlying cause of the error might be.</span></span> <span data-ttu-id="1b971-127">これは、ネットワークまたはデータベースの問題となる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1b971-127">This could be a network or database issue.</span></span> <span data-ttu-id="1b971-128">断続的な場合は、し、アクションは必要ありませんので、短い遅延の後にもう一度再暗号化が試行されます。</span><span class="sxs-lookup"><span data-stu-id="1b971-128">If it is intermittent, then no action is required because re-encryption will be attempted again after a short delay.</span></span> <span data-ttu-id="1b971-129">問題が断続的でない場合は、SSO サービスを停止し、問題を解決しようとしてください。</span><span class="sxs-lookup"><span data-stu-id="1b971-129">If the issue is not intermittent, stop the SSO service and attempt to resolve the issue.</span></span> <span data-ttu-id="1b971-130">問題が解決し、SSO サービスを再起動して、SSO サービスを再起動すると、再暗号化が実行自動的にします。</span><span class="sxs-lookup"><span data-stu-id="1b971-130">Once the issue is resolved then restart the SSO service, Restarting the SSO service will automatically perform the re-encryption.</span></span>  

  <span data-ttu-id="1b971-131">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="1b971-131">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="1b971-132">SSO データベース情報を表示する方法</span><span class="sxs-lookup"><span data-stu-id="1b971-132">How to Display the SSO Database Information</span></span>](../core/how-to-display-the-sso-database-information.md)  

- [<span data-ttu-id="1b971-133">マスター シークレット サーバー</span><span class="sxs-lookup"><span data-stu-id="1b971-133">Master Secret Server</span></span>](../core/master-secret-server.md)
