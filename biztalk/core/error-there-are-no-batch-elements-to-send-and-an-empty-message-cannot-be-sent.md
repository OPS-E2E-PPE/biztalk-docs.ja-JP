---
title: 送信するバッチ要素がないと、パーティが構成されていないので、空のメッセージを送信できません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0752079a-173e-4de3-96f4-e5de01b799b5
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a224625122fa498410dc9aed9036fe875e4b739
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346318"
---
# <a name="there-are-no-batch-elements-to-send-and-an-empty-message-cannot-be-sent-as-it-is-not-configured-for-party"></a><span data-ttu-id="bbee7-102">送信するバッチ要素がないと、パーティが構成されていないので、空のメッセージを送信できません。</span><span class="sxs-lookup"><span data-stu-id="bbee7-102">There are no batch elements to send and an empty message cannot be sent as it is not configured for party</span></span>
## <a name="details"></a><span data-ttu-id="bbee7-103">詳細</span><span class="sxs-lookup"><span data-stu-id="bbee7-103">Details</span></span>  
  
|                 |                                                                                                               |
|-----------------|---------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="bbee7-104">製品名</span><span class="sxs-lookup"><span data-stu-id="bbee7-104">Product Name</span></span>   |              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]               |
| <span data-ttu-id="bbee7-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="bbee7-105">Product Version</span></span> |                          [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                           |
|    <span data-ttu-id="bbee7-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="bbee7-106">Event ID</span></span>     |                                                       -                                                       |
|  <span data-ttu-id="bbee7-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="bbee7-107">Event Source</span></span>   |            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="bbee7-108">EDI</span><span class="sxs-lookup"><span data-stu-id="bbee7-108">EDI</span></span>             |
|    <span data-ttu-id="bbee7-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="bbee7-109">Component</span></span>    |                                                <span data-ttu-id="bbee7-110">バッチ処理エンジン</span><span class="sxs-lookup"><span data-stu-id="bbee7-110">Batching Engine</span></span>                                                |
|  <span data-ttu-id="bbee7-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="bbee7-111">Symbolic Name</span></span>  |                                            <span data-ttu-id="bbee7-112">EmptyMessageNotAllowed</span><span class="sxs-lookup"><span data-stu-id="bbee7-112">EmptyMessageNotAllowed</span></span>                                             |
|  <span data-ttu-id="bbee7-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="bbee7-113">Message Text</span></span>   | <span data-ttu-id="bbee7-114">送信するバッチ要素がないと、パーティが構成されていないので、空のメッセージを送信できません。 {0}</span><span class="sxs-lookup"><span data-stu-id="bbee7-114">There are no batch elements to send and an empty message cannot be sent as it is not configured for party {0}</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="bbee7-115">説明</span><span class="sxs-lookup"><span data-stu-id="bbee7-115">Explanation</span></span>  
 <span data-ttu-id="bbee7-116">この警告は、バッチ リリースのスケジュールが設定されているもののバッチ要素が受信されておらず、空のバッチ通知が有効化されていなかったため、スケジュールに基づくバッチ処理プロセスでバッチ メッセージが送信されなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="bbee7-116">This Warning indicates that no batch message was sent in a schedule-based batching process because no batch elements had been received when the batch release was scheduled, and the empty batch signal has not been enabled.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bbee7-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="bbee7-117">User Action</span></span>  
 <span data-ttu-id="bbee7-118">この警告が表示されないようにするには、次の操作を実行して空のバッチ通知を構成します。</span><span class="sxs-lookup"><span data-stu-id="bbee7-118">To prevent this warning from being posted, configure the empty batch signal by doing the following:</span></span>  
  
1.  <span data-ttu-id="bbee7-119">BizTalk Server 管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="bbee7-119">Open the BizTalk Server Administration Console.</span></span>  
  
2.  <span data-ttu-id="bbee7-120">[パーティ] ノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="bbee7-120">Move to the Parties node.</span></span>  
  
3.  <span data-ttu-id="bbee7-121">パーティの [EDI のプロパティ] ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="bbee7-121">Open the EDI Properties dialog box for the party.</span></span>  
  
4.  <span data-ttu-id="bbee7-122">[インターチェンジのバッチ作成用の設定] ノード (適切なエンコード用) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbee7-122">Click the Interchange Batch Creation Settings node (for the appropriate encoding).</span></span>  
  
5.  <span data-ttu-id="bbee7-123">スケジューラをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbee7-123">Click the Scheduler.</span></span>  
  
6.  <span data-ttu-id="bbee7-124">[空のバッチ通知を送信する] プロパティをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbee7-124">Click the Send empty batch signal property.</span></span>