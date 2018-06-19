---
title: 無効なテスト インジケーターの値 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d81d501-4020-4ff9-955c-5674a99d250b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 166ab446831243c58b1c12881393be1466399e0c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22261794"
---
# <a name="invalid-test-indicator-value"></a><span data-ttu-id="73829-102">テスト インジケーターの値が無効です</span><span class="sxs-lookup"><span data-stu-id="73829-102">Invalid Test Indicator Value</span></span>
## <a name="details"></a><span data-ttu-id="73829-103">詳細</span><span class="sxs-lookup"><span data-stu-id="73829-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="73829-104">製品名</span><span class="sxs-lookup"><span data-stu-id="73829-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="73829-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="73829-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="73829-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="73829-106">Event ID</span></span>|-|  
|<span data-ttu-id="73829-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="73829-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="73829-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="73829-108"> EDI</span></span>|  
|<span data-ttu-id="73829-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="73829-109">Component</span></span>|<span data-ttu-id="73829-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="73829-110">EDI Engine</span></span>|  
|<span data-ttu-id="73829-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="73829-111">Symbolic Name</span></span>|<span data-ttu-id="73829-112">X12Ta1InvalidTestIndicatorValueDescription</span><span class="sxs-lookup"><span data-stu-id="73829-112">X12Ta1InvalidTestIndicatorValueDescription</span></span>|  
|<span data-ttu-id="73829-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="73829-113">Message Text</span></span>|<span data-ttu-id="73829-114">テスト インジケーターの値が無効です</span><span class="sxs-lookup"><span data-stu-id="73829-114">Invalid Test Indicator Value</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="73829-115">説明</span><span class="sxs-lookup"><span data-stu-id="73829-115">Explanation</span></span>  
 <span data-ttu-id="73829-116">このエラー/警告/情報イベントは、UNB11 フィールドのテスト インジケーターがサービス スキーマ (BaseArtifacts.dll 内の X12ServiceSchema または EdifactServiceSchema) で設定されたデータ型と桁数に準拠していなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="73829-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the Test Indicator in the UNB11 field did not conform to the data type and number of digits established by the service schema (X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="73829-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="73829-117">User Action</span></span>  
 <span data-ttu-id="73829-118">このエラーを解決するには、UNB11 フィールドが EDIFACT_N データ型であり、1 文字の長さであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="73829-118">To resolve this error, make sure that the UNB11 field is of the EDIFACT_N data type and is 1 character in length.</span></span> <span data-ttu-id="73829-119">インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="73829-119">Have the interchange resent.</span></span>