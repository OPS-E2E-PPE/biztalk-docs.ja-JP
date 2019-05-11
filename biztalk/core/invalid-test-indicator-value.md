---
title: 無効なテスト インジケーターの値 |Microsoft Docs
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
ms.openlocfilehash: 01525f716ab77b91c83e3baf884761b317d78ec1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381041"
---
# <a name="invalid-test-indicator-value"></a><span data-ttu-id="d607d-102">テスト インジケーターの値が無効です</span><span class="sxs-lookup"><span data-stu-id="d607d-102">Invalid Test Indicator Value</span></span>
## <a name="details"></a><span data-ttu-id="d607d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="d607d-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="d607d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="d607d-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="d607d-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d607d-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="d607d-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d607d-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="d607d-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d607d-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="d607d-108">EDI</span><span class="sxs-lookup"><span data-stu-id="d607d-108">EDI</span></span> |
|    <span data-ttu-id="d607d-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d607d-109">Component</span></span>    |                                       <span data-ttu-id="d607d-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="d607d-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="d607d-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d607d-111">Symbolic Name</span></span>  |                       <span data-ttu-id="d607d-112">X12Ta1InvalidTestIndicatorValueDescription</span><span class="sxs-lookup"><span data-stu-id="d607d-112">X12Ta1InvalidTestIndicatorValueDescription</span></span>                       |
|  <span data-ttu-id="d607d-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d607d-113">Message Text</span></span>   |                              <span data-ttu-id="d607d-114">テスト インジケーターの値が無効です</span><span class="sxs-lookup"><span data-stu-id="d607d-114">Invalid Test Indicator Value</span></span>                              |
  
## <a name="explanation"></a><span data-ttu-id="d607d-115">説明</span><span class="sxs-lookup"><span data-stu-id="d607d-115">Explanation</span></span>  
 <span data-ttu-id="d607d-116">このエラー/警告/情報イベントは、UNB11 フィールドのテスト インジケーターがサービス スキーマ (BaseArtifacts.dll 内の X12ServiceSchema または EdifactServiceSchema) で設定されたデータ型と桁数に準拠していなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="d607d-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the Test Indicator in the UNB11 field did not conform to the data type and number of digits established by the service schema (X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d607d-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d607d-117">User Action</span></span>  
 <span data-ttu-id="d607d-118">このエラーを解決するには、UNB11 フィールドが EDIFACT_N データ型であり、1 文字の長さであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d607d-118">To resolve this error, make sure that the UNB11 field is of the EDIFACT_N data type and is 1 character in length.</span></span> <span data-ttu-id="d607d-119">インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="d607d-119">Have the interchange resent.</span></span>