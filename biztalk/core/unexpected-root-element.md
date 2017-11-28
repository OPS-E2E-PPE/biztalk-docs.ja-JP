---
title: "予期しないルート要素 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ecccf57e-9295-4a6d-95b6-efec662478cf
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5119b9b896b3b37b24b9b3151c5e11664dda8774
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="unexpected-root-element"></a><span data-ttu-id="fbbcb-102">ルート要素が正しくありません</span><span class="sxs-lookup"><span data-stu-id="fbbcb-102">Unexpected root element</span></span>
## <a name="details"></a><span data-ttu-id="fbbcb-103">詳細</span><span class="sxs-lookup"><span data-stu-id="fbbcb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fbbcb-104">製品名</span><span class="sxs-lookup"><span data-stu-id="fbbcb-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="fbbcb-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="fbbcb-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="fbbcb-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="fbbcb-106">Event ID</span></span>|<span data-ttu-id="fbbcb-107">0</span><span class="sxs-lookup"><span data-stu-id="fbbcb-107">0</span></span>|  
|<span data-ttu-id="fbbcb-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="fbbcb-108">Event Source</span></span>|<span data-ttu-id="fbbcb-109">0</span><span class="sxs-lookup"><span data-stu-id="fbbcb-109">0</span></span>|  
|<span data-ttu-id="fbbcb-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="fbbcb-110">Component</span></span>|<span data-ttu-id="fbbcb-111">0</span><span class="sxs-lookup"><span data-stu-id="fbbcb-111">0</span></span>|  
|<span data-ttu-id="fbbcb-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="fbbcb-112">Symbolic Name</span></span>|<span data-ttu-id="fbbcb-113">0</span><span class="sxs-lookup"><span data-stu-id="fbbcb-113">0</span></span>|  
|<span data-ttu-id="fbbcb-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="fbbcb-114">Message Text</span></span>|<span data-ttu-id="fbbcb-115">ルート要素が正しくありません</span><span class="sxs-lookup"><span data-stu-id="fbbcb-115">Unexpected root element</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fbbcb-116">説明</span><span class="sxs-lookup"><span data-stu-id="fbbcb-116">Explanation</span></span>  
 <span data-ttu-id="fbbcb-117">ヘッダー プロパティに含まれていない\<ヘッダー >...\</headers > の形式です。</span><span class="sxs-lookup"><span data-stu-id="fbbcb-117">Header property is not in \<headers>….\</headers> format.</span></span> <span data-ttu-id="fbbcb-118">通常、この状況は InboundHeaders および OutboundCustomHeaders に適用されます。</span><span class="sxs-lookup"><span data-stu-id="fbbcb-118">This situation normally applies to InboundHeaders and OutboundCustomHeaders.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fbbcb-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="fbbcb-119">User Action</span></span>  
 <span data-ttu-id="fbbcb-120">ヘッダー プロパティの形式であることを確認\<ヘッダー >.\</headers >。</span><span class="sxs-lookup"><span data-stu-id="fbbcb-120">Ensure that header property is in the format of  \<headers>…\</headers>.</span></span>