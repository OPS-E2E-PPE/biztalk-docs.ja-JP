---
title: 指定された区切り記号セットに基づいて、有効な数字見つかりません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 08887f7d-8256-4de3-8db9-b890451521ff
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63ad84e52fd66cb8430547ecd4e6a9e6dd054963
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358586"
---
# <a name="based-on-the-specified-delimiter-set-no-valid-digit-could-be-found"></a><span data-ttu-id="8e474-102">指定された区切り記号セットに基づいて、有効な数字見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="8e474-102">Based on the specified delimiter set, no valid Digit could be found</span></span>
## <a name="details"></a><span data-ttu-id="8e474-103">詳細</span><span class="sxs-lookup"><span data-stu-id="8e474-103">Details</span></span>  
  
|                 |                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="8e474-104">製品名</span><span class="sxs-lookup"><span data-stu-id="8e474-104">Product Name</span></span>   |           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]           |
| <span data-ttu-id="8e474-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="8e474-105">Product Version</span></span> |                       [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                       |
|    <span data-ttu-id="8e474-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="8e474-106">Event ID</span></span>     |                                                   -                                                    |
|  <span data-ttu-id="8e474-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="8e474-107">Event Source</span></span>   |         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="8e474-108">EDI</span><span class="sxs-lookup"><span data-stu-id="8e474-108">EDI</span></span>         |
|    <span data-ttu-id="8e474-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8e474-109">Component</span></span>    |                                               <span data-ttu-id="8e474-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="8e474-110">EDI Engine</span></span>                                               |
|  <span data-ttu-id="8e474-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="8e474-111">Symbolic Name</span></span>  |                                                   -                                                    |
|  <span data-ttu-id="8e474-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="8e474-112">Message Text</span></span>   | <span data-ttu-id="8e474-113">指定された区切り記号セットに基づいて有効な数字を見つけることができませんでした。</span><span class="sxs-lookup"><span data-stu-id="8e474-113">Based on the specified delimiter set, no valid Digit could be found.</span></span> <span data-ttu-id="8e474-114">別の区切り記号セットを使用してください。</span><span class="sxs-lookup"><span data-stu-id="8e474-114">Please use another delimiter set.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="8e474-115">説明</span><span class="sxs-lookup"><span data-stu-id="8e474-115">Explanation</span></span>  
 <span data-ttu-id="8e474-116">このエラー/警告/情報イベントは、送信インターチェンジのフィールドで使用されている数字が区切り記号と同じであるため、EDI 送信パイプラインが送信インターチェンジ生成時に有効な数字を見つけることができなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="8e474-116">This Error/Warning/Information event indicates that the EDI send pipeline could not find a valid digit when generating an outgoing interchange because a digit used in a field of the outgoing interchange was the same as a separator character.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8e474-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="8e474-117">User Action</span></span>  
 <span data-ttu-id="8e474-118">このエラーを解決するには、EDI 送信パイプラインでメッセージを作成するために使用される区切り記号の値を変更し、送信インターチェンジのフィールドで使用されている数字が区切り記号と同じにならないようにします。</span><span class="sxs-lookup"><span data-stu-id="8e474-118">To resolve this error, change the separator values used by the EDI send pipeline to create a message so that no separator character will be the same as a digit used in a field of the outgoing interchange.</span></span> <span data-ttu-id="8e474-119">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8e474-119">Do one of the following:</span></span>  
  
-   <span data-ttu-id="8e474-120">解決済みのパーティに対して送信される X12 インターチェンジの場合、インターチェンジの受信者となるパーティの [ISA セグメントの定義] ページで区切り記号の設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="8e474-120">For an X12 interchange being sent to a resolved party, change the separator settings in the ISA Segment Definition page for the party as interchange receiver.</span></span>  
  
-   <span data-ttu-id="8e474-121">未解決のパーティに対して送信される X12 インターチェンジの場合、[ISA セグメントの定義] グローバル プロパティ ページで区切り記号の設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="8e474-121">For an X12 interchange being sent to a party that has not been resolved, change the separator settings in the ISA Segment Definition global property page.</span></span>  
  
-   <span data-ttu-id="8e474-122">解決済みのパーティに対して送信される EDIFACT インターチェンジの場合、インターチェンジの受信者となるパーティの [UNA セグメントの定義] ページで区切り記号の設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="8e474-122">For an EDIFACT interchange being sent to a resolved party, change the separator settings in the UNA Segment Definition page for the party as interchange receiver.</span></span>  
  
-   <span data-ttu-id="8e474-123">未解決のパーティに対して送信される EDIFACT インターチェンジの場合、[UNA セグメントの定義] グローバル プロパティ ページで区切り記号の設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="8e474-123">For an EDIFACT interchange being sent to a party that has not been resolved, change the separator settings in the UNA Segment Definition global property page.</span></span>