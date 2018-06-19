---
title: メッセージをルーティングできません、バッチ処理オーケストレーションにエンコードの種類を特定できませんでした |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0d2ee38d-22c0-4fcf-bb68-b2ef00088c4c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe5054f53f779274c9b25f2751fdcb9d85545560
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241946"
---
# <a name="the-message-cannot-be-routed-to-the-batching-orchestration-as-the-encoding-type-could-not-be-determined"></a><span data-ttu-id="3dbdd-102">エンコードの種類を決定できなかったため、バッチ処理オーケストレーションへメッセージをルーティングできません</span><span class="sxs-lookup"><span data-stu-id="3dbdd-102">The message cannot be routed to the batching orchestration as the Encoding type could not be determined</span></span>
## <a name="details"></a><span data-ttu-id="3dbdd-103">詳細</span><span class="sxs-lookup"><span data-stu-id="3dbdd-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3dbdd-104">製品名</span><span class="sxs-lookup"><span data-stu-id="3dbdd-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="3dbdd-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="3dbdd-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="3dbdd-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="3dbdd-106">Event ID</span></span>|-|  
|<span data-ttu-id="3dbdd-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="3dbdd-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="3dbdd-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="3dbdd-108"> EDI</span></span>|  
|<span data-ttu-id="3dbdd-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3dbdd-109">Component</span></span>|<span data-ttu-id="3dbdd-110">バッチ処理エンジン</span><span class="sxs-lookup"><span data-stu-id="3dbdd-110">Batching Engine</span></span>|  
|<span data-ttu-id="3dbdd-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="3dbdd-111">Symbolic Name</span></span>|<span data-ttu-id="3dbdd-112">UnknownEncodingType</span><span class="sxs-lookup"><span data-stu-id="3dbdd-112">UnknownEncodingType</span></span>|  
|<span data-ttu-id="3dbdd-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="3dbdd-113">Message Text</span></span>|<span data-ttu-id="3dbdd-114">エンコードの種類を特定できなかったため、バッチ処理オーケストレーションへメッセージをルーティングできません。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-114">The message cannot be routed to the batching orchestration as the Encoding type could not be determined.</span></span> <span data-ttu-id="3dbdd-115">バッチ処理を行うには、エンコードの種類が X12 または EDIFACT である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-115">The encoding type needs to be either X12 or EDIFACT for the message to be batched.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3dbdd-116">説明</span><span class="sxs-lookup"><span data-stu-id="3dbdd-116">Explanation</span></span>  
 <span data-ttu-id="3dbdd-117">このエラー/警告/情報イベントは、トランザクション セットがバッチ処理のフィルター条件を満たしていたにもかかわらず、非 EDI バッチ要素がバッチ処理オーケストレーション インスタンスにルーティングされなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-117">This Error/Warning/Information event indicates that a non-EDI batch element was not routed to the batching orchestration instance, even though the transaction set meets the filter criteria for batching.</span></span> <span data-ttu-id="3dbdd-118">X12 を示す 0 または EDIFACT を示す 1 の値を使用した EDI.EncodingType コンテンツ プロパティの昇格が実行されなかったため、トランザクション セットをバッチ処理オーケストレーション インスタンスにルーティングすることができませんでした。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-118">The transaction set could not be routed to the batching orchestration instance because the EDI.EncodingType context property was not promoted with a value of 0 for X12 or 1 for EDIFACT.</span></span> <span data-ttu-id="3dbdd-119">このエラーは、バッチ要素が BatchMarker パイプライン コンポーネントによってルーティング オーケストレーションにルーティングされたものの、非 EDI バッチ要素がマップによって EDI メッセージに変換されなかった場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-119">This error occurred when the batch element was routed by the BatchMarker pipeline component to the routing orchestration, but the non-EDI batch element was not converted by a map into an EDI message.</span></span> <span data-ttu-id="3dbdd-120">その結果、ルーティング オーケストレーションは EDI ヘッダーからエンコードの種類を特定できません。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-120">As a result, the routing orchestration could not determine the encoding type from the EDI headers.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3dbdd-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="3dbdd-121">User Action</span></span>  
 <span data-ttu-id="3dbdd-122">このエラーを解決するには、非 EDI メッセージがルーティング オーケストレーションにルーティングされる前に、マップによって EDI メッセージに変換されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-122">To resolve this error, make sure that the non-EDI message is converted by a map into an EDI message before it is routed to the routing orchestration.</span></span> <span data-ttu-id="3dbdd-123">また、非 EDI バッチ要素を処理するためのカスタム パイプライン コンポーネント (BatchMarker コンポーネントと共に) またはカスタム オーケストレーションを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-123">You must also include a custom pipeline component (with the BatchMarker component) or custom orchestration to process the non-EDI batch element.</span></span> <span data-ttu-id="3dbdd-124">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの「バッチ EDI インターチェンジのアセンブル」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3dbdd-124">For more information, see "Assembling a Batched EDI Interchange" in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>