---
title: ReceiverId が無効な修飾子 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52d60f7e-6f16-424d-91b8-dc8181206249
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e023f205252b04dc5122cfa8c01b617758a25771
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381329"
---
# <a name="invalid-receiverid-qualifier"></a><span data-ttu-id="60fca-102">ReceiverId が無効な修飾子</span><span class="sxs-lookup"><span data-stu-id="60fca-102">Invalid ReceiverId Qualifier</span></span>
## <a name="details"></a><span data-ttu-id="60fca-103">詳細</span><span class="sxs-lookup"><span data-stu-id="60fca-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="60fca-104">製品名</span><span class="sxs-lookup"><span data-stu-id="60fca-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="60fca-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="60fca-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="60fca-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="60fca-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="60fca-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="60fca-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="60fca-108">EDI</span><span class="sxs-lookup"><span data-stu-id="60fca-108">EDI</span></span> |
|    <span data-ttu-id="60fca-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="60fca-109">Component</span></span>    |                                       <span data-ttu-id="60fca-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="60fca-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="60fca-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="60fca-111">Symbolic Name</span></span>  |                      <span data-ttu-id="60fca-112">X12Ta1InvalidReceiverIdQualifierDescription</span><span class="sxs-lookup"><span data-stu-id="60fca-112">X12Ta1InvalidReceiverIdQualifierDescription</span></span>                       |
|  <span data-ttu-id="60fca-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="60fca-113">Message Text</span></span>   |                              <span data-ttu-id="60fca-114">ReceiverId が無効な修飾子</span><span class="sxs-lookup"><span data-stu-id="60fca-114">Invalid ReceiverId Qualifier</span></span>                              |
  
## <a name="explanation"></a><span data-ttu-id="60fca-115">説明</span><span class="sxs-lookup"><span data-stu-id="60fca-115">Explanation</span></span>  
 <span data-ttu-id="60fca-116">このエラー/警告/情報イベントは、エントリのため、受信パイプラインが受信インターチェンジが処理しないことを示します [isa07] フィールドの受信者の修飾子 (x12 インターチェンジ) または受信者コードの修飾子 (EDIFACT の [unb3.2] フィールドインターチェンジの場合) では、サービス スキーマ (X12ServiceSchema または EdifactServiceSchema) で設定されている列挙の値が一致しませんでした。</span><span class="sxs-lookup"><span data-stu-id="60fca-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the Receiver Qualifier in the ISA07 field (for an X12 interchange) or the Recipient Code Qualifier in the UNB3.2 field (for an EDIFACT interchange) did not match a value in the enumeration established by the service schema (X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="60fca-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="60fca-117">User Action</span></span>  
 <span data-ttu-id="60fca-118">このエラーを解決するには、ISA07 フィールドまたは UNB3.2 フィールドが、サービス スキーマで設定されている列挙のいずれかの値と一致するようにします。</span><span class="sxs-lookup"><span data-stu-id="60fca-118">To resolve this error, make sure that the ISA07 field or the UNB3.2 field matches one of the values in the enumeration established by the service schema.</span></span> <span data-ttu-id="60fca-119">インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="60fca-119">Have the interchange resent.</span></span>