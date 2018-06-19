---
title: 予期しないセグメント |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7169190c-8893-4076-8634-137fd43992f2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47ff173b88c51ecf28a4979cef3a0c61475c62c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286474"
---
# <a name="unexpected-segment"></a><span data-ttu-id="bf9fa-102">セグメントが正しくありません</span><span class="sxs-lookup"><span data-stu-id="bf9fa-102">Unexpected segment</span></span>
## <a name="details"></a><span data-ttu-id="bf9fa-103">詳細</span><span class="sxs-lookup"><span data-stu-id="bf9fa-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bf9fa-104">製品名</span><span class="sxs-lookup"><span data-stu-id="bf9fa-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="bf9fa-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="bf9fa-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="bf9fa-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="bf9fa-106">Event ID</span></span>|-|  
|<span data-ttu-id="bf9fa-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="bf9fa-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="bf9fa-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="bf9fa-108"> EDI</span></span>|  
|<span data-ttu-id="bf9fa-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="bf9fa-109">Component</span></span>|<span data-ttu-id="bf9fa-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="bf9fa-110">EDI Engine</span></span>|  
|<span data-ttu-id="bf9fa-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="bf9fa-111">Symbolic Name</span></span>|<span data-ttu-id="bf9fa-112">X12UnexpectedSegmentDescription</span><span class="sxs-lookup"><span data-stu-id="bf9fa-112">X12UnexpectedSegmentDescription</span></span>|  
|<span data-ttu-id="bf9fa-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="bf9fa-113">Message Text</span></span>|<span data-ttu-id="bf9fa-114">セグメントが正しくありません</span><span class="sxs-lookup"><span data-stu-id="bf9fa-114">Unexpected segment</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bf9fa-115">説明</span><span class="sxs-lookup"><span data-stu-id="bf9fa-115">Explanation</span></span>  
 <span data-ttu-id="bf9fa-116">このエラー/警告/情報イベントは、インターチェンジに、ドキュメント スキーマまたはサービス スキーマのどちらでも定義されていないセグメントが含まれているため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="bf9fa-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the interchange contains a segment that is not defined by either the document schema or the service schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bf9fa-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="bf9fa-117">User Action</span></span>  
 <span data-ttu-id="bf9fa-118">このエラーを解決するには、インターチェンジの送信者に対して、予期しないセグメントをインターチェンジから削除し、インターチェンジを再送信するように依頼します。</span><span class="sxs-lookup"><span data-stu-id="bf9fa-118">To resolve this error, have the sender of the interchange remove the unexpected segment from the interchange, and then resend the interchange.</span></span>