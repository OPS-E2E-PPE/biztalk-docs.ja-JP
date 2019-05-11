---
title: セグメントのデータ要素エラーが |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 469622e2-6500-4f55-ab53-f8d89ee0a978
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8b96eb9eaff6e37c184cea23af96caf5e6ecee8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279922"
---
# <a name="segment-has-data-element-errors"></a><span data-ttu-id="df718-102">セグメントのデータ要素エラーをが</span><span class="sxs-lookup"><span data-stu-id="df718-102">Segment has data element errors</span></span>
## <a name="details"></a><span data-ttu-id="df718-103">詳細</span><span class="sxs-lookup"><span data-stu-id="df718-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="df718-104">製品名</span><span class="sxs-lookup"><span data-stu-id="df718-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="df718-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="df718-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="df718-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="df718-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="df718-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="df718-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="df718-108">EDI</span><span class="sxs-lookup"><span data-stu-id="df718-108">EDI</span></span> |
|    <span data-ttu-id="df718-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="df718-109">Component</span></span>    |                                       <span data-ttu-id="df718-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="df718-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="df718-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="df718-111">Symbolic Name</span></span>  |                       <span data-ttu-id="df718-112">X12SegmentHasDataElementErrorsDescription</span><span class="sxs-lookup"><span data-stu-id="df718-112">X12SegmentHasDataElementErrorsDescription</span></span>                        |
|  <span data-ttu-id="df718-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="df718-113">Message Text</span></span>   |                            <span data-ttu-id="df718-114">セグメントでデータ要素エラーが発生しています</span><span class="sxs-lookup"><span data-stu-id="df718-114">Segment Has Data Element Errors</span></span>                             |
  
## <a name="explanation"></a><span data-ttu-id="df718-115">説明</span><span class="sxs-lookup"><span data-stu-id="df718-115">Explanation</span></span>  
 <span data-ttu-id="df718-116">このエラー/警告/情報イベントは、ドキュメント スキーマに準拠していないデータ要素がインターチェンジ内のセグメントに含まれていたため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="df718-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the interchange contained segments that included data elements that did not conform to the document schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="df718-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="df718-117">User Action</span></span>  
 <span data-ttu-id="df718-118">このエラーを解決するには、インターチェンジ内のデータ要素がドキュメント スキーマに準拠していることを確認し、インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="df718-118">To resolve this error, make sure that the data elements in the interchange conform to the document schema, and then resend the interchange.</span></span>