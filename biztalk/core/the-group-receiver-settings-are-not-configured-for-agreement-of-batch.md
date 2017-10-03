---
title: "バッチのアグリーメントのグループの受信者設定が構成されていません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57b205e9-aaab-43d1-b373-17d206957814
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ea41ad5c8de88e446a86745b57ff282d5b90af5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-group-receiver-settings-are-not-configured-for-agreement-of-batch"></a><span data-ttu-id="82fba-102">バッチのアグリーメントにグループの受信者設定が構成されていません</span><span class="sxs-lookup"><span data-stu-id="82fba-102">The group receiver settings are not configured for agreement of batch</span></span>
## <a name="details"></a><span data-ttu-id="82fba-103">詳細</span><span class="sxs-lookup"><span data-stu-id="82fba-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="82fba-104">製品名</span><span class="sxs-lookup"><span data-stu-id="82fba-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="82fba-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="82fba-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="82fba-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="82fba-106">Event ID</span></span>|-|  
|<span data-ttu-id="82fba-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="82fba-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="82fba-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="82fba-108"> EDI</span></span>|  
|<span data-ttu-id="82fba-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="82fba-109">Component</span></span>|<span data-ttu-id="82fba-110">バッチ処理エンジン</span><span class="sxs-lookup"><span data-stu-id="82fba-110">Batching Engine</span></span>|  
|<span data-ttu-id="82fba-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="82fba-111">Symbolic Name</span></span>|<span data-ttu-id="82fba-112">GroupReceiverNotSelected</span><span class="sxs-lookup"><span data-stu-id="82fba-112">GroupReceiverNotSelected</span></span>|  
|<span data-ttu-id="82fba-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="82fba-113">Message Text</span></span>|<span data-ttu-id="82fba-114">バッチ {0} のアグリーメントは、グループの受信者設定は構成されていません。</span><span class="sxs-lookup"><span data-stu-id="82fba-114">The group receiver settings are not configured for agreement of batch {0}.</span></span> <span data-ttu-id="82fba-115">バッチ処理を続行する前にこの設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82fba-115">This needs to be configured before batching can proceed.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="82fba-116">説明</span><span class="sxs-lookup"><span data-stu-id="82fba-116">Explanation</span></span>  
 <span data-ttu-id="82fba-117">このエラー/警告/情報イベントは、2 つの状態のいずれか 1 つが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="82fba-117">This Error/Warning/Information event indicates that one of two conditions has occurred:</span></span>  
  
-   <span data-ttu-id="82fba-118">エンコードの構文を含む UNB1.1 フィールド (EDIFACT でエンコードされたインターチェンジの場合) が設定されていなかったため、バッチ処理オーケストレーションで受信したバッチ要素を検証できませんでした。</span><span class="sxs-lookup"><span data-stu-id="82fba-118">The batching orchestration could not validate a batch element that it has received because the UNB1.1 field (for an EDIFACT-encoded interchange) that contains the encoding syntax was not set.</span></span>  
  
-   <span data-ttu-id="82fba-119">ヘッダー プロパティ (X12 インターチェンジの ISA、GS、および ST プロパティ、または EDIFACT インターチェンジの UNA、UNB、UNG、および UNH プロパティ) が完全でなかったため、バッチ処理オーケストレーションでバッチ要素のエンベロープ設定を作成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="82fba-119">The batching orchestration could not create the envelope settings for the batch element because the header properties were not complete (ISA, GS, and ST properties for an X12 interchange or UNA, UNB, UNG, and UNH properties for an EDIFACT interchange).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="82fba-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="82fba-120">User Action</span></span>  
 <span data-ttu-id="82fba-121">このエラーを解決するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="82fba-121">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="82fba-122">エンコードの構文が設定されていないためにバッチ処理オーケストレーションで受信したバッチ要素を検証できなかった場合は、[EDI のプロパティ] ダイアログ ボックスの [UNB セグメントの定義] ページにある UNB1.1 フィールドにエンコードの構文を設定します。</span><span class="sxs-lookup"><span data-stu-id="82fba-122">If the batching orchestration could not validate a batch element that it has received because the encoding syntax was not set, set the encoding syntax for the UNB1.1 field in the UNB Segment Definition page of the EDI Properties dialog box.</span></span>  
  
-   <span data-ttu-id="82fba-123">ヘッダー プロパティが完全でなかったためにバッチ処理オーケストレーションでバッチ要素のエンベロープ設定を作成できなかった場合は、X12 インターチェンジの ISA、GS、および ST プロパティが設定されていること、または EDIFACT インターチェンジの UNA、UNB、UNG、および UNH プロパティが設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="82fba-123">If the batching orchestration could not create the envelope settings for the batch element because the header properties were not complete, ensure that the ISA, GS, and ST properties for an X12 interchange are set or that the UNA, UNB, UNG, and UNH properties for an EDIFACT interchange are set.</span></span>