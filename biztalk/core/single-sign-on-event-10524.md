---
title: シングル サインオン:イベント 10524 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55e26da3-f67f-4f87-92e5-2f8765b19989
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d135f8856707527eb3368b579b6f77d541cbb84b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262551"
---
# <a name="single-sign-on-event-10524"></a><span data-ttu-id="5c0c5-102">シングル サインオン:イベント 10524</span><span class="sxs-lookup"><span data-stu-id="5c0c5-102">Single Sign-On: Event 10524</span></span>
## <a name="details"></a><span data-ttu-id="5c0c5-103">詳細</span><span class="sxs-lookup"><span data-stu-id="5c0c5-103">Details</span></span>  

|                 |                                                                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="5c0c5-104">製品名</span><span class="sxs-lookup"><span data-stu-id="5c0c5-104">Product Name</span></span>   |                                                                                  <span data-ttu-id="5c0c5-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="5c0c5-105">Enterprise Single Sign-On</span></span>                                                                                  |
| <span data-ttu-id="5c0c5-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="5c0c5-106">Product Version</span></span> |                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                  |
|    <span data-ttu-id="5c0c5-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="5c0c5-107">Event ID</span></span>     |                                                                                            <span data-ttu-id="5c0c5-108">10524</span><span class="sxs-lookup"><span data-stu-id="5c0c5-108">10524</span></span>                                                                                            |
|  <span data-ttu-id="5c0c5-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="5c0c5-109">Event Source</span></span>   |                                                                                           <span data-ttu-id="5c0c5-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="5c0c5-110">ENTSSO</span></span>                                                                                            |
|    <span data-ttu-id="5c0c5-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5c0c5-111">Component</span></span>    |                                                                                             <span data-ttu-id="5c0c5-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="5c0c5-112">N\A</span></span>                                                                                             |
|  <span data-ttu-id="5c0c5-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="5c0c5-113">Symbolic Name</span></span>  |                                                                               <span data-ttu-id="5c0c5-114">SSO_ERROR_RESTORE_SECRET_FAILED</span><span class="sxs-lookup"><span data-stu-id="5c0c5-114">SSO_ERROR_RESTORE_SECRET_FAILED</span></span>                                                                               |
|  <span data-ttu-id="5c0c5-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="5c0c5-115">Message Text</span></span>   | <span data-ttu-id="5c0c5-116">マスター secrets.%r の復元に失敗しました</span><span class="sxs-lookup"><span data-stu-id="5c0c5-116">Failed to restore the master secrets.%r</span></span><br /><br /> <span data-ttu-id="5c0c5-117">ファイル名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="5c0c5-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="5c0c5-118">現在の MSID: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="5c0c5-118">Current MSID: %2%r</span></span><br /><br /> <span data-ttu-id="5c0c5-119">以前の MSID: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="5c0c5-119">Previous MSID: %3%r</span></span><br /><br /> <span data-ttu-id="5c0c5-120">クライアント ユーザー: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="5c0c5-120">Client User: %4%r</span></span><br /><br /> <span data-ttu-id="5c0c5-121">エラー コード: %5</span><span class="sxs-lookup"><span data-stu-id="5c0c5-121">Error Code: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="5c0c5-122">説明</span><span class="sxs-lookup"><span data-stu-id="5c0c5-122">Explanation</span></span>  
 <span data-ttu-id="5c0c5-123">このエラー イベントは、バックアップ ファイルからマスター シークレットを復元するユーザーの試行が失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="5c0c5-123">This Error event indicates that a user attempt to restore the master secrets from a backup file failed.</span></span> <span data-ttu-id="5c0c5-124">原因としては、アクセス許可 (マスター シークレットを復元するのには、SSO 管理者である必要があります) の問題またはバックアップ ファイルのファイルの破損原因として考えられます。</span><span class="sxs-lookup"><span data-stu-id="5c0c5-124">This might be due to permissions issues (you must be an SSO Administrator to restore the master secret) or possibly due to file corruption of the backup file.</span></span> <span data-ttu-id="5c0c5-125">このような場合があります関連するメッセージ、アプリケーション イベント ログ。</span><span class="sxs-lookup"><span data-stu-id="5c0c5-125">In these cases there should be related messages in the Application event log.</span></span>  

## <a name="user-action"></a><span data-ttu-id="5c0c5-126">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="5c0c5-126">User Action</span></span>  
 <span data-ttu-id="5c0c5-127">このエラーを解決するには、以下の 1 つ以上の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="5c0c5-127">To resolve this error, do one or more of the following:</span></span>  

- <span data-ttu-id="5c0c5-128">アプリケーション イベント ログの関連するイベントまたはエラーを確認します。</span><span class="sxs-lookup"><span data-stu-id="5c0c5-128">Check the Application event log for associated events or errors.</span></span>  

- <span data-ttu-id="5c0c5-129">適切な SSO 管理者のアクセス許可があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5c0c5-129">Check that you have the appropriate SSO Administrator permissions.</span></span>  

  <span data-ttu-id="5c0c5-130">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="5c0c5-130">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="5c0c5-131">マスター シークレットを復元する方法</span><span class="sxs-lookup"><span data-stu-id="5c0c5-131">How to Restore the Master Secret</span></span>](../core/how-to-restore-the-master-secret.md)  

- [<span data-ttu-id="5c0c5-132">マスター シークレットをバックアップする方法</span><span class="sxs-lookup"><span data-stu-id="5c0c5-132">How to Back Up the Master Secret</span></span>](../core/how-to-back-up-the-master-secret.md)  

- [<span data-ttu-id="5c0c5-133">マスター シークレットを生成する方法</span><span class="sxs-lookup"><span data-stu-id="5c0c5-133">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)
