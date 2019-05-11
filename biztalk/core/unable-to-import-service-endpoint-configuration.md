---
title: サービス エンドポイント構成をインポートできません。 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6dae5154-04e2-4d9b-b2b2-85313683fd9e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85d6fb8006020c47dcec56aa2a173fa36a1aff28
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292759"
---
# <a name="unable-to-import-service-endpoint-configuration"></a><span data-ttu-id="027cc-103">サービス エンドポイント構成をインポートできません。</span><span class="sxs-lookup"><span data-stu-id="027cc-103">Unable to import service endpoint configuration.</span></span>
## <a name="details"></a><span data-ttu-id="027cc-104">詳細</span><span class="sxs-lookup"><span data-stu-id="027cc-104">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="027cc-105">製品名</span><span class="sxs-lookup"><span data-stu-id="027cc-105">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="027cc-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="027cc-106">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="027cc-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="027cc-107">Event ID</span></span>     |                                         <span data-ttu-id="027cc-108">0</span><span class="sxs-lookup"><span data-stu-id="027cc-108">0</span></span>                                          |
|  <span data-ttu-id="027cc-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="027cc-109">Event Source</span></span>   |                                         <span data-ttu-id="027cc-110">0</span><span class="sxs-lookup"><span data-stu-id="027cc-110">0</span></span>                                          |
|    <span data-ttu-id="027cc-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="027cc-111">Component</span></span>    |                                         <span data-ttu-id="027cc-112">0</span><span class="sxs-lookup"><span data-stu-id="027cc-112">0</span></span>                                          |
|  <span data-ttu-id="027cc-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="027cc-113">Symbolic Name</span></span>  |                                         <span data-ttu-id="027cc-114">0</span><span class="sxs-lookup"><span data-stu-id="027cc-114">0</span></span>                                          |
|  <span data-ttu-id="027cc-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="027cc-115">Message Text</span></span>   |                  <span data-ttu-id="027cc-116">サービス エンドポイント構成をインポートできません。</span><span class="sxs-lookup"><span data-stu-id="027cc-116">Unable to import service endpoint configuration</span></span>                   |
  
## <a name="explanation"></a><span data-ttu-id="027cc-117">説明</span><span class="sxs-lookup"><span data-stu-id="027cc-117">Explanation</span></span>  
 <span data-ttu-id="027cc-118">このエラーの 1 つ以上の説明があります。</span><span class="sxs-lookup"><span data-stu-id="027cc-118">There could be more than one explanation for this error.</span></span> <span data-ttu-id="027cc-119">構成ファイルには、無効な文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="027cc-119">The configuration file may contain invalid characters.</span></span> <span data-ttu-id="027cc-120">ルート要素がない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="027cc-120">The root element may be missing.</span></span> <span data-ttu-id="027cc-121">ルート レベルのデータは、有効でない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="027cc-121">The data at the root level may be invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="027cc-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="027cc-122">User Action</span></span>  
 <span data-ttu-id="027cc-123">構成ファイルの有効性を確認します。</span><span class="sxs-lookup"><span data-stu-id="027cc-123">Verify the validity of the configuration file.</span></span> <span data-ttu-id="027cc-124">構成ファイル、サービス構成エディターを開く (**svcConfigEditor.exe**) 各プロパティを確認します。</span><span class="sxs-lookup"><span data-stu-id="027cc-124">Try to open the configuration file with the Service Configuration Editor (**svcConfigEditor.exe**) and verify each property.</span></span>