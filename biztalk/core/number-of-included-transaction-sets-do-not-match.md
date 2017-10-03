---
title: "含まれているトランザクション セットの数が一致しません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: db958803-4667-4558-81a6-70c62d6fe8bf
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16a28544757c3e9ae75dd7230673c4526fc2c8f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="number-of-included-transaction-sets-do-not-match"></a><span data-ttu-id="2863c-102">含まれているトランザクション セットの数が一致しません</span><span class="sxs-lookup"><span data-stu-id="2863c-102">Number of included transaction sets do not match</span></span>
## <a name="details"></a><span data-ttu-id="2863c-103">詳細</span><span class="sxs-lookup"><span data-stu-id="2863c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2863c-104">製品名</span><span class="sxs-lookup"><span data-stu-id="2863c-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="2863c-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="2863c-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="2863c-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="2863c-106">Event ID</span></span>|-|  
|<span data-ttu-id="2863c-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="2863c-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="2863c-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="2863c-108"> EDI</span></span>|  
|<span data-ttu-id="2863c-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2863c-109">Component</span></span>|<span data-ttu-id="2863c-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="2863c-110">EDI Engine</span></span>|  
|<span data-ttu-id="2863c-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="2863c-111">Symbolic Name</span></span>|<span data-ttu-id="2863c-112">X12FaNumberOfTsMismatchDescription</span><span class="sxs-lookup"><span data-stu-id="2863c-112">X12FaNumberOfTsMismatchDescription</span></span>|  
|<span data-ttu-id="2863c-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="2863c-113">Message Text</span></span>|<span data-ttu-id="2863c-114">含まれているトランザクション セットの数が一致しません</span><span class="sxs-lookup"><span data-stu-id="2863c-114">Number of included transaction sets do not match</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2863c-115">説明</span><span class="sxs-lookup"><span data-stu-id="2863c-115">Explanation</span></span>  
 <span data-ttu-id="2863c-116">このエラー/警告/情報イベントは、X12 インターチェンジのグループのトランザクション セット数が、グループ トレーラー (GE01 フィールド) の数と等しくないことを示します。</span><span class="sxs-lookup"><span data-stu-id="2863c-116">This Error/Warning/Information event indicates that the number of transaction sets in the group of the X12 interchange does not equal the number in the group trailer (GE01 field).</span></span> <span data-ttu-id="2863c-117">これは、インターチェンジが保存されて、インターチェンジがエラーで中断されている場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="2863c-117">This occurs when the interchange is preserved and the interchange is suspended on an error.</span></span> <span data-ttu-id="2863c-118">(インターチェンジが保存され、トランザクション セットがエラーで中断している場合、またはインターチェンジが分割されている場合、エラー メッセージは通知されません)。</span><span class="sxs-lookup"><span data-stu-id="2863c-118">(The error message is not posted if the interchange is preserved and the transaction sets are suspended on an error, or if the interchange is split.)</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2863c-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="2863c-119">User Action</span></span>  
 <span data-ttu-id="2863c-120">このエラーを解決するには、グループ トレーラーの GE01 フィールドの数が、インターチェンジのグループのトランザクション セット数と同じであることを確認し、インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="2863c-120">To resolve this error, make sure that the number in the GE01 field of the group trailer is the same as the number of transaction sets in the group of the interchange, and then resend the interchange.</span></span>