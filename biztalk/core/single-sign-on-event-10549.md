---
title: シングル サインオン:イベント 10549 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a18eb63-700c-4f49-acc4-890abe2a00ff
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac97f659dfc1f3b152df36c136fc45c3ef4238d8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243379"
---
# <a name="single-sign-on-event-10549"></a><span data-ttu-id="30d05-102">シングル サインオン:イベント 10549</span><span class="sxs-lookup"><span data-stu-id="30d05-102">Single Sign-On: Event 10549</span></span>
## <a name="details"></a><span data-ttu-id="30d05-103">詳細</span><span class="sxs-lookup"><span data-stu-id="30d05-103">Details</span></span>  

|                 |                                                                                                                                                                                          |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="30d05-104">製品名</span><span class="sxs-lookup"><span data-stu-id="30d05-104">Product Name</span></span>   |                                                                                <span data-ttu-id="30d05-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="30d05-105">Enterprise Single Sign-On</span></span>                                                                                 |
| <span data-ttu-id="30d05-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="30d05-106">Product Version</span></span> |                                                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                |
|    <span data-ttu-id="30d05-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="30d05-107">Event ID</span></span>     |                                                                                          <span data-ttu-id="30d05-108">10549</span><span class="sxs-lookup"><span data-stu-id="30d05-108">10549</span></span>                                                                                           |
|  <span data-ttu-id="30d05-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="30d05-109">Event Source</span></span>   |                                                                                          <span data-ttu-id="30d05-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="30d05-110">ENTSSO</span></span>                                                                                          |
|    <span data-ttu-id="30d05-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="30d05-111">Component</span></span>    |                                                                                            <span data-ttu-id="30d05-112">CO</span><span class="sxs-lookup"><span data-stu-id="30d05-112">CO</span></span>                                                                                            |
|  <span data-ttu-id="30d05-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="30d05-113">Symbolic Name</span></span>  |                                                                             <span data-ttu-id="30d05-114">SSO_ERROR_CREATE_DATABASE_FAILED</span><span class="sxs-lookup"><span data-stu-id="30d05-114">SSO_ERROR_CREATE_DATABASE_FAILED</span></span>                                                                             |
|  <span data-ttu-id="30d05-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="30d05-115">Message Text</span></span>   | <span data-ttu-id="30d05-116">SSO データベースの failed.%r を作成および初期化</span><span class="sxs-lookup"><span data-stu-id="30d05-116">Creation and initialization of the SSO database failed.%r</span></span><br /><br /> <span data-ttu-id="30d05-117">SQL Server 名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="30d05-117">SQL Server Name: %1%r</span></span><br /><br /> <span data-ttu-id="30d05-118">SSO データベース名: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="30d05-118">SSO Database Name: %2%r</span></span><br /><br /> <span data-ttu-id="30d05-119">クライアント ユーザー: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="30d05-119">Client User: %3%r</span></span><br /><br /> <span data-ttu-id="30d05-120">エラー コード: %4</span><span class="sxs-lookup"><span data-stu-id="30d05-120">Error Code: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="30d05-121">説明</span><span class="sxs-lookup"><span data-stu-id="30d05-121">Explanation</span></span>  
 <span data-ttu-id="30d05-122">このエラーは、SSO データベースを作成および初期化が失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="30d05-122">This Error indicates that creation and initialization of the SSO database failed.</span></span>  

## <a name="user-action"></a><span data-ttu-id="30d05-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="30d05-123">User Action</span></span>  
 <span data-ttu-id="30d05-124">このエラーは次を解決するには。</span><span class="sxs-lookup"><span data-stu-id="30d05-124">To resolve this error do the following:</span></span>  

- <span data-ttu-id="30d05-125">関連付けられているメッセージのシステムおよびアプリケーション イベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="30d05-125">Check the system and application event logs for associated messages.</span></span>  

- <span data-ttu-id="30d05-126">セットアップを再度実行します。</span><span class="sxs-lookup"><span data-stu-id="30d05-126">Run Setup again.</span></span>  

  <span data-ttu-id="30d05-127">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="30d05-127">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="30d05-128">SSO のインストール</span><span class="sxs-lookup"><span data-stu-id="30d05-128">Installing SSO</span></span>](../core/installing-sso.md)
