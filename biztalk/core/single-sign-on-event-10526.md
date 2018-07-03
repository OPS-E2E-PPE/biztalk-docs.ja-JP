---
title: 'シングル サインオン: イベント 10526 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f72d466-8b63-453c-b608-f9d64f635f65
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 433190146391c494ff3b890c8332cc15fb947753
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024456"
---
# <a name="single-sign-on-event-10526"></a><span data-ttu-id="904b9-102">シングル サインオン: イベント 10526</span><span class="sxs-lookup"><span data-stu-id="904b9-102">Single Sign-On: Event 10526</span></span>
## <a name="details"></a><span data-ttu-id="904b9-103">詳細</span><span class="sxs-lookup"><span data-stu-id="904b9-103">Details</span></span>  

|                 |                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="904b9-104">製品名</span><span class="sxs-lookup"><span data-stu-id="904b9-104">Product Name</span></span>   |                                                                     <span data-ttu-id="904b9-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="904b9-105">Enterprise Single Sign-On</span></span>                                                                     |
| <span data-ttu-id="904b9-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="904b9-106">Product Version</span></span> |                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                     |
|    <span data-ttu-id="904b9-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="904b9-107">Event ID</span></span>     |                                                                               <span data-ttu-id="904b9-108">10526</span><span class="sxs-lookup"><span data-stu-id="904b9-108">10526</span></span>                                                                               |
|  <span data-ttu-id="904b9-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="904b9-109">Event Source</span></span>   |                                                                              <span data-ttu-id="904b9-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="904b9-110">ENTSSO</span></span>                                                                               |
|    <span data-ttu-id="904b9-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="904b9-111">Component</span></span>    |                                                                                <span data-ttu-id="904b9-112">N\A</span><span class="sxs-lookup"><span data-stu-id="904b9-112">N\A</span></span>                                                                                |
|  <span data-ttu-id="904b9-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="904b9-113">Symbolic Name</span></span>  |                                                                 <span data-ttu-id="904b9-114">SSO_ERROR_GENERATE_SECRET_FAILED</span><span class="sxs-lookup"><span data-stu-id="904b9-114">SSO_ERROR_GENERATE_SECRET_FAILED</span></span>                                                                  |
|  <span data-ttu-id="904b9-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="904b9-115">Message Text</span></span>   | <span data-ttu-id="904b9-116">新しいマスター シークレットを生成できませんでした。%r</span><span class="sxs-lookup"><span data-stu-id="904b9-116">Failed to generate a new master secret.%r</span></span><br /><br /> <span data-ttu-id="904b9-117">クライアント ユーザー: 1 %r</span><span class="sxs-lookup"><span data-stu-id="904b9-117">Client User: %1%r</span></span><br /><br /> <span data-ttu-id="904b9-118">クライアント コンピューター: %2%r</span><span class="sxs-lookup"><span data-stu-id="904b9-118">Client Computer:%2%r</span></span><br /><br /> <span data-ttu-id="904b9-119">追跡 ID: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="904b9-119">Tracking ID: %3%r</span></span><br /><br /> <span data-ttu-id="904b9-120">エラー コード: %4</span><span class="sxs-lookup"><span data-stu-id="904b9-120">Error Code: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="904b9-121">説明</span><span class="sxs-lookup"><span data-stu-id="904b9-121">Explanation</span></span>  
 <span data-ttu-id="904b9-122">このエラー イベントは、ユーザーが新しいマスター シークレットを生成しようとしたが、失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="904b9-122">This Error event indicates that a user attempt to generate a new master secret has failed.</span></span> <span data-ttu-id="904b9-123">原因としては、アクセス許可の問題 (マスター シークレットを生成するには SSO 管理者である必要がある) であるか、またはバックアップ ファイルへのマスター シークレットの書き込みに問題がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="904b9-123">This might be due to permissions issues (you must be an SSO Administrator to generate the master secret) or possibly there were problems writing the master secret to the backup file.</span></span> <span data-ttu-id="904b9-124">これらの場合、アプリケーション イベント ログに関連するメッセージがあります。</span><span class="sxs-lookup"><span data-stu-id="904b9-124">In these cases there should be related messages in the Application event log.</span></span>  

## <a name="user-action"></a><span data-ttu-id="904b9-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="904b9-125">User Action</span></span>  
 <span data-ttu-id="904b9-126">このエラーを解決するには、以下の 1 つ以上の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="904b9-126">To resolve this error, do one or more of the following:</span></span>  

- <span data-ttu-id="904b9-127">関連するイベントまたはエラーについては、アプリケーション イベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="904b9-127">Check the Application event log for associated events or errors.</span></span>  

- <span data-ttu-id="904b9-128">適切な SSO 管理者のアクセス許可があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="904b9-128">Check that you have the appropriate SSO Administrator permissions.</span></span>  

  <span data-ttu-id="904b9-129">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="904b9-129">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="904b9-130">マスター シークレットを生成する方法</span><span class="sxs-lookup"><span data-stu-id="904b9-130">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  

- [<span data-ttu-id="904b9-131">マスター シークレットの管理</span><span class="sxs-lookup"><span data-stu-id="904b9-131">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)
