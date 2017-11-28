---
title: "サービス エンドポイント構成をインポートできません。 | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6dae5154-04e2-4d9b-b2b2-85313683fd9e
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4100435706ab26c0f4ab99dea4d2088ecad1c948
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="unable-to-import-service-endpoint-configuration"></a><span data-ttu-id="47864-103">サービス エンドポイント構成をインポートできません。</span><span class="sxs-lookup"><span data-stu-id="47864-103">Unable to import service endpoint configuration.</span></span>
## <a name="details"></a><span data-ttu-id="47864-104">詳細</span><span class="sxs-lookup"><span data-stu-id="47864-104">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="47864-105">製品名</span><span class="sxs-lookup"><span data-stu-id="47864-105">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="47864-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="47864-106">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="47864-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="47864-107">Event ID</span></span>|<span data-ttu-id="47864-108">0</span><span class="sxs-lookup"><span data-stu-id="47864-108">0</span></span>|  
|<span data-ttu-id="47864-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="47864-109">Event Source</span></span>|<span data-ttu-id="47864-110">0</span><span class="sxs-lookup"><span data-stu-id="47864-110">0</span></span>|  
|<span data-ttu-id="47864-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="47864-111">Component</span></span>|<span data-ttu-id="47864-112">0</span><span class="sxs-lookup"><span data-stu-id="47864-112">0</span></span>|  
|<span data-ttu-id="47864-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="47864-113">Symbolic Name</span></span>|<span data-ttu-id="47864-114">0</span><span class="sxs-lookup"><span data-stu-id="47864-114">0</span></span>|  
|<span data-ttu-id="47864-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="47864-115">Message Text</span></span>|<span data-ttu-id="47864-116">サービス エンドポイント構成をインポートできません</span><span class="sxs-lookup"><span data-stu-id="47864-116">Unable to import service endpoint configuration</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="47864-117">説明</span><span class="sxs-lookup"><span data-stu-id="47864-117">Explanation</span></span>  
 <span data-ttu-id="47864-118">このエラーについては、複数の説明が考えられます。</span><span class="sxs-lookup"><span data-stu-id="47864-118">There could be more than one explanation for this error.</span></span> <span data-ttu-id="47864-119">構成ファイルに無効な文字が含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="47864-119">The configuration file may contain invalid characters.</span></span> <span data-ttu-id="47864-120">ルート要素が欠落している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="47864-120">The root element may be missing.</span></span> <span data-ttu-id="47864-121">ルート レベルのデータが無効な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="47864-121">The data at the root level may be invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="47864-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="47864-122">User Action</span></span>  
 <span data-ttu-id="47864-123">構成ファイルが正しいかどうかを検証します。</span><span class="sxs-lookup"><span data-stu-id="47864-123">Verify the validity of the configuration file.</span></span> <span data-ttu-id="47864-124">サービス構成エディターで、構成ファイルを開く (**svcConfigEditor.exe**) の各プロパティを確認してください。</span><span class="sxs-lookup"><span data-stu-id="47864-124">Try to open the configuration file with the Service Configuration Editor (**svcConfigEditor.exe**) and verify each property.</span></span>