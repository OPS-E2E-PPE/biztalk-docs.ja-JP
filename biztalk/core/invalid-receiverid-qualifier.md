---
title: "無効な ReceiverId 修飾子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52d60f7e-6f16-424d-91b8-dc8181206249
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86c9adc1fa20f244d1061b67878e433d73dfa72d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-receiverid-qualifier"></a><span data-ttu-id="ae8e2-102">ReceiverId 修飾子が無効です</span><span class="sxs-lookup"><span data-stu-id="ae8e2-102">Invalid ReceiverId Qualifier</span></span>
## <a name="details"></a><span data-ttu-id="ae8e2-103">詳細</span><span class="sxs-lookup"><span data-stu-id="ae8e2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ae8e2-104">製品名</span><span class="sxs-lookup"><span data-stu-id="ae8e2-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="ae8e2-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="ae8e2-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="ae8e2-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ae8e2-106">Event ID</span></span>|-|  
|<span data-ttu-id="ae8e2-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="ae8e2-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="ae8e2-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="ae8e2-108"> EDI</span></span>|  
|<span data-ttu-id="ae8e2-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ae8e2-109">Component</span></span>|<span data-ttu-id="ae8e2-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="ae8e2-110">EDI Engine</span></span>|  
|<span data-ttu-id="ae8e2-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="ae8e2-111">Symbolic Name</span></span>|<span data-ttu-id="ae8e2-112">X12Ta1InvalidReceiverIdQualifierDescription</span><span class="sxs-lookup"><span data-stu-id="ae8e2-112">X12Ta1InvalidReceiverIdQualifierDescription</span></span>|  
|<span data-ttu-id="ae8e2-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="ae8e2-113">Message Text</span></span>|<span data-ttu-id="ae8e2-114">ReceiverId 修飾子が無効です</span><span class="sxs-lookup"><span data-stu-id="ae8e2-114">Invalid ReceiverId Qualifier</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ae8e2-115">説明</span><span class="sxs-lookup"><span data-stu-id="ae8e2-115">Explanation</span></span>  
 <span data-ttu-id="ae8e2-116">このエラー/警告/情報イベントは、こと、受信パイプラインために処理できませんでした、受信インターチェンジを示します、ISA07 フィールドの受信者の修飾子 (x12 インターチェンジ) または受信者コードの修飾子 (EDIFACT の [unb3.2] フィールドにインターチェンジの場合) では、サービス スキーマ (X12ServiceSchema または EdifactServiceSchema) で確立された列挙の値が一致しませんでした。</span><span class="sxs-lookup"><span data-stu-id="ae8e2-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the Receiver Qualifier in the ISA07 field (for an X12 interchange) or the Recipient Code Qualifier in the UNB3.2 field (for an EDIFACT interchange) did not match a value in the enumeration established by the service schema (X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ae8e2-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="ae8e2-117">User Action</span></span>  
 <span data-ttu-id="ae8e2-118">このエラーを解決するには、ISA07 フィールドまたは UNB3.2 フィールドが、サービス スキーマで設定されている列挙のいずれかの値と一致するようにします。</span><span class="sxs-lookup"><span data-stu-id="ae8e2-118">To resolve this error, make sure that the ISA07 field or the UNB3.2 field matches one of the values in the enumeration established by the service schema.</span></span> <span data-ttu-id="ae8e2-119">インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="ae8e2-119">Have the interchange resent.</span></span>