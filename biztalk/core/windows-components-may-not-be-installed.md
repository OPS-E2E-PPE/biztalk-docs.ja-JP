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
ms.openlocfilehash: 79e9855a3e9719f1a95801683a7b72da9c5ce86b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65240296"
---
# <a name="windows-components-may-not-be-installed"></a><span data-ttu-id="320ce-102">Windows コンポーネントがインストールされていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="320ce-102">Windows components may not be installed</span></span>
## <a name="details"></a><span data-ttu-id="320ce-103">詳細</span><span class="sxs-lookup"><span data-stu-id="320ce-103">Details</span></span>  

|                 |                                                                                                                                        |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="320ce-104">製品名</span><span class="sxs-lookup"><span data-stu-id="320ce-104">Product Name</span></span>   |                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                           |
| <span data-ttu-id="320ce-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="320ce-105">Product Version</span></span> |                                       [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                       |
|    <span data-ttu-id="320ce-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="320ce-106">Event ID</span></span>     |                                                                   <span data-ttu-id="320ce-107">0</span><span class="sxs-lookup"><span data-stu-id="320ce-107">0</span></span>                                                                    |
|  <span data-ttu-id="320ce-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="320ce-108">Event Source</span></span>   |                                                                   <span data-ttu-id="320ce-109">0</span><span class="sxs-lookup"><span data-stu-id="320ce-109">0</span></span>                                                                    |
|    <span data-ttu-id="320ce-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="320ce-110">Component</span></span>    |                                                                   <span data-ttu-id="320ce-111">0</span><span class="sxs-lookup"><span data-stu-id="320ce-111">0</span></span>                                                                    |
|  <span data-ttu-id="320ce-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="320ce-112">Symbolic Name</span></span>  |                                                                   <span data-ttu-id="320ce-113">0</span><span class="sxs-lookup"><span data-stu-id="320ce-113">0</span></span>                                                                    |
|  <span data-ttu-id="320ce-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="320ce-114">Message Text</span></span>   | <span data-ttu-id="320ce-115">次の Windows コンポーネントがインストールされていない可能性があります。アプリケーション サーバー -&gt;インターネット インフォメーション サービス (IIS) の&gt;共通ファイル。</span><span class="sxs-lookup"><span data-stu-id="320ce-115">The following Windows component may not be installed: Application Server -&gt; Internet Information Services (IIS) -&gt; Common Files.</span></span> |

## <a name="explanation"></a><span data-ttu-id="320ce-116">説明</span><span class="sxs-lookup"><span data-stu-id="320ce-116">Explanation</span></span>  
 <span data-ttu-id="320ce-117">発行はなくインターネット インフォメーション サービス (IIS)、ローカル コンピューターにインストールしようとした場合、このエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="320ce-117">This error will occur when publishing is attempted without Internet Information Services (IIS) installed on the local computer.</span></span>  

## <a name="user-action"></a><span data-ttu-id="320ce-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="320ce-118">User Action</span></span>  
 <span data-ttu-id="320ce-119">Windows 7 と Windows Vista SP2 では、ローカル IIS のインストールはマシンし、次のように IIS を構成します。</span><span class="sxs-lookup"><span data-stu-id="320ce-119">For Windows 7 and Windows Vista SP2, Install IIS on the local machine and configure IIS as follows:</span></span>  

1. <span data-ttu-id="320ce-120">をクリックして**開始**、 をクリックして**コントロール パネルの **、 をクリック**プログラム**します。</span><span class="sxs-lookup"><span data-stu-id="320ce-120">Click **Start**, click **Control Panel**, and click **Programs**.</span></span>  

2. <span data-ttu-id="320ce-121">クリックして**有効にする Windows 機能のオンとオフを**します。</span><span class="sxs-lookup"><span data-stu-id="320ce-121">Click **Turn Windows features on and off**.</span></span> <span data-ttu-id="320ce-122">Windows 機能のウィザードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="320ce-122">The Windows Features Wizard appears.</span></span>  

3. <span data-ttu-id="320ce-123">追加するには、IIS コンポーネントを確認します。</span><span class="sxs-lookup"><span data-stu-id="320ce-123">To add, check the IIS component.</span></span>  

   <span data-ttu-id="320ce-124">[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]と[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]をローカルの IIS のインストールはマシンし、次のように IIS を構成します。</span><span class="sxs-lookup"><span data-stu-id="320ce-124">For [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] and [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], Install IIS on the local machine and configure IIS as follows:</span></span>  

4. <span data-ttu-id="320ce-125">をクリックして**開始**、 をクリックして**コントロール パネルの **、 をクリック**管理ツール**します。</span><span class="sxs-lookup"><span data-stu-id="320ce-125">Click **Start**, click **Control Panel**, and click **Administrative Tools**.</span></span>  

5. <span data-ttu-id="320ce-126">クリックして**サーバー マネージャー**します。</span><span class="sxs-lookup"><span data-stu-id="320ce-126">Click **Server Manager**.</span></span> <span data-ttu-id="320ce-127">サーバー マネージャー ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="320ce-127">The Server Manger window appears.</span></span>  

6. <span data-ttu-id="320ce-128">クリックして**役割の追加**役割の追加ウィザードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="320ce-128">Click **Add Roles**, Add Roles Wizard appears.</span></span>  

7. <span data-ttu-id="320ce-129">追加するには、IIS コンポーネントを選択します。</span><span class="sxs-lookup"><span data-stu-id="320ce-129">To add, Select IIS component.</span></span>
