---
title: "OutboundCustomHeaders は正しい形式はいません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6097762b-01c9-48b8-8cee-ccd6b11d28d4
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df751526661ddef455be45c4258c331c940fdd47
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="outboundcustomheaders-does-not-have-correct-format"></a><span data-ttu-id="f4752-102">OutboundCustomHeaders は正しい形式はいません</span><span class="sxs-lookup"><span data-stu-id="f4752-102">OutboundCustomHeaders does not have correct format</span></span>
## <a name="details"></a><span data-ttu-id="f4752-103">詳細</span><span class="sxs-lookup"><span data-stu-id="f4752-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f4752-104">製品名</span><span class="sxs-lookup"><span data-stu-id="f4752-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="f4752-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f4752-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="f4752-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f4752-106">Event ID</span></span>|<span data-ttu-id="f4752-107">0</span><span class="sxs-lookup"><span data-stu-id="f4752-107">0</span></span>|  
|<span data-ttu-id="f4752-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f4752-108">Event Source</span></span>|<span data-ttu-id="f4752-109">0</span><span class="sxs-lookup"><span data-stu-id="f4752-109">0</span></span>|  
|<span data-ttu-id="f4752-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f4752-110">Component</span></span>|<span data-ttu-id="f4752-111">0</span><span class="sxs-lookup"><span data-stu-id="f4752-111">0</span></span>|  
|<span data-ttu-id="f4752-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f4752-112">Symbolic Name</span></span>|<span data-ttu-id="f4752-113">0</span><span class="sxs-lookup"><span data-stu-id="f4752-113">0</span></span>|  
|<span data-ttu-id="f4752-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f4752-114">Message Text</span></span>|<span data-ttu-id="f4752-115">OutboundCustomHeaders は正しい形式ではありません</span><span class="sxs-lookup"><span data-stu-id="f4752-115">OutboundCustomHeaders does not have a correct format</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f4752-116">説明</span><span class="sxs-lookup"><span data-stu-id="f4752-116">Explanation</span></span>  
 <span data-ttu-id="f4752-117">WCF の値。InboundHeaders または WCF です。OutboundCustomHeaders が次の形式ではありません:\<ヘッダー\>...\</headers\>です。</span><span class="sxs-lookup"><span data-stu-id="f4752-117">The value of WCF.InboundHeaders or WCF.OutboundCustomHeaders  is not in the following format: \<headers\>….\</headers\>.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f4752-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f4752-118">User Action</span></span>  
 <span data-ttu-id="f4752-119">プロパティ値のラップ\<ヘッダー\>要素。</span><span class="sxs-lookup"><span data-stu-id="f4752-119">Wrap the property values with \<headers\> element.</span></span>  
  
 <span data-ttu-id="f4752-120">詳細については、次のリソースを参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。</span><span class="sxs-lookup"><span data-stu-id="f4752-120">For further information, see the following resource in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="f4752-121">パイプライン コンポーネントでの WCF メッセージにおける SOAP ヘッダーの使用</span><span class="sxs-lookup"><span data-stu-id="f4752-121">Using SOAP Headers in WCF Messages with Pipeline Components</span></span>](../core/using-soap-headers-in-wcf-messages-with-pipeline-components.md)