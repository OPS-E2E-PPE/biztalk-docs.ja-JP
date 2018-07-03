---
title: 'シングル サインオン: イベント 10532 |Microsoft Docs'
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
ms.openlocfilehash: 135060013686ff24e4f2692bda0e8829189e1c4a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974851"
---
# <a name="single-sign-on-event-10532"></a><span data-ttu-id="622ec-102">シングル サインオン: イベント 10532</span><span class="sxs-lookup"><span data-stu-id="622ec-102">Single Sign-On: Event 10532</span></span>
## <a name="details"></a><span data-ttu-id="622ec-103">詳細</span><span class="sxs-lookup"><span data-stu-id="622ec-103">Details</span></span>  

|                 |                                                                                                                                                                                     |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="622ec-104">製品名</span><span class="sxs-lookup"><span data-stu-id="622ec-104">Product Name</span></span>   |                                                                              <span data-ttu-id="622ec-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="622ec-105">Enterprise Single Sign-On</span></span>                                                                              |
| <span data-ttu-id="622ec-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="622ec-106">Product Version</span></span> |                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                              |
|    <span data-ttu-id="622ec-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="622ec-107">Event ID</span></span>     |                                                                                        <span data-ttu-id="622ec-108">10532</span><span class="sxs-lookup"><span data-stu-id="622ec-108">10532</span></span>                                                                                        |
|  <span data-ttu-id="622ec-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="622ec-109">Event Source</span></span>   |                                                                                       <span data-ttu-id="622ec-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="622ec-110">ENTSSO</span></span>                                                                                        |
|    <span data-ttu-id="622ec-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="622ec-111">Component</span></span>    |                                                                                         <span data-ttu-id="622ec-112">CO</span><span class="sxs-lookup"><span data-stu-id="622ec-112">CO</span></span>                                                                                          |
|  <span data-ttu-id="622ec-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="622ec-113">Symbolic Name</span></span>  |                                                                             <span data-ttu-id="622ec-114">SSO_WARN_LOST_SECRET_SERVER</span><span class="sxs-lookup"><span data-stu-id="622ec-114">SSO_WARN_LOST_SECRET_SERVER</span></span>                                                                             |
|  <span data-ttu-id="622ec-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="622ec-115">Message Text</span></span>   | <span data-ttu-id="622ec-116">マスター シークレットを取得できませんでした。</span><span class="sxs-lookup"><span data-stu-id="622ec-116">Failed to retrieve master secrets.</span></span> <span data-ttu-id="622ec-117">マスター シークレット サーバー名が正しいこと、および利用可能であることを確認してください。%r</span><span class="sxs-lookup"><span data-stu-id="622ec-117">Verify that the master secret server name is correct and that it is available.%r</span></span><br /><br /> <span data-ttu-id="622ec-118">シークレット サーバー名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="622ec-118">Secret Server Name: %1%r</span></span><br /><br /> <span data-ttu-id="622ec-119">エラー コード: %2</span><span class="sxs-lookup"><span data-stu-id="622ec-119">Error Code: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="622ec-120">説明</span><span class="sxs-lookup"><span data-stu-id="622ec-120">Explanation</span></span>  
 <span data-ttu-id="622ec-121">この警告イベントは、マスター シークレットの取得要求が失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="622ec-121">This Warning event indicates that a request to get the master secret has failed.</span></span> <span data-ttu-id="622ec-122">エンタープライズ シングル サインオン サービスがサーバー上で実行されていないことが原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="622ec-122">This might be because the Enterprise Single Sign-On service is not running on the server.</span></span>  

## <a name="user-action"></a><span data-ttu-id="622ec-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="622ec-123">User Action</span></span>  
 <span data-ttu-id="622ec-124">この警告を解消するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="622ec-124">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="622ec-125">関連するイベントまたはエラーについては、アプリケーション イベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="622ec-125">Check the Application event log for associated events or errors.</span></span>  

- <span data-ttu-id="622ec-126">マスター シークレット サーバー名が正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="622ec-126">Verify the master secret server name is correct.</span></span>  

- <span data-ttu-id="622ec-127">マスター シークレット サーバーがオンラインであり、エンタープライズ シングル サインオン サービスが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="622ec-127">Verify the master secret server is online and that the Enterprise Single Sign-On service is running.</span></span>  

  <span data-ttu-id="622ec-128">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="622ec-128">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="622ec-129">マスター シークレットを生成する方法</span><span class="sxs-lookup"><span data-stu-id="622ec-129">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  

- [<span data-ttu-id="622ec-130">マスター シークレットの管理</span><span class="sxs-lookup"><span data-stu-id="622ec-130">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)
