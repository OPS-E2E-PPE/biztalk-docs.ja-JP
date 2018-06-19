---
title: 'インターチェンジで構造エラーが見つかりました。 最後の構造上有効な機能グループ ID が: |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bd62855b-ecc6-4cfd-be9c-0025348eb841
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 565a4865455cabef3cd53988d601a89ecf1549e0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241410"
---
# <a name="the-interchange-had-structural-error-last-structurally-valid-functional-group-id-was"></a><span data-ttu-id="e4485-103">インターチェンジで構造エラーが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="e4485-103">The interchange had structural error.</span></span> <span data-ttu-id="e4485-104">構造上有効な最後の機能グループ ID: </span><span class="sxs-lookup"><span data-stu-id="e4485-104">Last structurally valid functional group ID was:</span></span>
## <a name="details"></a><span data-ttu-id="e4485-105">詳細</span><span class="sxs-lookup"><span data-stu-id="e4485-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e4485-106">製品名</span><span class="sxs-lookup"><span data-stu-id="e4485-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="e4485-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="e4485-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="e4485-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e4485-108">Event ID</span></span>|-|  
|<span data-ttu-id="e4485-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="e4485-109">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e4485-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="e4485-110"> EDI</span></span>|  
|<span data-ttu-id="e4485-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e4485-111">Component</span></span>|<span data-ttu-id="e4485-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="e4485-112">EDI Engine</span></span>|  
|<span data-ttu-id="e4485-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="e4485-113">Symbolic Name</span></span>|<span data-ttu-id="e4485-114">X12InterchangeStructuralErrorAfter1stGroup</span><span class="sxs-lookup"><span data-stu-id="e4485-114">X12InterchangeStructuralErrorAfter1stGroup</span></span>|  
|<span data-ttu-id="e4485-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="e4485-115">Message Text</span></span>|<span data-ttu-id="e4485-116">Id '{0}'、送信者 id '{1}' で、インターチェンジ受信者 id '{2}' には、構造エラーが必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4485-116">The interchange with id '{0}', with sender id '{1}', receiver id '{2}' had structural error.</span></span> <span data-ttu-id="e4485-117">最後の構造上有効な機能グループ ID が '{3}'</span><span class="sxs-lookup"><span data-stu-id="e4485-117">Last structurally valid functional group ID was '{3}'</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e4485-118">説明</span><span class="sxs-lookup"><span data-stu-id="e4485-118">Explanation</span></span>  
 <span data-ttu-id="e4485-119">このエラー/警告/情報イベントは、表示された機能グループの後にインターチェンジで構造エラーが発生したため、受信パイプラインで受信 X12 インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="e4485-119">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange, because a structural error occurred in the interchange after the indicated functional group.</span></span> <span data-ttu-id="e4485-120">このイベントは保存中のインターチェンジで発生し、トランザクション セットはエラー時に中断された可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e4485-120">This may have occurred with an interchange that was being preserved, with transaction sets suspended on the error.</span></span> <span data-ttu-id="e4485-121">このエラーにより、このエラーを含むトランザクション セット (複数可) は中断されましたが、それ以外のトランザクション セットは保存されたバッチの一部として処理されました。</span><span class="sxs-lookup"><span data-stu-id="e4485-121">As a result of this error, the transaction set (or sets) that included the error was suspended, but the rest of the transaction sets were processed as part of the preserved batch.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e4485-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="e4485-122">User Action</span></span>  
 <span data-ttu-id="e4485-123">このエラーを解決するには、インターチェンジの送信者が構造上のエラーを修正した上で、インターチェンジを再送信してもらいます。</span><span class="sxs-lookup"><span data-stu-id="e4485-123">To resolve this error, have the sender of the interchange fix the structural error, and then resend the interchange.</span></span>