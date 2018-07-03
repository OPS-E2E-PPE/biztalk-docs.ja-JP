---
title: 1 つまたは複数のエラー セグメント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4ee86667-e72a-4f1b-8d5c-15ca710dbe5d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c364af2691767ac55a52afb52b77f09d39ef6d2d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005072"
---
# <a name="one-or-more-segments-in-error"></a><span data-ttu-id="200d8-102">エラーに 1 つ以上のセグメントが含まれています</span><span class="sxs-lookup"><span data-stu-id="200d8-102">One or more segments in error</span></span>
## <a name="details"></a><span data-ttu-id="200d8-103">詳細</span><span class="sxs-lookup"><span data-stu-id="200d8-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="200d8-104">製品名</span><span class="sxs-lookup"><span data-stu-id="200d8-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="200d8-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="200d8-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="200d8-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="200d8-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="200d8-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="200d8-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="200d8-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="200d8-108"> EDI</span></span> |
|    <span data-ttu-id="200d8-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="200d8-109">Component</span></span>    |                                       <span data-ttu-id="200d8-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="200d8-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="200d8-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="200d8-111">Symbolic Name</span></span>  |                        <span data-ttu-id="200d8-112">X12TsOneOrMoreSegmentsInErrorDescription</span><span class="sxs-lookup"><span data-stu-id="200d8-112">X12TsOneOrMoreSegmentsInErrorDescription</span></span>                        |
|  <span data-ttu-id="200d8-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="200d8-113">Message Text</span></span>   |                             <span data-ttu-id="200d8-114">エラーに 1 つ以上のセグメントが含まれています</span><span class="sxs-lookup"><span data-stu-id="200d8-114">One or more segments in error</span></span>                              |
  
## <a name="explanation"></a><span data-ttu-id="200d8-115">説明</span><span class="sxs-lookup"><span data-stu-id="200d8-115">Explanation</span></span>  
 <span data-ttu-id="200d8-116">このエラー/警告/情報イベントは、インターチェンジの 1 つ以上のセグメントが、それらのセグメントを管理するスキーマに準拠していなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="200d8-116">This Error/Warning/Information event indicates that one or more segments in the interchange did not conform to the schema governing them.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="200d8-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="200d8-117">User Action</span></span>  
 <span data-ttu-id="200d8-118">このエラーを解決するには、どのセグメントがエラーになっているかを特定し、そのセグメントを管理するスキーマを開きます。その後、セグメントがエラーになっている理由をそのスキーマから判断します。</span><span class="sxs-lookup"><span data-stu-id="200d8-118">To resolve this error, determine which segment is in error, open the schema governing that segment, and determine from that schema why the segment is in error.</span></span>