---
title: 無効な日付 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a41da9c5-9dcf-44cd-be5b-922e6c267ec3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd96e7022d05696c01977266ebdfda6f14876aad
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381282"
---
# <a name="invalid-date"></a><span data-ttu-id="12fe7-102">日付が無効です</span><span class="sxs-lookup"><span data-stu-id="12fe7-102">Invalid Date</span></span>
## <a name="details"></a><span data-ttu-id="12fe7-103">詳細</span><span class="sxs-lookup"><span data-stu-id="12fe7-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="12fe7-104">製品名</span><span class="sxs-lookup"><span data-stu-id="12fe7-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="12fe7-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="12fe7-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="12fe7-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="12fe7-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="12fe7-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="12fe7-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="12fe7-108">EDI</span><span class="sxs-lookup"><span data-stu-id="12fe7-108">EDI</span></span> |
|    <span data-ttu-id="12fe7-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="12fe7-109">Component</span></span>    |                                       <span data-ttu-id="12fe7-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="12fe7-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="12fe7-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="12fe7-111">Symbolic Name</span></span>  |                              <span data-ttu-id="12fe7-112">X12DeInvalidDateDescription</span><span class="sxs-lookup"><span data-stu-id="12fe7-112">X12DeInvalidDateDescription</span></span>                               |
|  <span data-ttu-id="12fe7-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="12fe7-113">Message Text</span></span>   |                                      <span data-ttu-id="12fe7-114">日付が無効です</span><span class="sxs-lookup"><span data-stu-id="12fe7-114">Invalid Date</span></span>                                      |
  
## <a name="explanation"></a><span data-ttu-id="12fe7-115">説明</span><span class="sxs-lookup"><span data-stu-id="12fe7-115">Explanation</span></span>  
 <span data-ttu-id="12fe7-116">このエラー/警告/情報イベントは、データ要素の日付値が、EDI スキーマで指定されたデータ型に準拠していなかったか、または X12 インターチェンジの GS04 フィールド ヘッダーの日付値が、サービス スキーマ (BaseArtifacts.dll 内の X12ServiceSchema) に準拠していなかったため、受信パイプラインで受信インターチェンジを処理できなかったか、または送信パイプラインで送信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="12fe7-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange or the send pipeline could not process the outgoing interchange because a date value in a data element did not conform to the data type specified by the EDI schema or the date value in the GS04 field header in an X12 interchange did not conform to the service schema (X12ServiceSchema in BaseArtifacts.dll).</span></span> <span data-ttu-id="12fe7-117">X12 の場合、サービス スキーマは、GS04 フィールドの日付を X12_DT データ型として、6 ～ 8 文字の長さで定義します。</span><span class="sxs-lookup"><span data-stu-id="12fe7-117">For X12, the service schema defines a date in the GS04 field as of the X12_DT data type and between six and eight characters in length.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="12fe7-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="12fe7-118">User Action</span></span>  
 <span data-ttu-id="12fe7-119">このエラーを解決するには、データ要素の時間値が、EDI スキーマで定義されたデータ型に準拠しているか、または X12 インターチェンジの GS04 ヘッダーの日付値がサービス スキーマに準拠していることを確認し、インターチェンジを再送信してもらいます。</span><span class="sxs-lookup"><span data-stu-id="12fe7-119">To resolve this error, make sure that the time value in a data element conforms to the data type specified by the EDI schema or the date value in the GS04 header of an X12 interchange conforms to the service schema, and then have the interchange resent.</span></span>