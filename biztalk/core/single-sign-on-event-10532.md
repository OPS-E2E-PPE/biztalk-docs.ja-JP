---
title: 'シングル サインオン: イベント 10532 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae2112bc-b53c-4d99-9dc1-a2f55dda4665
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7a9d477ec54a3c959f2afdf4c687c65b88523ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269754"
---
# <a name="single-sign-on-event-10532"></a><span data-ttu-id="9e1bd-102">シングル サインオン: イベント 10532</span><span class="sxs-lookup"><span data-stu-id="9e1bd-102">Single Sign-On: Event 10532</span></span>
## <a name="details"></a><span data-ttu-id="9e1bd-103">詳細</span><span class="sxs-lookup"><span data-stu-id="9e1bd-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9e1bd-104">製品名</span><span class="sxs-lookup"><span data-stu-id="9e1bd-104">Product Name</span></span>|<span data-ttu-id="9e1bd-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="9e1bd-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="9e1bd-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="9e1bd-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="9e1bd-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="9e1bd-107">Event ID</span></span>|<span data-ttu-id="9e1bd-108">10532</span><span class="sxs-lookup"><span data-stu-id="9e1bd-108">10532</span></span>|  
|<span data-ttu-id="9e1bd-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="9e1bd-109">Event Source</span></span>|<span data-ttu-id="9e1bd-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="9e1bd-110">ENTSSO</span></span>|  
|<span data-ttu-id="9e1bd-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9e1bd-111">Component</span></span>|<span data-ttu-id="9e1bd-112">CO</span><span class="sxs-lookup"><span data-stu-id="9e1bd-112">CO</span></span>|  
|<span data-ttu-id="9e1bd-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="9e1bd-113">Symbolic Name</span></span>|<span data-ttu-id="9e1bd-114">SSO_WARN_LOST_SECRET_SERVER</span><span class="sxs-lookup"><span data-stu-id="9e1bd-114">SSO_WARN_LOST_SECRET_SERVER</span></span>|  
|<span data-ttu-id="9e1bd-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="9e1bd-115">Message Text</span></span>|<span data-ttu-id="9e1bd-116">マスター シークレットを取得できませんでした。</span><span class="sxs-lookup"><span data-stu-id="9e1bd-116">Failed to retrieve master secrets.</span></span> <span data-ttu-id="9e1bd-117">マスター シークレット サーバー名が正しいこと、および利用可能であることを確認してください。%r</span><span class="sxs-lookup"><span data-stu-id="9e1bd-117">Verify that the master secret server name is correct and that it is available.%r</span></span><br /><br /> <span data-ttu-id="9e1bd-118">シークレット サーバー名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="9e1bd-118">Secret Server Name: %1%r</span></span><br /><br /> <span data-ttu-id="9e1bd-119">エラー コード: %2</span><span class="sxs-lookup"><span data-stu-id="9e1bd-119">Error Code: %2</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9e1bd-120">説明</span><span class="sxs-lookup"><span data-stu-id="9e1bd-120">Explanation</span></span>  
 <span data-ttu-id="9e1bd-121">この警告イベントは、マスター シークレットの取得要求が失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="9e1bd-121">This Warning event indicates that a request to get the master secret has failed.</span></span> <span data-ttu-id="9e1bd-122">エンタープライズ シングル サインオン サービスがサーバー上で実行されていないことが原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9e1bd-122">This might be because the Enterprise Single Sign-On service is not running on the server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9e1bd-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="9e1bd-123">User Action</span></span>  
 <span data-ttu-id="9e1bd-124">この警告を解消するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="9e1bd-124">To resolve this warning, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="9e1bd-125">関連するイベントまたはエラーについては、アプリケーション イベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="9e1bd-125">Check the Application event log for associated events or errors.</span></span>  
  
-   <span data-ttu-id="9e1bd-126">マスター シークレット サーバー名が正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9e1bd-126">Verify the master secret server name is correct.</span></span>  
  
-   <span data-ttu-id="9e1bd-127">マスター シークレット サーバーがオンラインであり、エンタープライズ シングル サインオン サービスが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9e1bd-127">Verify the master secret server is online and that the Enterprise Single Sign-On service is running.</span></span>  
  
 <span data-ttu-id="9e1bd-128">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="9e1bd-128">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="9e1bd-129">マスター シークレットを生成する方法</span><span class="sxs-lookup"><span data-stu-id="9e1bd-129">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  
  
-   [<span data-ttu-id="9e1bd-130">マスタ シークレットの管理</span><span class="sxs-lookup"><span data-stu-id="9e1bd-130">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)