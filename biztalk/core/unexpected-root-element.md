---
title: 予期しないルート要素 |Microsoft Docs
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
ms.openlocfilehash: b0e54e0eac7e3f8ae54d23417033388bc493b0ab
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981635"
---
# <a name="unexpected-root-element"></a><span data-ttu-id="aa28e-102">ルート要素が正しくありません</span><span class="sxs-lookup"><span data-stu-id="aa28e-102">Unexpected root element</span></span>
## <a name="details"></a><span data-ttu-id="aa28e-103">詳細</span><span class="sxs-lookup"><span data-stu-id="aa28e-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="aa28e-104">製品名</span><span class="sxs-lookup"><span data-stu-id="aa28e-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="aa28e-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="aa28e-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="aa28e-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="aa28e-106">Event ID</span></span>     |                                         <span data-ttu-id="aa28e-107">0</span><span class="sxs-lookup"><span data-stu-id="aa28e-107">0</span></span>                                          |
|  <span data-ttu-id="aa28e-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="aa28e-108">Event Source</span></span>   |                                         <span data-ttu-id="aa28e-109">0</span><span class="sxs-lookup"><span data-stu-id="aa28e-109">0</span></span>                                          |
|    <span data-ttu-id="aa28e-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="aa28e-110">Component</span></span>    |                                         <span data-ttu-id="aa28e-111">0</span><span class="sxs-lookup"><span data-stu-id="aa28e-111">0</span></span>                                          |
|  <span data-ttu-id="aa28e-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="aa28e-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="aa28e-113">0</span><span class="sxs-lookup"><span data-stu-id="aa28e-113">0</span></span>                                          |
|  <span data-ttu-id="aa28e-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="aa28e-114">Message Text</span></span>   |                              <span data-ttu-id="aa28e-115">ルート要素が正しくありません</span><span class="sxs-lookup"><span data-stu-id="aa28e-115">Unexpected root element</span></span>                               |
  
## <a name="explanation"></a><span data-ttu-id="aa28e-116">説明</span><span class="sxs-lookup"><span data-stu-id="aa28e-116">Explanation</span></span>  
 <span data-ttu-id="aa28e-117">ヘッダー プロパティにない\<ヘッダー\>...\</headers\>形式。</span><span class="sxs-lookup"><span data-stu-id="aa28e-117">Header property is not in \<headers\>….\</headers\> format.</span></span> <span data-ttu-id="aa28e-118">通常、この状況は InboundHeaders および OutboundCustomHeaders に適用されます。</span><span class="sxs-lookup"><span data-stu-id="aa28e-118">This situation normally applies to InboundHeaders and OutboundCustomHeaders.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="aa28e-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="aa28e-119">User Action</span></span>  
 <span data-ttu-id="aa28e-120">ヘッダー プロパティの形式であることを確認\<ヘッダー\>.\</headers\>します。</span><span class="sxs-lookup"><span data-stu-id="aa28e-120">Ensure that header property is in the format of  \<headers\>…\</headers\>.</span></span>