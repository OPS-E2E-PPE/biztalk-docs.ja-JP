---
title: X12 トランザクション セットは、SE01 に一致しないカウントが |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a90079f5-5939-40b6-9756-d7943240c125
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 762aa7fbbb76cb97e796fa85e89158cd594d8ce0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253875"
---
# <a name="the-x12-transaction-set-had-a-mismatched-count-in-se01"></a><span data-ttu-id="74a31-102">X12 トランザクション セットは、SE01 に一致しないカウントが</span><span class="sxs-lookup"><span data-stu-id="74a31-102">The X12 Transaction set had a mismatched count in SE01</span></span>
## <a name="details"></a><span data-ttu-id="74a31-103">詳細</span><span class="sxs-lookup"><span data-stu-id="74a31-103">Details</span></span>  
  
|                 |                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="74a31-104">製品名</span><span class="sxs-lookup"><span data-stu-id="74a31-104">Product Name</span></span>   |                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                       |
| <span data-ttu-id="74a31-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="74a31-105">Product Version</span></span> |                                  [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                   |
|    <span data-ttu-id="74a31-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="74a31-106">Event ID</span></span>     |                                                               -                                                               |
|  <span data-ttu-id="74a31-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="74a31-107">Event Source</span></span>   |                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="74a31-108">EDI</span><span class="sxs-lookup"><span data-stu-id="74a31-108">EDI</span></span>                     |
|    <span data-ttu-id="74a31-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="74a31-109">Component</span></span>    |                                                          <span data-ttu-id="74a31-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="74a31-110">EDI Engine</span></span>                                                           |
|  <span data-ttu-id="74a31-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="74a31-111">Symbolic Name</span></span>  |                                                     <span data-ttu-id="74a31-112">X12StSeCountMismatch</span><span class="sxs-lookup"><span data-stu-id="74a31-112">X12StSeCountMismatch</span></span>                                                      |
|  <span data-ttu-id="74a31-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="74a31-113">Message Text</span></span>   | <span data-ttu-id="74a31-114">X12 トランザクション セットは、SE01 に一致しないカウントが。</span><span class="sxs-lookup"><span data-stu-id="74a31-114">The X12 Transaction set had a mismatched count in SE01.</span></span> <span data-ttu-id="74a31-115">SE01 が{0}されている一方、{1}します。</span><span class="sxs-lookup"><span data-stu-id="74a31-115">SE01 was {0}, whereas it should have been {1}.</span></span> <span data-ttu-id="74a31-116">修正されています。</span><span class="sxs-lookup"><span data-stu-id="74a31-116">It has been corrected.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="74a31-117">説明</span><span class="sxs-lookup"><span data-stu-id="74a31-117">Explanation</span></span>  
 <span data-ttu-id="74a31-118">この警告は、トランザクション セット トレーラー (SE01 フィールド) 内の数が、インターチェンジのトランザクション セットのセグメントの数と一致しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="74a31-118">This Warning indicates that the number in the transaction set trailer (SE01 field) did not match the number of segments in the transaction set of the interchange.</span></span> <span data-ttu-id="74a31-119">送信パイプラインは、SE01 フィールドのカウントを修正し、警告を表示します。</span><span class="sxs-lookup"><span data-stu-id="74a31-119">The send pipeline corrects the count in the SE01 field and posts the warning.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="74a31-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="74a31-120">User Action</span></span>  
 <span data-ttu-id="74a31-121">必要なアクションはありません。</span><span class="sxs-lookup"><span data-stu-id="74a31-121">No action is necessary.</span></span>