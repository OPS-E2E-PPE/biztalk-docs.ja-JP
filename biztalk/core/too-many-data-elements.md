---
title: データ要素が多すぎる |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5000577d-5748-4e81-a394-86b2a780d70f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cb05cc31331dcc2633b7dc398c8f77a369c3f28
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395422"
---
# <a name="too-many-data-elements"></a><span data-ttu-id="19998-102">データ要素が多すぎます</span><span class="sxs-lookup"><span data-stu-id="19998-102">Too many data elements</span></span>
## <a name="details"></a><span data-ttu-id="19998-103">詳細</span><span class="sxs-lookup"><span data-stu-id="19998-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="19998-104">製品名</span><span class="sxs-lookup"><span data-stu-id="19998-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="19998-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="19998-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="19998-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="19998-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="19998-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="19998-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="19998-108">EDI</span><span class="sxs-lookup"><span data-stu-id="19998-108">EDI</span></span> |
|    <span data-ttu-id="19998-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="19998-109">Component</span></span>    |                                       <span data-ttu-id="19998-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="19998-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="19998-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="19998-111">Symbolic Name</span></span>  |                          <span data-ttu-id="19998-112">X12DeTooManyDataElementsDescription</span><span class="sxs-lookup"><span data-stu-id="19998-112">X12DeTooManyDataElementsDescription</span></span>                           |
|  <span data-ttu-id="19998-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="19998-113">Message Text</span></span>   |                                 <span data-ttu-id="19998-114">データ要素が多すぎます</span><span class="sxs-lookup"><span data-stu-id="19998-114">Too many data elements</span></span>                                 |
  
## <a name="explanation"></a><span data-ttu-id="19998-115">説明</span><span class="sxs-lookup"><span data-stu-id="19998-115">Explanation</span></span>  
 <span data-ttu-id="19998-116">このエラー/警告/情報イベントは、インターチェンジ内のセグメントにドキュメント スキーマまたはサービス スキーマで許容されているよりも多くのデータ要素が含まれていたため、受信パイプラインで受信インターチェンジを処理できなかったか、送信パイプラインで送信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="19998-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange or the send pipeline could not process the outgoing interchange because a segment in the interchange contained more data elements than allowed by the document schema or the service schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="19998-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="19998-117">User Action</span></span>  
 <span data-ttu-id="19998-118">このエラーを解決するには、要求されている数のデータ要素がセグメントに含まれていることを確認するようインターチェンジの送信者に依頼し、必要に応じてセグメントから余分なデータ要素を削除して、セグメントがスキーマに準拠するようにしてもらいます。</span><span class="sxs-lookup"><span data-stu-id="19998-118">To resolve this error, have the sender of the interchange ensure that segments include the required number of data elements, removing excess data elements from the segment if necessary, until the segment conforms to the schema.</span></span>