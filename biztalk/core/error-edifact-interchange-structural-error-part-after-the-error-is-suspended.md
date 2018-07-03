---
title: インターチェンジで構造エラーが見つかりました。 中断されていますが、エラー後の部分 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9071825d-7b90-42bf-bcf9-2a15ae36086d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e77100200a4fb2eacb24c6745fcd17011231b991
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967307"
---
# <a name="the-interchange-had-structural-error-the-part-after-the-error-is-being-suspended"></a><span data-ttu-id="7a332-103">インターチェンジで構造エラーが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="7a332-103">The interchange had structural error.</span></span> <span data-ttu-id="7a332-104">エラー発生後の部分は中断されています</span><span class="sxs-lookup"><span data-stu-id="7a332-104">The part after the error is being suspended</span></span>
## <a name="details"></a><span data-ttu-id="7a332-105">詳細</span><span class="sxs-lookup"><span data-stu-id="7a332-105">Details</span></span>  
  
|                 |                                                                                                                                                                                |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="7a332-106">製品名</span><span class="sxs-lookup"><span data-stu-id="7a332-106">Product Name</span></span>   |                                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                               |
| <span data-ttu-id="7a332-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="7a332-107">Product Version</span></span> |                                                           [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                           |
|    <span data-ttu-id="7a332-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7a332-108">Event ID</span></span>     |                                                                                       -                                                                                        |
|  <span data-ttu-id="7a332-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="7a332-109">Event Source</span></span>   |                                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="7a332-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="7a332-110"> EDI</span></span>                                             |
|    <span data-ttu-id="7a332-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7a332-111">Component</span></span>    |                                                                                   <span data-ttu-id="7a332-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="7a332-112">EDI Engine</span></span>                                                                                   |
|  <span data-ttu-id="7a332-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="7a332-113">Symbolic Name</span></span>  |                                                                        <span data-ttu-id="7a332-114">EfactInterchangeStructuralError</span><span class="sxs-lookup"><span data-stu-id="7a332-114">EfactInterchangeStructuralError</span></span>                                                                         |
|  <span data-ttu-id="7a332-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="7a332-115">Message Text</span></span>   | <span data-ttu-id="7a332-116">Id を持つインターチェンジ '{0}'、送信者 id'{1}'、受信者 id '{2}' 構造エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="7a332-116">The interchange with id '{0}', with sender id '{1}', receiver id '{2}' had structural error.</span></span> <span data-ttu-id="7a332-117">エラー発生後の部分は中断されています。詳細については、保留キューを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a332-117">The part after the error is being suspended, refer to Suspended Queue for details</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="7a332-118">説明</span><span class="sxs-lookup"><span data-stu-id="7a332-118">Explanation</span></span>  
 <span data-ttu-id="7a332-119">このエラー/警告/情報イベントは、インターチェンジで構造エラーが発生したため、受信パイプラインで受信 EDIFACT インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="7a332-119">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming EDIFACT interchange, because a structural error occurred in the interchange.</span></span> <span data-ttu-id="7a332-120">このイベントは保存中のインターチェンジで発生し、トランザクション セットはエラー時に中断されました。</span><span class="sxs-lookup"><span data-stu-id="7a332-120">This occurred with an interchange that was being preserved, with transaction sets suspended on the error.</span></span> <span data-ttu-id="7a332-121">このエラーにより、このエラーを含むトランザクション セット (複数可) は中断されましたが、それ以外のトランザクション セットは保存されたバッチの一部として処理されました。</span><span class="sxs-lookup"><span data-stu-id="7a332-121">As a result of this error, the transaction set (or sets) that included the error was suspended, but the rest of the transaction sets were processed as part of the preserved batch.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7a332-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="7a332-122">User Action</span></span>  
 <span data-ttu-id="7a332-123">このエラーを解決するには、インターチェンジの送信者が構造上のエラーを修正した上で、インターチェンジを再送信してもらいます。</span><span class="sxs-lookup"><span data-stu-id="7a332-123">To resolve this error, have the sender of the interchange fix the structural error, and then resend the interchange.</span></span>