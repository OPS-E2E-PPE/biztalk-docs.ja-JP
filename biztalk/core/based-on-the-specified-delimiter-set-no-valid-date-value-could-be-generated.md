---
title: 指定された区切り記号セットに基づいて、有効な日付値でしたを生成できません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cdd157c0-9a0d-421b-8350-aa1263126ca0
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef866157078e037d7424452a0c7c6a1bff1ae445
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008563"
---
# <a name="based-on-the-specified-delimiter-set-no-valid-date-value-could-be-generated"></a><span data-ttu-id="23fd2-102">指定された区切り記号セットに基づいて有効な日付値を生成できませんでした</span><span class="sxs-lookup"><span data-stu-id="23fd2-102">Based on the specified delimiter set, no valid Date value could be generated</span></span>
## <a name="details"></a><span data-ttu-id="23fd2-103">詳細</span><span class="sxs-lookup"><span data-stu-id="23fd2-103">Details</span></span>  
  
|                 |                                                                                                                 |
|-----------------|-----------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="23fd2-104">製品名</span><span class="sxs-lookup"><span data-stu-id="23fd2-104">Product Name</span></span>   |               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                |
| <span data-ttu-id="23fd2-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="23fd2-105">Product Version</span></span> |                           [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                            |
|    <span data-ttu-id="23fd2-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="23fd2-106">Event ID</span></span>     |                                                        -                                                        |
|  <span data-ttu-id="23fd2-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="23fd2-107">Event Source</span></span>   |             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="23fd2-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="23fd2-108"> EDI</span></span>              |
|    <span data-ttu-id="23fd2-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="23fd2-109">Component</span></span>    |                                                   <span data-ttu-id="23fd2-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="23fd2-110">EDI Engine</span></span>                                                    |
|  <span data-ttu-id="23fd2-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="23fd2-111">Symbolic Name</span></span>  |                                                        -                                                        |
|  <span data-ttu-id="23fd2-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="23fd2-112">Message Text</span></span>   | <span data-ttu-id="23fd2-113">指定された区切り記号セットに基づいて有効な日付値を生成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="23fd2-113">Based on the specified delimiter set, no valid Date value could be generated.</span></span> <span data-ttu-id="23fd2-114">別の区切り記号セットを使用してください。</span><span class="sxs-lookup"><span data-stu-id="23fd2-114">Please use another delimiter set.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="23fd2-115">説明</span><span class="sxs-lookup"><span data-stu-id="23fd2-115">Explanation</span></span>  
 <span data-ttu-id="23fd2-116">このエラー/警告/情報イベントは、送信インターチェンジの日付フィールドに使用されている文字が、区切り記号の文字と同じだったため、EDI 送信パイプラインで有効な日付値を生成できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="23fd2-116">This Error/Warning/Information event indicates that the EDI send pipeline could not generate a valid date value because a character used in a Date field of the outgoing interchange was the same as a separator character.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="23fd2-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="23fd2-117">User Action</span></span>  
 <span data-ttu-id="23fd2-118">このエラーを解決するには、EDI 送信パイプラインでメッセージを作成するために使用される区切り記号の値を変更し、送信インターチェンジの日付フィールドで使用されている文字が区切り記号と同じにならないようにします。</span><span class="sxs-lookup"><span data-stu-id="23fd2-118">To resolve this error, change the separator values used by the EDI send pipeline to create a message so that no separator character will be the same as a character used in a Date field of the outgoing interchange.</span></span> <span data-ttu-id="23fd2-119">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="23fd2-119">Do one of the following:</span></span>  
  
-   <span data-ttu-id="23fd2-120">解決済みのパーティに対して送信される X12 インターチェンジの場合、インターチェンジの受信者となるパーティの [ISA セグメントの定義] ページで区切り記号の設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="23fd2-120">For an X12 interchange being sent to a resolved party, change the separator settings in the ISA Segment Definition page for the party as interchange receiver.</span></span>  
  
-   <span data-ttu-id="23fd2-121">未解決のパーティに対して送信される X12 インターチェンジの場合、[ISA セグメントの定義] グローバル プロパティ ページで区切り記号の設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="23fd2-121">For an X12 interchange being sent to a party that has not been resolved, change the separator settings in the ISA Segment Definition global property page.</span></span>  
  
-   <span data-ttu-id="23fd2-122">解決済みのパーティに対して送信される EDIFACT インターチェンジの場合、インターチェンジの受信者となるパーティの [UNA セグメントの定義] ページで区切り記号の設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="23fd2-122">For an EDIFACT interchange being sent to a resolved party, change the separator settings in the UNA Segment Definition page for the party as interchange receiver.</span></span>  
  
-   <span data-ttu-id="23fd2-123">未解決のパーティに対して送信される EDIFACT インターチェンジの場合、[UNA セグメントの定義] グローバル プロパティ ページで区切り記号の設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="23fd2-123">For an EDIFACT interchange being sent to a party that has not been resolved, change the separator settings in the UNA Segment Definition global property page.</span></span>