---
title: セグメントは、少なくとも 2 つの文字の名前が必要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f80bbc4a-151a-4094-8640-1944e8812730
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 814da0db8dce26e9078126ede767f623b59b6401
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65251012"
---
# <a name="segment-should-have-a-name-with-at-least-two-characters"></a><span data-ttu-id="57bb1-102">セグメントは、少なくとも 2 つの文字の名前が必要</span><span class="sxs-lookup"><span data-stu-id="57bb1-102">Segment should have a name with at least two characters</span></span>
## <a name="details"></a><span data-ttu-id="57bb1-103">詳細</span><span class="sxs-lookup"><span data-stu-id="57bb1-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="57bb1-104">製品名</span><span class="sxs-lookup"><span data-stu-id="57bb1-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="57bb1-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="57bb1-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="57bb1-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="57bb1-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="57bb1-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="57bb1-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="57bb1-108">EDI</span><span class="sxs-lookup"><span data-stu-id="57bb1-108">EDI</span></span> |
|    <span data-ttu-id="57bb1-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="57bb1-109">Component</span></span>    |                                       <span data-ttu-id="57bb1-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="57bb1-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="57bb1-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="57bb1-111">Symbolic Name</span></span>  |                             <span data-ttu-id="57bb1-112">SchemaCode103EInvalidTagLength</span><span class="sxs-lookup"><span data-stu-id="57bb1-112">SchemaCode103EInvalidTagLength</span></span>                             |
|  <span data-ttu-id="57bb1-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="57bb1-113">Message Text</span></span>   |                 <span data-ttu-id="57bb1-114">セグメントは少なくとも 2 つの文字の名前である必要があります。</span><span class="sxs-lookup"><span data-stu-id="57bb1-114">Segment should have a name with at least 2 characters</span></span>                  |
  
## <a name="explanation"></a><span data-ttu-id="57bb1-115">説明</span><span class="sxs-lookup"><span data-stu-id="57bb1-115">Explanation</span></span>  
 <span data-ttu-id="57bb1-116">このエラー/警告/情報イベントは、インターチェンジ内のセグメントの名前に、少なくとも 2 つの文字があるないためにで受信インターチェンジでした、受信パイプラインによって処理することを示します。</span><span class="sxs-lookup"><span data-stu-id="57bb1-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the name of a segment in the interchange does not have at least two characters.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="57bb1-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="57bb1-117">User Action</span></span>  
 <span data-ttu-id="57bb1-118">このエラーを解決するには、インターチェンジ内の各セグメントの名前に、少なくとも 2 つの文字があることを確認してもらい、インターチェンジのインターチェンジの送信者を依頼します。</span><span class="sxs-lookup"><span data-stu-id="57bb1-118">To resolve this error, have the sender of the interchange ensure that the name of each segment in the interchange has at least two characters, and then resend the interchange.</span></span>