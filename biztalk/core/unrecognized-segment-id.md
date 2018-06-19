---
title: セグメント ID を認識できない |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a00fe451-0a84-4dca-980c-682243fc9804
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a49de4c7f800d740d9219f787a325279eac4c15
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286650"
---
# <a name="unrecognized-segment-id"></a><span data-ttu-id="78b9d-102">セグメント ID が認識されません</span><span class="sxs-lookup"><span data-stu-id="78b9d-102">Unrecognized segment ID</span></span>
## <a name="details"></a><span data-ttu-id="78b9d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="78b9d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="78b9d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="78b9d-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="78b9d-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="78b9d-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="78b9d-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="78b9d-106">Event ID</span></span>|-|  
|<span data-ttu-id="78b9d-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="78b9d-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="78b9d-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="78b9d-108"> EDI</span></span>|  
|<span data-ttu-id="78b9d-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="78b9d-109">Component</span></span>|<span data-ttu-id="78b9d-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="78b9d-110">EDI Engine</span></span>|  
|<span data-ttu-id="78b9d-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="78b9d-111">Symbolic Name</span></span>|<span data-ttu-id="78b9d-112">EfactUnrecognizedSegmentIDDescription</span><span class="sxs-lookup"><span data-stu-id="78b9d-112">EfactUnrecognizedSegmentIDDescription</span></span><br /><br /> <span data-ttu-id="78b9d-113">X12UnrecognizedSegmentIDDescription</span><span class="sxs-lookup"><span data-stu-id="78b9d-113">X12UnrecognizedSegmentIDDescription</span></span>|  
|<span data-ttu-id="78b9d-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="78b9d-114">Message Text</span></span>|<span data-ttu-id="78b9d-115">セグメント ID が認識されません</span><span class="sxs-lookup"><span data-stu-id="78b9d-115">Unrecognized segment ID</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="78b9d-116">説明</span><span class="sxs-lookup"><span data-stu-id="78b9d-116">Explanation</span></span>  
 <span data-ttu-id="78b9d-117">このエラー/警告/情報イベントは、インターチェンジのトランザクション セットのセグメントが、対応するドキュメント スキーマで定義されていなかったため、受信パイプラインが受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="78b9d-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because a segment in a transaction set in the interchange was not defined by the corresponding document schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="78b9d-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="78b9d-118">User Action</span></span>  
 <span data-ttu-id="78b9d-119">このエラーを解決するには、インターチェンジの送信者に対して、認識されないセグメントを削除し、インターチェンジを再送信するように依頼します。</span><span class="sxs-lookup"><span data-stu-id="78b9d-119">To resolve this error, have the sender of the interchange remove the unrecognized segment and resend the interchange.</span></span>