---
title: "インターチェンジに含まれている TA1 次のエラーが発生しました |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e2d63fe9-63ef-44b3-8cb9-45a7abf8d0e4
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03bd7486d25e2c94fc809e6dc50c43359c152b70
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-ta1-contained-in-interchange-had-the-following-errors"></a><span data-ttu-id="3c709-102">インターチェンジに含まれている TA1 で次のエラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="3c709-102">The TA1 contained in interchange had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="3c709-103">詳細</span><span class="sxs-lookup"><span data-stu-id="3c709-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3c709-104">製品名</span><span class="sxs-lookup"><span data-stu-id="3c709-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="3c709-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="3c709-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="3c709-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="3c709-106">Event ID</span></span>|-|  
|<span data-ttu-id="3c709-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="3c709-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="3c709-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="3c709-108"> EDI</span></span>|  
|<span data-ttu-id="3c709-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3c709-109">Component</span></span>|<span data-ttu-id="3c709-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="3c709-110">EDI Engine</span></span>|  
|<span data-ttu-id="3c709-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="3c709-111">Symbolic Name</span></span>|<span data-ttu-id="3c709-112">X12TA1Error</span><span class="sxs-lookup"><span data-stu-id="3c709-112">X12TA1Error</span></span>|  
|<span data-ttu-id="3c709-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="3c709-113">Message Text</span></span>|<span data-ttu-id="3c709-114">Id '{1}'、送信者 id '{2}' を持つインターチェンジに含まれている TA1 {0}、受信者 id '{3}' 次のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="3c709-114">The {0} TA1 contained in interchange with id '{1}', sender id '{2}', receiver id '{3}' had the following errors:</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3c709-115">説明</span><span class="sxs-lookup"><span data-stu-id="3c709-115">Explanation</span></span>  
 <span data-ttu-id="3c709-116">このエラー/警告/情報イベントは、示されたエラー状態のため、受信パイプラインで受信 TA1 受信確認を処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="3c709-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming TA1 acknowledgment because of the indicated error condition.</span></span> <span data-ttu-id="3c709-117">これは、受信確認が TA1Schema に準拠していないことを示している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3c709-117">This may indicate that the acknowledgment does not conform to the TA1Schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3c709-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="3c709-118">User Action</span></span>  
 <span data-ttu-id="3c709-119">このエラーを解決するには、受信確認の送信者に対して、受信確認の問題を解決し、受信確認が TA1Schema に準拠していることを確認して、受信確認を再送信するように依頼します。</span><span class="sxs-lookup"><span data-stu-id="3c709-119">To resolve this error, have the sender of the acknowledgment resolve the issue with the acknowledgment, ensuring that the acknowledgment conforms to the TA1Schema, and then resend the acknowledgment.</span></span>