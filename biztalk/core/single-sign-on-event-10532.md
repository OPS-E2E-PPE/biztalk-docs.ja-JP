---
title: シングル サインオン:イベント 10532 |Microsoft Docs
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
ms.openlocfilehash: 3ea52d8e64f5a59a633a6e22eef7220f44b36f77
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262338"
---
# <a name="single-sign-on-event-10532"></a><span data-ttu-id="18280-102">シングル サインオン:イベント 10532</span><span class="sxs-lookup"><span data-stu-id="18280-102">Single Sign-On: Event 10532</span></span>
## <a name="details"></a><span data-ttu-id="18280-103">詳細</span><span class="sxs-lookup"><span data-stu-id="18280-103">Details</span></span>  

|                 |                                                                                                                                                                                     |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="18280-104">製品名</span><span class="sxs-lookup"><span data-stu-id="18280-104">Product Name</span></span>   |                                                                              <span data-ttu-id="18280-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="18280-105">Enterprise Single Sign-On</span></span>                                                                              |
| <span data-ttu-id="18280-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="18280-106">Product Version</span></span> |                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                              |
|    <span data-ttu-id="18280-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="18280-107">Event ID</span></span>     |                                                                                        <span data-ttu-id="18280-108">10532</span><span class="sxs-lookup"><span data-stu-id="18280-108">10532</span></span>                                                                                        |
|  <span data-ttu-id="18280-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="18280-109">Event Source</span></span>   |                                                                                       <span data-ttu-id="18280-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="18280-110">ENTSSO</span></span>                                                                                        |
|    <span data-ttu-id="18280-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="18280-111">Component</span></span>    |                                                                                         <span data-ttu-id="18280-112">CO</span><span class="sxs-lookup"><span data-stu-id="18280-112">CO</span></span>                                                                                          |
|  <span data-ttu-id="18280-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="18280-113">Symbolic Name</span></span>  |                                                                             <span data-ttu-id="18280-114">SSO_WARN_LOST_SECRET_SERVER</span><span class="sxs-lookup"><span data-stu-id="18280-114">SSO_WARN_LOST_SECRET_SERVER</span></span>                                                                             |
|  <span data-ttu-id="18280-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="18280-115">Message Text</span></span>   | <span data-ttu-id="18280-116">マスター シークレットを取得できませんでした。</span><span class="sxs-lookup"><span data-stu-id="18280-116">Failed to retrieve master secrets.</span></span> <span data-ttu-id="18280-117">マスター シークレット サーバー名が正しいことおよび available.%r であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="18280-117">Verify that the master secret server name is correct and that it is available.%r</span></span><br /><br /> <span data-ttu-id="18280-118">シークレット サーバー名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="18280-118">Secret Server Name: %1%r</span></span><br /><br /> <span data-ttu-id="18280-119">エラー コード: %2</span><span class="sxs-lookup"><span data-stu-id="18280-119">Error Code: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="18280-120">説明</span><span class="sxs-lookup"><span data-stu-id="18280-120">Explanation</span></span>  
 <span data-ttu-id="18280-121">この警告イベントは、マスター シークレットを取得する要求が失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="18280-121">This Warning event indicates that a request to get the master secret has failed.</span></span> <span data-ttu-id="18280-122">エンタープライズ シングル サインオン サービスがサーバーで実行されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="18280-122">This might be because the Enterprise Single Sign-On service is not running on the server.</span></span>  

## <a name="user-action"></a><span data-ttu-id="18280-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="18280-123">User Action</span></span>  
 <span data-ttu-id="18280-124">この警告を解決するには、次の 1 つ以上の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="18280-124">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="18280-125">アプリケーション イベント ログの関連するイベントまたはエラーを確認します。</span><span class="sxs-lookup"><span data-stu-id="18280-125">Check the Application event log for associated events or errors.</span></span>  

- <span data-ttu-id="18280-126">マスター シークレット サーバー名が正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="18280-126">Verify the master secret server name is correct.</span></span>  

- <span data-ttu-id="18280-127">マスター シークレット サーバーがオンラインであり、エンタープライズ シングル サインオン サービスが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="18280-127">Verify the master secret server is online and that the Enterprise Single Sign-On service is running.</span></span>  

  <span data-ttu-id="18280-128">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="18280-128">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="18280-129">マスター シークレットを生成する方法</span><span class="sxs-lookup"><span data-stu-id="18280-129">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  

- [<span data-ttu-id="18280-130">マスター シークレットの管理</span><span class="sxs-lookup"><span data-stu-id="18280-130">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)
