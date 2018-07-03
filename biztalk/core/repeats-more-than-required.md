---
title: 必要な複数の繰り返し |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fec52b5b-e95f-479e-8922-dcf17dcefee7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ac4649ea88756ba63393155ca8910437567fbd1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024040"
---
# <a name="repeats-more-than-required"></a><span data-ttu-id="782b9-102">繰り返しが必要な回数を上回っています</span><span class="sxs-lookup"><span data-stu-id="782b9-102">Repeats more than required</span></span>
## <a name="details"></a><span data-ttu-id="782b9-103">詳細</span><span class="sxs-lookup"><span data-stu-id="782b9-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="782b9-104">製品名</span><span class="sxs-lookup"><span data-stu-id="782b9-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="782b9-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="782b9-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="782b9-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="782b9-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="782b9-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="782b9-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="782b9-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="782b9-108"> EDI</span></span> |
|    <span data-ttu-id="782b9-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="782b9-109">Component</span></span>    |                                       <span data-ttu-id="782b9-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="782b9-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="782b9-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="782b9-111">Symbolic Name</span></span>  |                        <span data-ttu-id="782b9-112">X12FeRepeatsMoreThanRequiredDescription</span><span class="sxs-lookup"><span data-stu-id="782b9-112">X12FeRepeatsMoreThanRequiredDescription</span></span>                         |
|  <span data-ttu-id="782b9-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="782b9-113">Message Text</span></span>   |                               <span data-ttu-id="782b9-114">繰り返しが必要な回数を上回っています</span><span class="sxs-lookup"><span data-stu-id="782b9-114">Repeats more than required</span></span>                               |
  
## <a name="explanation"></a><span data-ttu-id="782b9-115">説明</span><span class="sxs-lookup"><span data-stu-id="782b9-115">Explanation</span></span>  
 <span data-ttu-id="782b9-116">このエラー/警告/情報イベントは、X12 インターチェンジのループ内またはループ外にあるセグメントの繰り返しが、ドキュメント スキーマで必要な回数を上回っていたことを示します。</span><span class="sxs-lookup"><span data-stu-id="782b9-116">This Error/Warning/Information event indicates that segments in an X12 interchange that are either inside or outside of a loop repeated more times than required by the document schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="782b9-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="782b9-117">User Action</span></span>  
 <span data-ttu-id="782b9-118">このエラーを解決するには、インターチェンジのループの内側または外側にあるセグメントがスキーマで指定された回数繰り返されることを確認し、インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="782b9-118">To resolve this error, make sure that the segments that are either inside or outside of a loop in the interchange repeat the numbers of times specified in the schema, and then resend the interchange.</span></span>