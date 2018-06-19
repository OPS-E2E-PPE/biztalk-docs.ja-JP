---
title: インターチェンジで構造エラーが見つかりました。 エラーが中断された後の部分 |Microsoft ドキュメント
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
ms.openlocfilehash: a028608e9843ee40c26bc7e8b158d97552a58163
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241298"
---
# <a name="the-interchange-had-structural-error-the-part-after-the-error-is-being-suspended"></a><span data-ttu-id="579eb-103">インターチェンジで構造エラーが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="579eb-103">The interchange had structural error.</span></span> <span data-ttu-id="579eb-104">エラー発生後の部分は中断されています</span><span class="sxs-lookup"><span data-stu-id="579eb-104">The part after the error is being suspended</span></span>
## <a name="details"></a><span data-ttu-id="579eb-105">詳細</span><span class="sxs-lookup"><span data-stu-id="579eb-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="579eb-106">製品名</span><span class="sxs-lookup"><span data-stu-id="579eb-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="579eb-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="579eb-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="579eb-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="579eb-108">Event ID</span></span>|-|  
|<span data-ttu-id="579eb-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="579eb-109">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="579eb-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="579eb-110"> EDI</span></span>|  
|<span data-ttu-id="579eb-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="579eb-111">Component</span></span>|<span data-ttu-id="579eb-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="579eb-112">EDI Engine</span></span>|  
|<span data-ttu-id="579eb-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="579eb-113">Symbolic Name</span></span>|<span data-ttu-id="579eb-114">EfactInterchangeStructuralError</span><span class="sxs-lookup"><span data-stu-id="579eb-114">EfactInterchangeStructuralError</span></span>|  
|<span data-ttu-id="579eb-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="579eb-115">Message Text</span></span>|<span data-ttu-id="579eb-116">Id '{0}'、送信者 id '{1}' で、インターチェンジ受信者 id '{2}' には、構造エラーが必要があります。</span><span class="sxs-lookup"><span data-stu-id="579eb-116">The interchange with id '{0}', with sender id '{1}', receiver id '{2}' had structural error.</span></span> <span data-ttu-id="579eb-117">エラー発生後の部分は中断されています。詳細については、保留キューを参照してください。</span><span class="sxs-lookup"><span data-stu-id="579eb-117">The part after the error is being suspended, refer to Suspended Queue for details</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="579eb-118">説明</span><span class="sxs-lookup"><span data-stu-id="579eb-118">Explanation</span></span>  
 <span data-ttu-id="579eb-119">このエラー/警告/情報イベントは、インターチェンジで構造エラーが発生したため、受信パイプラインで受信 EDIFACT インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="579eb-119">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming EDIFACT interchange, because a structural error occurred in the interchange.</span></span> <span data-ttu-id="579eb-120">このイベントは保存中のインターチェンジで発生し、トランザクション セットはエラー時に中断されました。</span><span class="sxs-lookup"><span data-stu-id="579eb-120">This occurred with an interchange that was being preserved, with transaction sets suspended on the error.</span></span> <span data-ttu-id="579eb-121">このエラーにより、このエラーを含むトランザクション セット (複数可) は中断されましたが、それ以外のトランザクション セットは保存されたバッチの一部として処理されました。</span><span class="sxs-lookup"><span data-stu-id="579eb-121">As a result of this error, the transaction set (or sets) that included the error was suspended, but the rest of the transaction sets were processed as part of the preserved batch.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="579eb-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="579eb-122">User Action</span></span>  
 <span data-ttu-id="579eb-123">このエラーを解決するには、インターチェンジの送信者が構造上のエラーを修正した上で、インターチェンジを再送信してもらいます。</span><span class="sxs-lookup"><span data-stu-id="579eb-123">To resolve this error, have the sender of the interchange fix the structural error, and then resend the interchange.</span></span>