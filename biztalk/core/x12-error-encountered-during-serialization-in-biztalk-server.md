---
title: シリアル化中に発生したエラーです。 X12 機能グループが、次のエラーがありました。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dad987c3-92f3-4a6b-ba1a-b60f6ea2fbe4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a461a5db58a2ca41fdd7e42211fbb798bc6e197
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394757"
---
# <a name="error-encountered-during-serialization-the-x12-functional-group-had-the-following-errors"></a><span data-ttu-id="4169e-103">シリアル化中に発生したエラーです。</span><span class="sxs-lookup"><span data-stu-id="4169e-103">Error encountered during serialization.</span></span> <span data-ttu-id="4169e-104">X12 機能グループが、次のエラーがありました</span><span class="sxs-lookup"><span data-stu-id="4169e-104">The X12 functional group had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="4169e-105">詳細</span><span class="sxs-lookup"><span data-stu-id="4169e-105">Details</span></span>  
  
|                 |                                                                                                                                                                                 |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="4169e-106">製品名</span><span class="sxs-lookup"><span data-stu-id="4169e-106">Product Name</span></span>   |                                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                |
| <span data-ttu-id="4169e-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="4169e-107">Product Version</span></span> |                                                           [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                            |
|    <span data-ttu-id="4169e-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4169e-108">Event ID</span></span>     |                                                                                        -                                                                                        |
|  <span data-ttu-id="4169e-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="4169e-109">Event Source</span></span>   |                                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="4169e-110">EDI</span><span class="sxs-lookup"><span data-stu-id="4169e-110">EDI</span></span>                                              |
|    <span data-ttu-id="4169e-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="4169e-111">Component</span></span>    |                                                                                   <span data-ttu-id="4169e-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="4169e-112">EDI Engine</span></span>                                                                                    |
|  <span data-ttu-id="4169e-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="4169e-113">Symbolic Name</span></span>  |                                                                           <span data-ttu-id="4169e-114">X12FunctionalGroupSendError</span><span class="sxs-lookup"><span data-stu-id="4169e-114">X12FunctionalGroupSendError</span></span>                                                                           |
|  <span data-ttu-id="4169e-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="4169e-115">Message Text</span></span>   | <span data-ttu-id="4169e-116">シリアル化中に発生したエラーです。</span><span class="sxs-lookup"><span data-stu-id="4169e-116">Error encountered during serialization.</span></span> <span data-ttu-id="4169e-117">X12 機能グループ id '{0}'、id を持つインターチェンジ内で'{1}'、送信者 id '{2}'、受信者 id'{3}' 次のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="4169e-117">The X12 functional group with id '{0}', in interchange with id '{1}', with sender id '{2}', receiver id '{3}' had the following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="4169e-118">説明</span><span class="sxs-lookup"><span data-stu-id="4169e-118">Explanation</span></span>  
 <span data-ttu-id="4169e-119">このエラー/警告/情報イベントは、EDI 送信パイプラインでは、X12 の送信をシリアル化するときに、エラーが発生したことを示しますインターチェンジで識別された機能グループ、示されたエラーが原因です。</span><span class="sxs-lookup"><span data-stu-id="4169e-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing an outgoing X12 interchange because of the stated errors with the identified functional group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4169e-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="4169e-120">User Action</span></span>  
 <span data-ttu-id="4169e-121">このエラーを解決するには、エラー メッセージの情報を使用して機能グループでエラーを特定し、製品のヘルプで問題の解決方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="4169e-121">To resolve this error, use the information in the error message to identify the error in the functional group and then determine the problem resolution in the product help.</span></span>