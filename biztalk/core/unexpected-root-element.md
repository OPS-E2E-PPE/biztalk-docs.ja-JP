---
title: 予期しないルート要素 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ecccf57e-9295-4a6d-95b6-efec662478cf
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec4ed8e39a05f81984dca21794eca3d829ba8f42
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973032"
---
# <a name="unexpected-root-element"></a><span data-ttu-id="7018a-102">ルート要素が正しくありません</span><span class="sxs-lookup"><span data-stu-id="7018a-102">Unexpected root element</span></span>
## <a name="details"></a><span data-ttu-id="7018a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="7018a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7018a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="7018a-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="7018a-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="7018a-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="7018a-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7018a-106">Event ID</span></span>|<span data-ttu-id="7018a-107">0</span><span class="sxs-lookup"><span data-stu-id="7018a-107">0</span></span>|  
|<span data-ttu-id="7018a-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="7018a-108">Event Source</span></span>|<span data-ttu-id="7018a-109">0</span><span class="sxs-lookup"><span data-stu-id="7018a-109">0</span></span>|  
|<span data-ttu-id="7018a-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7018a-110">Component</span></span>|<span data-ttu-id="7018a-111">0</span><span class="sxs-lookup"><span data-stu-id="7018a-111">0</span></span>|  
|<span data-ttu-id="7018a-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="7018a-112">Symbolic Name</span></span>|<span data-ttu-id="7018a-113">0</span><span class="sxs-lookup"><span data-stu-id="7018a-113">0</span></span>|  
|<span data-ttu-id="7018a-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="7018a-114">Message Text</span></span>|<span data-ttu-id="7018a-115">ルート要素が正しくありません</span><span class="sxs-lookup"><span data-stu-id="7018a-115">Unexpected root element</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7018a-116">説明</span><span class="sxs-lookup"><span data-stu-id="7018a-116">Explanation</span></span>  
 <span data-ttu-id="7018a-117">ヘッダー プロパティに含まれていない\<ヘッダー\>...\</headers\>形式です。</span><span class="sxs-lookup"><span data-stu-id="7018a-117">Header property is not in \<headers\>….\</headers\> format.</span></span> <span data-ttu-id="7018a-118">通常、この状況は InboundHeaders および OutboundCustomHeaders に適用されます。</span><span class="sxs-lookup"><span data-stu-id="7018a-118">This situation normally applies to InboundHeaders and OutboundCustomHeaders.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7018a-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="7018a-119">User Action</span></span>  
 <span data-ttu-id="7018a-120">ヘッダー プロパティの形式であることを確認\<ヘッダー\>しています.\</headers\>です。</span><span class="sxs-lookup"><span data-stu-id="7018a-120">Ensure that header property is in the format of  \<headers\>…\</headers\>.</span></span>