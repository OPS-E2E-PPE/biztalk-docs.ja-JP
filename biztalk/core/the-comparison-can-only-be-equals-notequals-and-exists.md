---
title: 比較には、Equals、NotEquals、および Exists のみを指定できます |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aad902a2-d0dc-4d91-87a7-a6305e2f40e0
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50499ea6ab9f002d36c213a8bca871884d3b077a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023472"
---
# <a name="the-comparison-can-only-be-equals-notequals-and-exists"></a><span data-ttu-id="70a58-102">この比較には、Equals、NotEquals、および Exists のみを指定できます</span><span class="sxs-lookup"><span data-stu-id="70a58-102">The Comparison can only be Equals, NotEquals and Exists</span></span>
## <a name="details"></a><span data-ttu-id="70a58-103">詳細</span><span class="sxs-lookup"><span data-stu-id="70a58-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="70a58-104">製品名</span><span class="sxs-lookup"><span data-stu-id="70a58-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="70a58-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="70a58-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="70a58-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="70a58-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="70a58-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="70a58-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="70a58-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="70a58-108"> EDI</span></span> |
|    <span data-ttu-id="70a58-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="70a58-109">Component</span></span>    |                                       <span data-ttu-id="70a58-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="70a58-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="70a58-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="70a58-111">Symbolic Name</span></span>  |                                 <span data-ttu-id="70a58-112">Err_InvalidComparision</span><span class="sxs-lookup"><span data-stu-id="70a58-112">Err_InvalidComparision</span></span>                                 |
|  <span data-ttu-id="70a58-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="70a58-113">Message Text</span></span>   |                <span data-ttu-id="70a58-114">この比較には、Equals、NotEquals、および Exists のみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="70a58-114">The Comparison can only be Equals, NotEquals and Exists.</span></span>                |
  
## <a name="explanation"></a><span data-ttu-id="70a58-115">説明</span><span class="sxs-lookup"><span data-stu-id="70a58-115">Explanation</span></span>  
 <span data-ttu-id="70a58-116">このエラー/警告/情報イベントは、メッセージをバッチ処理する際に、BizTalk Server がコンテキスト プロパティを比較できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="70a58-116">This Error/Warning/Information event indicates BizTalk Server was unable to compare a context property while trying to decide to Batch a message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="70a58-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="70a58-117">User Action</span></span>  
 <span data-ttu-id="70a58-118">このエラーを解決するには、その他の操作をサポートしていない XSD 型の Equals、NotEquals、および Exists 以外の演算子をアクティブなバッチで提供されるフィルターが指定されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="70a58-118">To resolve this error, ensure that the filter provided in Active batches doesn’t specify an operator  other than Equals, NotEquals and Exists for XSD types that don’t support other operations.</span></span>