---
title: Windows コンポーネントがインストールされていない |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc78ac0a-ee21-4633-afb3-1357efd29903
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d61ded5b2ddb077ff0851c20d673fad4f9de9d26
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975507"
---
# <a name="windows-components-may-not-be-installed"></a><span data-ttu-id="7c03d-102">Windows コンポーネントがインストールされていない可能性があります</span><span class="sxs-lookup"><span data-stu-id="7c03d-102">Windows components may not be installed</span></span>
## <a name="details"></a><span data-ttu-id="7c03d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="7c03d-103">Details</span></span>  

|                 |                                                                                                                                        |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="7c03d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="7c03d-104">Product Name</span></span>   |                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                           |
| <span data-ttu-id="7c03d-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="7c03d-105">Product Version</span></span> |                                       [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                       |
|    <span data-ttu-id="7c03d-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7c03d-106">Event ID</span></span>     |                                                                   <span data-ttu-id="7c03d-107">0</span><span class="sxs-lookup"><span data-stu-id="7c03d-107">0</span></span>                                                                    |
|  <span data-ttu-id="7c03d-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="7c03d-108">Event Source</span></span>   |                                                                   <span data-ttu-id="7c03d-109">0</span><span class="sxs-lookup"><span data-stu-id="7c03d-109">0</span></span>                                                                    |
|    <span data-ttu-id="7c03d-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7c03d-110">Component</span></span>    |                                                                   <span data-ttu-id="7c03d-111">0</span><span class="sxs-lookup"><span data-stu-id="7c03d-111">0</span></span>                                                                    |
|  <span data-ttu-id="7c03d-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="7c03d-112">Symbolic Name</span></span>  |                                                                   <span data-ttu-id="7c03d-113">0</span><span class="sxs-lookup"><span data-stu-id="7c03d-113">0</span></span>                                                                    |
|  <span data-ttu-id="7c03d-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="7c03d-114">Message Text</span></span>   | <span data-ttu-id="7c03d-115">次の Windows コンポーネントがインストールされていない可能性があります。 アプリケーション サーバー -&gt;インターネット インフォメーション サービス (IIS) の&gt;共通ファイル。</span><span class="sxs-lookup"><span data-stu-id="7c03d-115">The following Windows component may not be installed: Application Server -&gt; Internet Information Services (IIS) -&gt; Common Files.</span></span> |

## <a name="explanation"></a><span data-ttu-id="7c03d-116">説明</span><span class="sxs-lookup"><span data-stu-id="7c03d-116">Explanation</span></span>  
 <span data-ttu-id="7c03d-117">このエラーは、インターネット インフォメーション サービス (IIS) がローカル コンピューターにインストールされていない状態で公開が試行されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="7c03d-117">This error will occur when publishing is attempted without Internet Information Services (IIS) installed on the local computer.</span></span>  

## <a name="user-action"></a><span data-ttu-id="7c03d-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="7c03d-118">User Action</span></span>  
 <span data-ttu-id="7c03d-119">Windows 7 および Windows Vista SP2 の場合、IIS をローカル コンピューターにインストールし、次のように IIS を構成します。</span><span class="sxs-lookup"><span data-stu-id="7c03d-119">For Windows 7 and Windows Vista SP2, Install IIS on the local machine and configure IIS as follows:</span></span>  

1. <span data-ttu-id="7c03d-120">をクリックして**開始**、 をクリックして**コントロール パネルの **、 をクリック**プログラム**します。</span><span class="sxs-lookup"><span data-stu-id="7c03d-120">Click **Start**, click **Control Panel**, and click **Programs**.</span></span>  

2. <span data-ttu-id="7c03d-121">クリックして**有効にする Windows 機能のオンとオフを**します。</span><span class="sxs-lookup"><span data-stu-id="7c03d-121">Click **Turn Windows features on and off**.</span></span> <span data-ttu-id="7c03d-122">Windows の機能ウィザードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7c03d-122">The Windows Features Wizard appears.</span></span>  

3. <span data-ttu-id="7c03d-123">IIS コンポーネントを追加するために、IIS コンポーネントにチェックマークを付けます。</span><span class="sxs-lookup"><span data-stu-id="7c03d-123">To add, check the IIS component.</span></span>  

   <span data-ttu-id="7c03d-124">[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] および [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] の場合、IIS をローカル コンピューターにインストールし、次のように IIS を構成します。</span><span class="sxs-lookup"><span data-stu-id="7c03d-124">For [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] and [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], Install IIS on the local machine and configure IIS as follows:</span></span>  

4. <span data-ttu-id="7c03d-125">をクリックして**開始**、 をクリックして**コントロール パネルの **、 をクリック**管理ツール**します。</span><span class="sxs-lookup"><span data-stu-id="7c03d-125">Click **Start**, click **Control Panel**, and click **Administrative Tools**.</span></span>  

5. <span data-ttu-id="7c03d-126">クリックして**サーバー マネージャー**します。</span><span class="sxs-lookup"><span data-stu-id="7c03d-126">Click **Server Manager**.</span></span> <span data-ttu-id="7c03d-127">サーバー マネージャー ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7c03d-127">The Server Manger window appears.</span></span>  

6. <span data-ttu-id="7c03d-128">クリックして**役割の追加**役割の追加ウィザードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7c03d-128">Click **Add Roles**, Add Roles Wizard appears.</span></span>  

7. <span data-ttu-id="7c03d-129">IIS コンポーネントを追加するために、IIS コンポーネントを選択します。</span><span class="sxs-lookup"><span data-stu-id="7c03d-129">To add, Select IIS component.</span></span>
