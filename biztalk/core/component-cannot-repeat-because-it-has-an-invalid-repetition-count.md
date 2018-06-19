---
title: 無効な繰り返し回数があるために、コンポーネントは繰り返すことはできません |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 040d7ea4-60a9-495f-91d7-b5b868957e2d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d535d72b5f265f07e6ae3fb468ed56efdc7975b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231682"
---
# <a name="component-cannot-repeat-because-it-has-an-invalid-repetition-count"></a><span data-ttu-id="7fcd5-102">コンポーネントを繰り返すことはできません。無効な繰り返し回数が指定されています</span><span class="sxs-lookup"><span data-stu-id="7fcd5-102">Component cannot repeat because it has an invalid repetition count</span></span>
## <a name="details"></a><span data-ttu-id="7fcd5-103">詳細</span><span class="sxs-lookup"><span data-stu-id="7fcd5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7fcd5-104">製品名</span><span class="sxs-lookup"><span data-stu-id="7fcd5-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="7fcd5-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="7fcd5-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="7fcd5-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7fcd5-106">Event ID</span></span>|-|  
|<span data-ttu-id="7fcd5-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="7fcd5-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="7fcd5-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="7fcd5-108"> EDI</span></span>|  
|<span data-ttu-id="7fcd5-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7fcd5-109">Component</span></span>|<span data-ttu-id="7fcd5-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="7fcd5-110">EDI Engine</span></span>|  
|<span data-ttu-id="7fcd5-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="7fcd5-111">Symbolic Name</span></span>|<span data-ttu-id="7fcd5-112">SchemaCode118EInvalidRepetition</span><span class="sxs-lookup"><span data-stu-id="7fcd5-112">SchemaCode118EInvalidRepetition</span></span>|  
|<span data-ttu-id="7fcd5-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="7fcd5-113">Message Text</span></span>|<span data-ttu-id="7fcd5-114">コンポーネントを繰り返すことはできません。無効な繰り返し回数 {0} が指定されています。</span><span class="sxs-lookup"><span data-stu-id="7fcd5-114">Component cannot repeat, it has an invalid repetition count of {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7fcd5-115">説明</span><span class="sxs-lookup"><span data-stu-id="7fcd5-115">Explanation</span></span>  
 <span data-ttu-id="7fcd5-116">このエラー/警告/情報イベントは、スキーマで繰り返しが許可されていないにもかかわらず、インターチェンジで要素コンポーネント、要素、セグメント、またはループが繰り返されていたため、受信パイプラインで受信インターチェンジを処理できなかったか、送信パイプラインで送信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="7fcd5-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange or the send pipeline could not process the outgoing interchange because an element component, element, segment, or loop was repeated in the interchange while the schema does not allow the repetition.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7fcd5-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="7fcd5-117">User Action</span></span>  
 <span data-ttu-id="7fcd5-118">このエラーを解決するには、インターチェンジに要素コンポーネント、要素、セグメント、またはループの繰り返しがなく、スキーマの要件どおりであることを確認し、メッセージを再送信します。</span><span class="sxs-lookup"><span data-stu-id="7fcd5-118">To resolve this error, ensure that the element component, element, segment, or loop does not repeat in the interchange, as required by the schema, and have the message resent.</span></span>