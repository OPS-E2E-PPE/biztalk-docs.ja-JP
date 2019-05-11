---
title: シングル サインオン:イベント 10527 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 40995ad8-9f74-4e96-863d-427e23025ba1
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57f5ac8452d96e3af54ff4d5cfc21f6664435bc6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262508"
---
# <a name="single-sign-on-event-10527"></a><span data-ttu-id="f0752-102">シングル サインオン:イベント 10527</span><span class="sxs-lookup"><span data-stu-id="f0752-102">Single Sign-On: Event 10527</span></span>
## <a name="details"></a><span data-ttu-id="f0752-103">詳細</span><span class="sxs-lookup"><span data-stu-id="f0752-103">Details</span></span>  

|                 |                                                                                                                                                                                                     |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="f0752-104">製品名</span><span class="sxs-lookup"><span data-stu-id="f0752-104">Product Name</span></span>   |                                                                                      <span data-ttu-id="f0752-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="f0752-105">Enterprise Single Sign-On</span></span>                                                                                      |
| <span data-ttu-id="f0752-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f0752-106">Product Version</span></span> |                                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                      |
|    <span data-ttu-id="f0752-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f0752-107">Event ID</span></span>     |                                                                                                <span data-ttu-id="f0752-108">10527</span><span class="sxs-lookup"><span data-stu-id="f0752-108">10527</span></span>                                                                                                |
|  <span data-ttu-id="f0752-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f0752-109">Event Source</span></span>   |                                                                                               <span data-ttu-id="f0752-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f0752-110">ENTSSO</span></span>                                                                                                |
|    <span data-ttu-id="f0752-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f0752-111">Component</span></span>    |                                                                                                  <span data-ttu-id="f0752-112">0</span><span class="sxs-lookup"><span data-stu-id="f0752-112">0</span></span>                                                                                                  |
|  <span data-ttu-id="f0752-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f0752-113">Symbolic Name</span></span>  |                                                                                     <span data-ttu-id="f0752-114">SSO_ERROR_GET_SECRET_FAILED</span><span class="sxs-lookup"><span data-stu-id="f0752-114">SSO_ERROR_GET_SECRET_FAILED</span></span>                                                                                     |
|  <span data-ttu-id="f0752-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f0752-115">Message Text</span></span>   | <span data-ttu-id="f0752-116">マスター シークレット failed.%r を取得する要求</span><span class="sxs-lookup"><span data-stu-id="f0752-116">A request to get a master secret failed.%r</span></span><br /><br /> <span data-ttu-id="f0752-117">シークレット番号: % 1 %r</span><span class="sxs-lookup"><span data-stu-id="f0752-117">Secret Number: %1%r</span></span><br /><br /> <span data-ttu-id="f0752-118">クライアント ユーザー: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="f0752-118">Client User: %2%r</span></span><br /><br /> <span data-ttu-id="f0752-119">クライアント コンピューターの場合: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="f0752-119">Client Computer: %3%r</span></span><br /><br /> <span data-ttu-id="f0752-120">追跡 ID: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="f0752-120">Tracking ID: %4%r</span></span><br /><br /> <span data-ttu-id="f0752-121">エラー コード: %5</span><span class="sxs-lookup"><span data-stu-id="f0752-121">Error Code: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="f0752-122">説明</span><span class="sxs-lookup"><span data-stu-id="f0752-122">Explanation</span></span>  
 <span data-ttu-id="f0752-123">このエラー イベントは、マスター シークレットを取得する要求が失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="f0752-123">This Error event indicates that a request to get the master secret has failed.</span></span> <span data-ttu-id="f0752-124">このような場合があります関連するメッセージ、アプリケーション イベント ログ。</span><span class="sxs-lookup"><span data-stu-id="f0752-124">In these cases there should be related messages in the Application event log.</span></span>  

## <a name="user-action"></a><span data-ttu-id="f0752-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f0752-125">User Action</span></span>  
 <span data-ttu-id="f0752-126">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f0752-126">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="f0752-127">アプリケーション イベント ログの関連するイベントまたはエラーを確認します。</span><span class="sxs-lookup"><span data-stu-id="f0752-127">Check the Application event log for associated events or errors.</span></span>  

  <span data-ttu-id="f0752-128">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="f0752-128">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="f0752-129">マスター シークレットを生成する方法</span><span class="sxs-lookup"><span data-stu-id="f0752-129">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  

- [<span data-ttu-id="f0752-130">マスター シークレットの管理</span><span class="sxs-lookup"><span data-stu-id="f0752-130">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)
