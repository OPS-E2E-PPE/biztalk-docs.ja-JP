---
title: 最大回数を超えてループが発生します |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0ac9f5d3-04ec-4c40-8a1f-17ef0b143cda
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fead7e98c587b78e9614dbc02171f3c19d01934
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380535"
---
# <a name="loop-occurs-over-maximum-times"></a><span data-ttu-id="6a00e-102">最大回数を超えてループが発生します</span><span class="sxs-lookup"><span data-stu-id="6a00e-102">Loop Occurs Over Maximum Times</span></span>
## <a name="details"></a><span data-ttu-id="6a00e-103">詳細</span><span class="sxs-lookup"><span data-stu-id="6a00e-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="6a00e-104">製品名</span><span class="sxs-lookup"><span data-stu-id="6a00e-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="6a00e-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="6a00e-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="6a00e-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="6a00e-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="6a00e-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="6a00e-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="6a00e-108">EDI</span><span class="sxs-lookup"><span data-stu-id="6a00e-108">EDI</span></span> |
|    <span data-ttu-id="6a00e-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6a00e-109">Component</span></span>    |                                       <span data-ttu-id="6a00e-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="6a00e-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="6a00e-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="6a00e-111">Symbolic Name</span></span>  |                        <span data-ttu-id="6a00e-112">X12LoopOccursOverMaximumTimesDescription</span><span class="sxs-lookup"><span data-stu-id="6a00e-112">X12LoopOccursOverMaximumTimesDescription</span></span>                        |
|  <span data-ttu-id="6a00e-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="6a00e-113">Message Text</span></span>   |                            <span data-ttu-id="6a00e-114">最大回数を超えてループが発生します</span><span class="sxs-lookup"><span data-stu-id="6a00e-114">Loops Occurs Over Maximum Times</span></span>                             |
  
## <a name="explanation"></a><span data-ttu-id="6a00e-115">説明</span><span class="sxs-lookup"><span data-stu-id="6a00e-115">Explanation</span></span>  
 <span data-ttu-id="6a00e-116">このエラー/警告/情報イベントは、インターチェンジには、メッセージ スキーマで必要な時間の最大数を超える繰り返し回数をループが含まれているためで受信インターチェンジでした、受信パイプラインによって処理することを示します。</span><span class="sxs-lookup"><span data-stu-id="6a00e-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the interchange contained a loop that repeated more times than the maximum number of times required by the message schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6a00e-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="6a00e-117">User Action</span></span>  
 <span data-ttu-id="6a00e-118">このエラーを解決するのには、ループが繰り返さインターチェンジでない指定されたメッセージのスキーマのループの maxOccurs プロパティの回数以上とし、インターチェンジを再送信のことを確認します。</span><span class="sxs-lookup"><span data-stu-id="6a00e-118">To resolve this error, make sure that the loop repeats in the interchange no more than the number of times in the maxOccurs property specified for the loop in the message schema, and then have the interchange resent.</span></span>