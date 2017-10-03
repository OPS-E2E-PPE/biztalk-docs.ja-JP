---
title: "Receiverid が無効です |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: feabf940-c49b-4f4a-8906-230dc8fb1b30
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d397c75efe1172f87def3dee92e20f4d0d7ef4d1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-receiverid"></a><span data-ttu-id="1313f-102">ReceiverId が無効です</span><span class="sxs-lookup"><span data-stu-id="1313f-102">Invalid ReceiverId</span></span>
## <a name="details"></a><span data-ttu-id="1313f-103">詳細</span><span class="sxs-lookup"><span data-stu-id="1313f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1313f-104">製品名</span><span class="sxs-lookup"><span data-stu-id="1313f-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="1313f-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="1313f-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="1313f-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="1313f-106">Event ID</span></span>|-|  
|<span data-ttu-id="1313f-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="1313f-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="1313f-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="1313f-108"> EDI</span></span>|  
|<span data-ttu-id="1313f-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1313f-109">Component</span></span>|<span data-ttu-id="1313f-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="1313f-110">EDI Engine</span></span>|  
|<span data-ttu-id="1313f-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="1313f-111">Symbolic Name</span></span>|<span data-ttu-id="1313f-112">X12Ta1InvalidReceiverIdDescription</span><span class="sxs-lookup"><span data-stu-id="1313f-112">X12Ta1InvalidReceiverIdDescription</span></span>|  
|<span data-ttu-id="1313f-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="1313f-113">Message Text</span></span>|<span data-ttu-id="1313f-114">ReceiverId が無効です</span><span class="sxs-lookup"><span data-stu-id="1313f-114">Invalid ReceiverId</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1313f-115">説明</span><span class="sxs-lookup"><span data-stu-id="1313f-115">Explanation</span></span>  
 <span data-ttu-id="1313f-116">このエラー/警告/情報イベントは、ISA08 フィールドの受信者 ID または UNB3.1 フィールドの受信者 ID が、サービス スキーマ (BaseArtifacts.dll 内の X12ServiceSchema または EdifactServiceSchema) で設定されたデータ型と桁数に準拠していなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="1313f-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the Receiver ID in the ISA08 field or the Recipient Identification in the UNB3.1 field did not conform to the data type and number of digits established by the service schema (X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1313f-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="1313f-117">User Action</span></span>  
 <span data-ttu-id="1313f-118">このエラーを解決するには、ISA08 フィールドが X12_AN データ型で、長さが 15 桁 (末尾のスペースの有無とは無関係) であるか、または UNB3.1 フィールドが EDIFACT_AN データ型で、長さが 1 ～ 35 文字の範囲であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1313f-118">To resolve this error, make sure that the ISA08 field is of the X12_AN data type and is 15 characters long (with or without trailing spaces) or that the UNB3.1 field is of the EDIFACT_AN data type and is between 1 and 35 characters.</span></span> <span data-ttu-id="1313f-119">インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="1313f-119">Have the interchange resent.</span></span>