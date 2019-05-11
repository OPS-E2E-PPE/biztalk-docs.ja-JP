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
ms.openlocfilehash: a34b014015d97a6dfa9dc11345e47480f055a237
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399493"
---
# <a name="unexpected-root-element"></a><span data-ttu-id="e1901-102">予期しないルート要素</span><span class="sxs-lookup"><span data-stu-id="e1901-102">Unexpected root element</span></span>
## <a name="details"></a><span data-ttu-id="e1901-103">詳細</span><span class="sxs-lookup"><span data-stu-id="e1901-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="e1901-104">製品名</span><span class="sxs-lookup"><span data-stu-id="e1901-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="e1901-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="e1901-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="e1901-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e1901-106">Event ID</span></span>     |                                         <span data-ttu-id="e1901-107">0</span><span class="sxs-lookup"><span data-stu-id="e1901-107">0</span></span>                                          |
|  <span data-ttu-id="e1901-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="e1901-108">Event Source</span></span>   |                                         <span data-ttu-id="e1901-109">0</span><span class="sxs-lookup"><span data-stu-id="e1901-109">0</span></span>                                          |
|    <span data-ttu-id="e1901-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e1901-110">Component</span></span>    |                                         <span data-ttu-id="e1901-111">0</span><span class="sxs-lookup"><span data-stu-id="e1901-111">0</span></span>                                          |
|  <span data-ttu-id="e1901-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="e1901-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="e1901-113">0</span><span class="sxs-lookup"><span data-stu-id="e1901-113">0</span></span>                                          |
|  <span data-ttu-id="e1901-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="e1901-114">Message Text</span></span>   |                              <span data-ttu-id="e1901-115">予期しないルート要素</span><span class="sxs-lookup"><span data-stu-id="e1901-115">Unexpected root element</span></span>                               |
  
## <a name="explanation"></a><span data-ttu-id="e1901-116">説明</span><span class="sxs-lookup"><span data-stu-id="e1901-116">Explanation</span></span>  
 <span data-ttu-id="e1901-117">ヘッダー プロパティにない\<ヘッダー\>...\</headers\>形式。</span><span class="sxs-lookup"><span data-stu-id="e1901-117">Header property is not in \<headers\>….\</headers\> format.</span></span> <span data-ttu-id="e1901-118">通常、このような状況は InboundHeaders および OutboundCustomHeaders に適用されます。</span><span class="sxs-lookup"><span data-stu-id="e1901-118">This situation normally applies to InboundHeaders and OutboundCustomHeaders.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e1901-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="e1901-119">User Action</span></span>  
 <span data-ttu-id="e1901-120">ヘッダー プロパティの形式であることを確認\<ヘッダー\>.\</headers\>します。</span><span class="sxs-lookup"><span data-stu-id="e1901-120">Ensure that header property is in the format of  \<headers\>…\</headers\>.</span></span>