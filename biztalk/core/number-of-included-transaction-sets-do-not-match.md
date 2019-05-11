---
title: 含まれているトランザクション セットの数が一致しない |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db958803-4667-4558-81a6-70c62d6fe8bf
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb45df387dd7c06e995c2e3a2790e6cc2af68260
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65263217"
---
# <a name="number-of-included-transaction-sets-do-not-match"></a><span data-ttu-id="14e69-102">含まれているトランザクション セットの数が一致しません</span><span class="sxs-lookup"><span data-stu-id="14e69-102">Number of included transaction sets do not match</span></span>
## <a name="details"></a><span data-ttu-id="14e69-103">詳細</span><span class="sxs-lookup"><span data-stu-id="14e69-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="14e69-104">製品名</span><span class="sxs-lookup"><span data-stu-id="14e69-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="14e69-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="14e69-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="14e69-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="14e69-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="14e69-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="14e69-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="14e69-108">EDI</span><span class="sxs-lookup"><span data-stu-id="14e69-108">EDI</span></span> |
|    <span data-ttu-id="14e69-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="14e69-109">Component</span></span>    |                                       <span data-ttu-id="14e69-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="14e69-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="14e69-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="14e69-111">Symbolic Name</span></span>  |                           <span data-ttu-id="14e69-112">X12FaNumberOfTsMismatchDescription</span><span class="sxs-lookup"><span data-stu-id="14e69-112">X12FaNumberOfTsMismatchDescription</span></span>                           |
|  <span data-ttu-id="14e69-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="14e69-113">Message Text</span></span>   |                    <span data-ttu-id="14e69-114">含まれているトランザクション セットの数が一致しません</span><span class="sxs-lookup"><span data-stu-id="14e69-114">Number of included transaction sets do not match</span></span>                    |
  
## <a name="explanation"></a><span data-ttu-id="14e69-115">説明</span><span class="sxs-lookup"><span data-stu-id="14e69-115">Explanation</span></span>  
 <span data-ttu-id="14e69-116">このエラー/警告/情報イベントは、X12 インターチェンジのグループのトランザクション セット数が、グループ トレーラー (GE01 フィールド) の数と等しくないことを示します。</span><span class="sxs-lookup"><span data-stu-id="14e69-116">This Error/Warning/Information event indicates that the number of transaction sets in the group of the X12 interchange does not equal the number in the group trailer (GE01 field).</span></span> <span data-ttu-id="14e69-117">これは、インターチェンジが保存されて、インターチェンジがエラーで中断されている場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="14e69-117">This occurs when the interchange is preserved and the interchange is suspended on an error.</span></span> <span data-ttu-id="14e69-118">(インターチェンジが保存され、トランザクション セットがエラーで中断している場合、またはインターチェンジが分割されている場合、エラー メッセージは通知されません)。</span><span class="sxs-lookup"><span data-stu-id="14e69-118">(The error message is not posted if the interchange is preserved and the transaction sets are suspended on an error, or if the interchange is split.)</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="14e69-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="14e69-119">User Action</span></span>  
 <span data-ttu-id="14e69-120">このエラーを解決するには、グループ トレーラーの GE01 フィールドの数が、インターチェンジのグループのトランザクション セット数と同じであることを確認し、インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="14e69-120">To resolve this error, make sure that the number in the GE01 field of the group trailer is the same as the number of transaction sets in the group of the interchange, and then resend the interchange.</span></span>