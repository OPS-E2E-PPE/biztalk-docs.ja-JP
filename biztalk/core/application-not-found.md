---
title: アプリケーションが見つかりません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c37680b2-b38a-40f3-bb27-7b7281299ec3
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d935ca74ce1fd6b8137807f14184d4fa22f3ade
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359036"
---
# <a name="application-not-found"></a><span data-ttu-id="fd50c-102">アプリケーションが見つかりません</span><span class="sxs-lookup"><span data-stu-id="fd50c-102">Application not found</span></span>
## <a name="details"></a><span data-ttu-id="fd50c-103">詳細</span><span class="sxs-lookup"><span data-stu-id="fd50c-103">Details</span></span>  

|                 |                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="fd50c-104">製品名</span><span class="sxs-lookup"><span data-stu-id="fd50c-104">Product Name</span></span>   |           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]            |
| <span data-ttu-id="fd50c-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="fd50c-105">Product Version</span></span> |                       [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                        |
|    <span data-ttu-id="fd50c-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="fd50c-106">Event ID</span></span>     |                                                    <span data-ttu-id="fd50c-107">0</span><span class="sxs-lookup"><span data-stu-id="fd50c-107">0</span></span>                                                    |
|  <span data-ttu-id="fd50c-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="fd50c-108">Event Source</span></span>   |                                                    <span data-ttu-id="fd50c-109">0</span><span class="sxs-lookup"><span data-stu-id="fd50c-109">0</span></span>                                                    |
|    <span data-ttu-id="fd50c-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="fd50c-110">Component</span></span>    |                                                    <span data-ttu-id="fd50c-111">0</span><span class="sxs-lookup"><span data-stu-id="fd50c-111">0</span></span>                                                    |
|  <span data-ttu-id="fd50c-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="fd50c-112">Symbolic Name</span></span>  |                                                    <span data-ttu-id="fd50c-113">0</span><span class="sxs-lookup"><span data-stu-id="fd50c-113">0</span></span>                                                    |
|  <span data-ttu-id="fd50c-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="fd50c-114">Message Text</span></span>   | <span data-ttu-id="fd50c-115">アプリケーション"{0}"が見つかりませんでした。アプリケーションが既定の BizTalk 構成データベースに存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="fd50c-115">Application "{0}" not found.Verify the application exists in the default BizTalk configuration database</span></span> |

## <a name="explanation"></a><span data-ttu-id="fd50c-116">説明</span><span class="sxs-lookup"><span data-stu-id="fd50c-116">Explanation</span></span>  
 <span data-ttu-id="fd50c-117">このエラーは、BizTalk は BizTalk データベースに存在しないアプリケーションを使用したことを示します。</span><span class="sxs-lookup"><span data-stu-id="fd50c-117">This error indicates BizTalk is using an application that does not exist in the BizTalk databases.</span></span>  

## <a name="user-action"></a><span data-ttu-id="fd50c-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="fd50c-118">User Action</span></span>  
 <span data-ttu-id="fd50c-119">有効なアプリケーションを構成するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="fd50c-119">Use the following procedure to configure a valid application.</span></span>  

#### <a name="to-configure-a-valid-application"></a><span data-ttu-id="fd50c-120">有効なアプリケーションを構成するには</span><span class="sxs-lookup"><span data-stu-id="fd50c-120">To configure a valid application</span></span>  

1. <span data-ttu-id="fd50c-121">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="fd50c-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="fd50c-122">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="fd50c-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand **Applications**.</span></span>  

3. <span data-ttu-id="fd50c-123">アプリケーションがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fd50c-123">Ensure that the application exists there.</span></span> <span data-ttu-id="fd50c-124">それ以外の場合は、別の有効なアプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="fd50c-124">If not, select a different valid application.</span></span>
