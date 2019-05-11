---
title: UNA セグメントが無効です。 6 個のフィールドが指定されていなかった |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c939d8d3-e6fb-4505-836d-31559fc5f1a3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7aaa5714a3063ba5039c042fb24c5c6a9a28f7d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258661"
---
# <a name="una-segment-is-invalid-it-did-not-contain-6-fields"></a><span data-ttu-id="c53e4-103">UNA セグメントが無効です。</span><span class="sxs-lookup"><span data-stu-id="c53e4-103">UNA segment is invalid.</span></span> <span data-ttu-id="c53e4-104">6 個のフィールドが含まれていませんでした</span><span class="sxs-lookup"><span data-stu-id="c53e4-104">It did not contain 6 fields</span></span>
## <a name="details"></a><span data-ttu-id="c53e4-105">詳細</span><span class="sxs-lookup"><span data-stu-id="c53e4-105">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="c53e4-106">製品名</span><span class="sxs-lookup"><span data-stu-id="c53e4-106">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="c53e4-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c53e4-107">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="c53e4-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c53e4-108">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="c53e4-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c53e4-109">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="c53e4-110">EDI</span><span class="sxs-lookup"><span data-stu-id="c53e4-110">EDI</span></span> |
|    <span data-ttu-id="c53e4-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c53e4-111">Component</span></span>    |                                       <span data-ttu-id="c53e4-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="c53e4-112">EDI Engine</span></span>                                       |
|  <span data-ttu-id="c53e4-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c53e4-113">Symbolic Name</span></span>  |                             <span data-ttu-id="c53e4-114">UnaDidNotContainSixDelimiters</span><span class="sxs-lookup"><span data-stu-id="c53e4-114">UnaDidNotContainSixDelimiters</span></span>                              |
|  <span data-ttu-id="c53e4-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c53e4-115">Message Text</span></span>   |                  <span data-ttu-id="c53e4-116">UNA セグメントが無効です。</span><span class="sxs-lookup"><span data-stu-id="c53e4-116">UNA segment is invalid.</span></span> <span data-ttu-id="c53e4-117">6 個のフィールドが含まれていませんでした</span><span class="sxs-lookup"><span data-stu-id="c53e4-117">It did not contain 6 fields</span></span>                   |
  
## <a name="explanation"></a><span data-ttu-id="c53e4-118">説明</span><span class="sxs-lookup"><span data-stu-id="c53e4-118">Explanation</span></span>  
 <span data-ttu-id="c53e4-119">このエラー/警告/情報イベントは、UNA セグメントに含まれているデータ要素が 6 個未満だったため、受信パイプラインで受信 EDIFACT インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="c53e4-119">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming EDIFACT interchange because the UNA segment contained fewer than six data elements.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c53e4-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c53e4-120">User Action</span></span>  
 <span data-ttu-id="c53e4-121">このエラーを解決するには、インターチェンジの送信者に対して、UNA セグメントに 6 個のデータ要素を含めるよう依頼し、インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="c53e4-121">To resolve this error, have the sender of the interchange make sure that the UNA segment contains six data elements, and then resend the interchange.</span></span>