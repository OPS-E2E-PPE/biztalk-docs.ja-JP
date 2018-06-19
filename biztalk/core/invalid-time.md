---
title: 無効な時間 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6942eb77-3ef1-460c-ac4f-8f1339c25d1b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aae508a945cc6934e83408b2a9b78c324947e0e8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22261978"
---
# <a name="invalid-time"></a><span data-ttu-id="1a285-102">時刻が無効です</span><span class="sxs-lookup"><span data-stu-id="1a285-102">Invalid Time</span></span>
## <a name="details"></a><span data-ttu-id="1a285-103">詳細</span><span class="sxs-lookup"><span data-stu-id="1a285-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1a285-104">製品名</span><span class="sxs-lookup"><span data-stu-id="1a285-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="1a285-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="1a285-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="1a285-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="1a285-106">Event ID</span></span>|-|  
|<span data-ttu-id="1a285-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="1a285-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="1a285-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="1a285-108"> EDI</span></span>|  
|<span data-ttu-id="1a285-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1a285-109">Component</span></span>|<span data-ttu-id="1a285-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="1a285-110">EDI Engine</span></span>|  
|<span data-ttu-id="1a285-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="1a285-111">Symbolic Name</span></span>|<span data-ttu-id="1a285-112">X12Ta1InvalidTimeDescription</span><span class="sxs-lookup"><span data-stu-id="1a285-112">X12Ta1InvalidTimeDescription</span></span>|  
|<span data-ttu-id="1a285-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="1a285-113">Message Text</span></span>|<span data-ttu-id="1a285-114">時刻が無効です</span><span class="sxs-lookup"><span data-stu-id="1a285-114">Invalid Time</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1a285-115">説明</span><span class="sxs-lookup"><span data-stu-id="1a285-115">Explanation</span></span>  
 <span data-ttu-id="1a285-116">このエラー/警告/情報イベントは、データ要素の時刻値が、EDI スキーマで指定されたデータ型に準拠していなかったか、または X12 インターチェンジの GS05 フィールド ヘッダーの時刻値が、サービス スキーマ (BaseArtifacts.dll 内の X12ServiceSchema) に準拠していなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="1a285-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because a time value in a data element did not conform to the data type specified by the EDI schema or the time value in the GS05 field header in an X12 interchange did not conform to the service schema (X12ServiceSchema in BaseArtifacts.dll).</span></span> <span data-ttu-id="1a285-117">X12 の場合、サービス スキーマは、GS05 フィールドの時刻を X12_TM データ型として、4 ～ 8 文字の長さで定義します。</span><span class="sxs-lookup"><span data-stu-id="1a285-117">For X12, the service schema defines a time in the GS05 field as of the X12_TM data type and between four and eight characters in length.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1a285-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="1a285-118">User Action</span></span>  
 <span data-ttu-id="1a285-119">このエラーを解決するには、データ要素の時刻値が、EDI スキーマで指定されたデータ型に準拠しているか、または X12 インターチェンジの GS05 ヘッダーの時刻値がサービス スキーマに準拠していることを確認し、インターチェンジを再送信してもらいます。</span><span class="sxs-lookup"><span data-stu-id="1a285-119">To resolve this error, make sure that a time value in a data element conforms to the data type specified by the EDI schema or a time value in the GS05 header of an X12 interchange conforms to the service schema, and then have the interchange resent.</span></span>