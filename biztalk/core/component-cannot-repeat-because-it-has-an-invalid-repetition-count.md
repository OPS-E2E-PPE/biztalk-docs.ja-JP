---
title: 無効な繰り返し回数があるため、コンポーネントを繰り返すことはできません |Microsoft Docs
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
ms.openlocfilehash: b9bb4cd603084a4bd105423a556d6480051fc0a5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391661"
---
# <a name="component-cannot-repeat-because-it-has-an-invalid-repetition-count"></a><span data-ttu-id="191f0-102">無効な繰り返し回数があるため、コンポーネントを繰り返すことはできません。</span><span class="sxs-lookup"><span data-stu-id="191f0-102">Component cannot repeat because it has an invalid repetition count</span></span>
## <a name="details"></a><span data-ttu-id="191f0-103">詳細</span><span class="sxs-lookup"><span data-stu-id="191f0-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="191f0-104">製品名</span><span class="sxs-lookup"><span data-stu-id="191f0-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="191f0-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="191f0-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="191f0-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="191f0-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="191f0-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="191f0-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="191f0-108">EDI</span><span class="sxs-lookup"><span data-stu-id="191f0-108">EDI</span></span> |
|    <span data-ttu-id="191f0-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="191f0-109">Component</span></span>    |                                       <span data-ttu-id="191f0-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="191f0-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="191f0-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="191f0-111">Symbolic Name</span></span>  |                            <span data-ttu-id="191f0-112">SchemaCode118EInvalidRepetition</span><span class="sxs-lookup"><span data-stu-id="191f0-112">SchemaCode118EInvalidRepetition</span></span>                             |
|  <span data-ttu-id="191f0-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="191f0-113">Message Text</span></span>   |           <span data-ttu-id="191f0-114">無効な繰り返し数があるコンポーネントを繰り返すことはできません。 {0}</span><span class="sxs-lookup"><span data-stu-id="191f0-114">Component cannot repeat, it has an invalid repetition count of {0}</span></span>           |
  
## <a name="explanation"></a><span data-ttu-id="191f0-115">説明</span><span class="sxs-lookup"><span data-stu-id="191f0-115">Explanation</span></span>  
 <span data-ttu-id="191f0-116">このエラー/警告/情報イベントは、スキーマで繰り返しが許可されていないにもかかわらず、インターチェンジで要素コンポーネント、要素、セグメント、またはループが繰り返されていたため、受信パイプラインで受信インターチェンジを処理できなかったか、送信パイプラインで送信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="191f0-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange or the send pipeline could not process the outgoing interchange because an element component, element, segment, or loop was repeated in the interchange while the schema does not allow the repetition.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="191f0-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="191f0-117">User Action</span></span>  
 <span data-ttu-id="191f0-118">このエラーを解決するには、インターチェンジに要素コンポーネント、要素、セグメント、またはループの繰り返しがなく、スキーマの要件どおりであることを確認し、メッセージを再送信します。</span><span class="sxs-lookup"><span data-stu-id="191f0-118">To resolve this error, ensure that the element component, element, segment, or loop does not repeat in the interchange, as required by the schema, and have the message resent.</span></span>