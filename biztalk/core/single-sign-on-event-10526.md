---
title: シングル サインオン:イベント 10526 |Microsoft Docs
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
ms.openlocfilehash: 924f6dee79b51740c62b302a0e57371fdd060470
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394324"
---
# <a name="single-sign-on-event-10526"></a><span data-ttu-id="bdebb-102">シングル サインオン:イベント 10526</span><span class="sxs-lookup"><span data-stu-id="bdebb-102">Single Sign-On: Event 10526</span></span>
## <a name="details"></a><span data-ttu-id="bdebb-103">詳細</span><span class="sxs-lookup"><span data-stu-id="bdebb-103">Details</span></span>  

|                 |                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="bdebb-104">製品名</span><span class="sxs-lookup"><span data-stu-id="bdebb-104">Product Name</span></span>   |                                                                     <span data-ttu-id="bdebb-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="bdebb-105">Enterprise Single Sign-On</span></span>                                                                     |
| <span data-ttu-id="bdebb-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="bdebb-106">Product Version</span></span> |                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                     |
|    <span data-ttu-id="bdebb-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="bdebb-107">Event ID</span></span>     |                                                                               <span data-ttu-id="bdebb-108">10526</span><span class="sxs-lookup"><span data-stu-id="bdebb-108">10526</span></span>                                                                               |
|  <span data-ttu-id="bdebb-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="bdebb-109">Event Source</span></span>   |                                                                              <span data-ttu-id="bdebb-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="bdebb-110">ENTSSO</span></span>                                                                               |
|    <span data-ttu-id="bdebb-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="bdebb-111">Component</span></span>    |                                                                                <span data-ttu-id="bdebb-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="bdebb-112">N\A</span></span>                                                                                |
|  <span data-ttu-id="bdebb-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="bdebb-113">Symbolic Name</span></span>  |                                                                 <span data-ttu-id="bdebb-114">SSO_ERROR_GENERATE_SECRET_FAILED</span><span class="sxs-lookup"><span data-stu-id="bdebb-114">SSO_ERROR_GENERATE_SECRET_FAILED</span></span>                                                                  |
|  <span data-ttu-id="bdebb-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="bdebb-115">Message Text</span></span>   | <span data-ttu-id="bdebb-116">新しいマスター secret.%r を生成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="bdebb-116">Failed to generate a new master secret.%r</span></span><br /><br /> <span data-ttu-id="bdebb-117">クライアント ユーザー: 1 %r</span><span class="sxs-lookup"><span data-stu-id="bdebb-117">Client User: %1%r</span></span><br /><br /> <span data-ttu-id="bdebb-118">クライアント コンピューター: %2 %r</span><span class="sxs-lookup"><span data-stu-id="bdebb-118">Client Computer:%2%r</span></span><br /><br /> <span data-ttu-id="bdebb-119">追跡 ID: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="bdebb-119">Tracking ID: %3%r</span></span><br /><br /> <span data-ttu-id="bdebb-120">エラー コード: %4</span><span class="sxs-lookup"><span data-stu-id="bdebb-120">Error Code: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="bdebb-121">説明</span><span class="sxs-lookup"><span data-stu-id="bdebb-121">Explanation</span></span>  
 <span data-ttu-id="bdebb-122">このエラー イベントは、新しいマスター シークレットを生成するユーザーの試行が失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="bdebb-122">This Error event indicates that a user attempt to generate a new master secret has failed.</span></span> <span data-ttu-id="bdebb-123">原因としては、アクセス許可 (マスター シークレットを生成するのには、SSO 管理者である必要があります) の問題またはバックアップ ファイルに、マスター シークレットの書き込みに問題があった可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bdebb-123">This might be due to permissions issues (you must be an SSO Administrator to generate the master secret) or possibly there were problems writing the master secret to the backup file.</span></span> <span data-ttu-id="bdebb-124">このような場合があります関連するメッセージ、アプリケーション イベント ログ。</span><span class="sxs-lookup"><span data-stu-id="bdebb-124">In these cases there should be related messages in the Application event log.</span></span>  

## <a name="user-action"></a><span data-ttu-id="bdebb-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="bdebb-125">User Action</span></span>  
 <span data-ttu-id="bdebb-126">このエラーを解決するには、以下の 1 つ以上の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="bdebb-126">To resolve this error, do one or more of the following:</span></span>  

- <span data-ttu-id="bdebb-127">アプリケーション イベント ログの関連するイベントまたはエラーを確認します。</span><span class="sxs-lookup"><span data-stu-id="bdebb-127">Check the Application event log for associated events or errors.</span></span>  

- <span data-ttu-id="bdebb-128">適切な SSO 管理者のアクセス許可があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bdebb-128">Check that you have the appropriate SSO Administrator permissions.</span></span>  

  <span data-ttu-id="bdebb-129">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="bdebb-129">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="bdebb-130">マスター シークレットを生成する方法</span><span class="sxs-lookup"><span data-stu-id="bdebb-130">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  

- [<span data-ttu-id="bdebb-131">マスター シークレットの管理</span><span class="sxs-lookup"><span data-stu-id="bdebb-131">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)
