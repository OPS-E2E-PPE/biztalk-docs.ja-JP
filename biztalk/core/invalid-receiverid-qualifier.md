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
ms.openlocfilehash: 7f4cf13bb338959ca4cd7d2d25a85749f0ff0171
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981819"
---
# <a name="invalid-receiverid-qualifier"></a><span data-ttu-id="f8c6e-102">ReceiverId 修飾子が無効です</span><span class="sxs-lookup"><span data-stu-id="f8c6e-102">Invalid ReceiverId Qualifier</span></span>
## <a name="details"></a><span data-ttu-id="f8c6e-103">詳細</span><span class="sxs-lookup"><span data-stu-id="f8c6e-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="f8c6e-104">製品名</span><span class="sxs-lookup"><span data-stu-id="f8c6e-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="f8c6e-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f8c6e-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="f8c6e-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f8c6e-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="f8c6e-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f8c6e-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="f8c6e-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="f8c6e-108"> EDI</span></span> |
|    <span data-ttu-id="f8c6e-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f8c6e-109">Component</span></span>    |                                       <span data-ttu-id="f8c6e-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="f8c6e-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="f8c6e-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f8c6e-111">Symbolic Name</span></span>  |                      <span data-ttu-id="f8c6e-112">X12Ta1InvalidReceiverIdQualifierDescription</span><span class="sxs-lookup"><span data-stu-id="f8c6e-112">X12Ta1InvalidReceiverIdQualifierDescription</span></span>                       |
|  <span data-ttu-id="f8c6e-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f8c6e-113">Message Text</span></span>   |                              <span data-ttu-id="f8c6e-114">ReceiverId 修飾子が無効です</span><span class="sxs-lookup"><span data-stu-id="f8c6e-114">Invalid ReceiverId Qualifier</span></span>                              |
  
## <a name="explanation"></a><span data-ttu-id="f8c6e-115">説明</span><span class="sxs-lookup"><span data-stu-id="f8c6e-115">Explanation</span></span>  
 <span data-ttu-id="f8c6e-116">このエラー/警告/情報イベントは、エントリのため、受信パイプラインが受信インターチェンジが処理しないことを示します [isa07] フィールドの受信者の修飾子 (x12 インターチェンジ) または受信者コードの修飾子 (EDIFACT の [unb3.2] フィールドインターチェンジの場合) では、サービス スキーマ (X12ServiceSchema または EdifactServiceSchema) で設定されている列挙の値が一致しませんでした。</span><span class="sxs-lookup"><span data-stu-id="f8c6e-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the Receiver Qualifier in the ISA07 field (for an X12 interchange) or the Recipient Code Qualifier in the UNB3.2 field (for an EDIFACT interchange) did not match a value in the enumeration established by the service schema (X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f8c6e-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f8c6e-117">User Action</span></span>  
 <span data-ttu-id="f8c6e-118">このエラーを解決するには、ISA07 フィールドまたは UNB3.2 フィールドが、サービス スキーマで設定されている列挙のいずれかの値と一致するようにします。</span><span class="sxs-lookup"><span data-stu-id="f8c6e-118">To resolve this error, make sure that the ISA07 field or the UNB3.2 field matches one of the values in the enumeration established by the service schema.</span></span> <span data-ttu-id="f8c6e-119">インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="f8c6e-119">Have the interchange resent.</span></span>