---
title: OutboundCustomHeaders は正しい形式をありません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6097762b-01c9-48b8-8cee-ccd6b11d28d4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d9cb9311015bfa7d88169944a206a8882b11cfe
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008923"
---
# <a name="outboundcustomheaders-does-not-have-correct-format"></a><span data-ttu-id="35af2-102">OutboundCustomHeaders には、正しい形式はありません。</span><span class="sxs-lookup"><span data-stu-id="35af2-102">OutboundCustomHeaders does not have correct format</span></span>
## <a name="details"></a><span data-ttu-id="35af2-103">詳細</span><span class="sxs-lookup"><span data-stu-id="35af2-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="35af2-104">製品名</span><span class="sxs-lookup"><span data-stu-id="35af2-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="35af2-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="35af2-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="35af2-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="35af2-106">Event ID</span></span>     |                                         <span data-ttu-id="35af2-107">0</span><span class="sxs-lookup"><span data-stu-id="35af2-107">0</span></span>                                          |
|  <span data-ttu-id="35af2-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="35af2-108">Event Source</span></span>   |                                         <span data-ttu-id="35af2-109">0</span><span class="sxs-lookup"><span data-stu-id="35af2-109">0</span></span>                                          |
|    <span data-ttu-id="35af2-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="35af2-110">Component</span></span>    |                                         <span data-ttu-id="35af2-111">0</span><span class="sxs-lookup"><span data-stu-id="35af2-111">0</span></span>                                          |
|  <span data-ttu-id="35af2-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="35af2-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="35af2-113">0</span><span class="sxs-lookup"><span data-stu-id="35af2-113">0</span></span>                                          |
|  <span data-ttu-id="35af2-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="35af2-114">Message Text</span></span>   |                <span data-ttu-id="35af2-115">OutboundCustomHeaders は正しい形式ではありません</span><span class="sxs-lookup"><span data-stu-id="35af2-115">OutboundCustomHeaders does not have a correct format</span></span>                |
  
## <a name="explanation"></a><span data-ttu-id="35af2-116">説明</span><span class="sxs-lookup"><span data-stu-id="35af2-116">Explanation</span></span>  
 <span data-ttu-id="35af2-117">WCF の値。InboundHeaders または WCF です。OutboundCustomHeaders は次の形式がありません:\<ヘッダー\>...\</headers\>します。</span><span class="sxs-lookup"><span data-stu-id="35af2-117">The value of WCF.InboundHeaders or WCF.OutboundCustomHeaders  is not in the following format: \<headers\>….\</headers\>.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="35af2-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="35af2-118">User Action</span></span>  
 <span data-ttu-id="35af2-119">プロパティ値をラップ\<ヘッダー\>要素。</span><span class="sxs-lookup"><span data-stu-id="35af2-119">Wrap the property values with \<headers\> element.</span></span>  
  
 <span data-ttu-id="35af2-120">詳細についてで、次のリソースを参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。</span><span class="sxs-lookup"><span data-stu-id="35af2-120">For further information, see the following resource in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="35af2-121">パイプライン コンポーネントでの WCF メッセージにおける SOAP ヘッダーの使用</span><span class="sxs-lookup"><span data-stu-id="35af2-121">Using SOAP Headers in WCF Messages with Pipeline Components</span></span>](../core/using-soap-headers-in-wcf-messages-with-pipeline-components.md)