---
title: SenderId が無効な修飾子 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cfe9c51c-d569-4f14-a690-f145ef1bf6a4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc05357a18679af845c6556a9a96952dbe8bfe3e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330463"
---
# <a name="invalid-senderid-qualifier"></a><span data-ttu-id="0b182-102">SenderId 修飾子が無効です</span><span class="sxs-lookup"><span data-stu-id="0b182-102">Invalid SenderId Qualifier</span></span>
## <a name="details"></a><span data-ttu-id="0b182-103">詳細</span><span class="sxs-lookup"><span data-stu-id="0b182-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="0b182-104">製品名</span><span class="sxs-lookup"><span data-stu-id="0b182-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="0b182-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="0b182-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="0b182-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0b182-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="0b182-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="0b182-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="0b182-108">EDI</span><span class="sxs-lookup"><span data-stu-id="0b182-108">EDI</span></span> |
|    <span data-ttu-id="0b182-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0b182-109">Component</span></span>    |                                       <span data-ttu-id="0b182-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="0b182-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="0b182-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="0b182-111">Symbolic Name</span></span>  |                       <span data-ttu-id="0b182-112">X12Ta1InvalidSenderIdQualifierDescription</span><span class="sxs-lookup"><span data-stu-id="0b182-112">X12Ta1InvalidSenderIdQualifierDescription</span></span>                        |
|  <span data-ttu-id="0b182-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="0b182-113">Message Text</span></span>   |                               <span data-ttu-id="0b182-114">SenderId 修飾子が無効です</span><span class="sxs-lookup"><span data-stu-id="0b182-114">Invalid SenderId Qualifier</span></span>                               |
  
## <a name="explanation"></a><span data-ttu-id="0b182-115">説明</span><span class="sxs-lookup"><span data-stu-id="0b182-115">Explanation</span></span>  
 <span data-ttu-id="0b182-116">このエラー/警告/情報イベントは、ISA05 フィールドの送信者修飾子 (X12 インターチェンジの場合) または UNB2.2 フィールドの送信者コード修飾子 (EDIFACT インターチェンジの場合) が、サービス スキーマ (BaseArtifacts.dll 内の X12ServiceSchema または EdifactServiceSchema) で確立された列挙の値に一致しなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="0b182-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the Sender Qualifier in the ISA05 field (for an X12 interchange) or the Sender Code Qualifier in the UNB2.2 field (for an EDIFACT interchange) did not match a value in the enumeration established by the service schema (X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0b182-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="0b182-117">User Action</span></span>  
 <span data-ttu-id="0b182-118">このエラーを解決するには、ISA07 フィールドまたは UNB3.2 フィールドが、サービス スキーマで設定されている列挙のいずれかの値と一致するようにします。</span><span class="sxs-lookup"><span data-stu-id="0b182-118">To resolve this error, make sure that the ISA07 field or the UNB3.2 field matches one of the values in the enumeration established by the service schema.</span></span> <span data-ttu-id="0b182-119">インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="0b182-119">Have the interchange resent.</span></span>