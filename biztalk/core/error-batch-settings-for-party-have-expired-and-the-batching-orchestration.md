---
title: パーティのバッチ設定の期限が切れているし、バッチ処理オーケストレーションが終了しています |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2f272b6-4da2-4736-8d61-ce48359f36dd
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 896eb6325aa2bac076908643e582d286f2b5febe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389403"
---
# <a name="the-batch-settings-for-party-have-expired-and-the-batching-orchestration-is-being-terminated"></a><span data-ttu-id="cfcd2-102">パーティのバッチ設定の期限が切れているし、バッチ処理オーケストレーションが終了しています</span><span class="sxs-lookup"><span data-stu-id="cfcd2-102">The batch settings for party have expired and the batching orchestration is being terminated</span></span>
## <a name="details"></a><span data-ttu-id="cfcd2-103">詳細</span><span class="sxs-lookup"><span data-stu-id="cfcd2-103">Details</span></span>  
  
|                 |                                                                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="cfcd2-104">製品名</span><span class="sxs-lookup"><span data-stu-id="cfcd2-104">Product Name</span></span>   |                                                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                   |
| <span data-ttu-id="cfcd2-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="cfcd2-105">Product Version</span></span> |                                                              [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                               |
|    <span data-ttu-id="cfcd2-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="cfcd2-106">Event ID</span></span>     |                                                                                           -                                                                                           |
|  <span data-ttu-id="cfcd2-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="cfcd2-107">Event Source</span></span>   |                                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="cfcd2-108">EDI</span><span class="sxs-lookup"><span data-stu-id="cfcd2-108">EDI</span></span>                                                 |
|    <span data-ttu-id="cfcd2-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="cfcd2-109">Component</span></span>    |                                                                                    <span data-ttu-id="cfcd2-110">バッチ処理エンジン</span><span class="sxs-lookup"><span data-stu-id="cfcd2-110">Batching Engine</span></span>                                                                                    |
|  <span data-ttu-id="cfcd2-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="cfcd2-111">Symbolic Name</span></span>  |                                                                                 <span data-ttu-id="cfcd2-112">BatchSettingsExpired</span><span class="sxs-lookup"><span data-stu-id="cfcd2-112">BatchSettingsExpired</span></span>                                                                                  |
|  <span data-ttu-id="cfcd2-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="cfcd2-113">Message Text</span></span>   | <span data-ttu-id="cfcd2-114">パーティのバッチ設定{0}期限が切れていると、バッチ処理オーケストレーションが終了しています。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-114">The batch settings for party {0} have expired and the batching orchestration is being terminated.</span></span> <span data-ttu-id="cfcd2-115">このパーティのバッチ処理がアクティブ化されるまで、これ以上バッチは生成されません。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-115">Further batches will not be generated till the batching is activated for this party</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="cfcd2-116">説明</span><span class="sxs-lookup"><span data-stu-id="cfcd2-116">Explanation</span></span>  
 <span data-ttu-id="cfcd2-117">この警告は、アクティベーションの範囲の末尾に達しているため、バッチ処理オーケストレーション インスタンスはアクティブすることを示します。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-117">This Warning indicates that the batching orchestration instance has been deactivated because the end of the activation range has been reached.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cfcd2-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="cfcd2-118">User Action</span></span>  
 <span data-ttu-id="cfcd2-119">このエラーを解決するには、次の手順に従ってバッチ処理のプロセスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-119">To resolve this error, restart the batching process by doing the following:</span></span>  
  
1.  <span data-ttu-id="cfcd2-120">BizTalk Server 管理コンソールを開き、インターチェンジのバッチ作成の設定 ページの EDI のプロパティ ダイアログ ボックスに移動します。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-120">Open the BizTalk Server Administration Console, and move to the Interchange Batch Creation Settings Page of the EDI Properties dialog box.</span></span>  
  
2.  <span data-ttu-id="cfcd2-121">最後の条件をリセットしをクリックして、オーケストレーションを再起動**開始**します。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-121">Reset the end criteria, and then restart the orchestration by clicking **Start**.</span></span>  
  
3.  <span data-ttu-id="cfcd2-122">クリックした日時より前の開始 日時が場合**開始**、 をクリックして**はい**開始日時を現在の日時に更新します。</span><span class="sxs-lookup"><span data-stu-id="cfcd2-122">If the Start datetime is prior to the time when you clicked **Start**, click **Yes** to update the Start datetime to the current datetime.</span></span>