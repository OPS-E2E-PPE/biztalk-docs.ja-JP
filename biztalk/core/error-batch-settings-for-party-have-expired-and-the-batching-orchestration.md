---
title: "パーティのバッチ設定が有効期限が切れて、バッチ処理オーケストレーションが終了しています |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a2f272b6-4da2-4736-8d61-ce48359f36dd
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d56e06766a980c1ce293b211d2956a86c093726
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-batch-settings-for-party-have-expired-and-the-batching-orchestration-is-being-terminated"></a><span data-ttu-id="e63d3-102">パーティのバッチの設定が期限切れになったため、バッチ処理オーケストレーションが終了しています</span><span class="sxs-lookup"><span data-stu-id="e63d3-102">The batch settings for party have expired and the batching orchestration is being terminated</span></span>
## <a name="details"></a><span data-ttu-id="e63d3-103">詳細</span><span class="sxs-lookup"><span data-stu-id="e63d3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e63d3-104">製品名</span><span class="sxs-lookup"><span data-stu-id="e63d3-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="e63d3-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="e63d3-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="e63d3-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e63d3-106">Event ID</span></span>|-|  
|<span data-ttu-id="e63d3-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="e63d3-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e63d3-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="e63d3-108"> EDI</span></span>|  
|<span data-ttu-id="e63d3-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e63d3-109">Component</span></span>|<span data-ttu-id="e63d3-110">バッチ処理エンジン</span><span class="sxs-lookup"><span data-stu-id="e63d3-110">Batching Engine</span></span>|  
|<span data-ttu-id="e63d3-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="e63d3-111">Symbolic Name</span></span>|<span data-ttu-id="e63d3-112">BatchSettingsExpired</span><span class="sxs-lookup"><span data-stu-id="e63d3-112">BatchSettingsExpired</span></span>|  
|<span data-ttu-id="e63d3-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="e63d3-113">Message Text</span></span>|<span data-ttu-id="e63d3-114">パーティ {0} のバッチの設定が期限切れになったため、バッチ処理オーケストレーションが終了しています。</span><span class="sxs-lookup"><span data-stu-id="e63d3-114">The batch settings for party {0} have expired and the batching orchestration is being terminated.</span></span> <span data-ttu-id="e63d3-115">このパーティのバッチ処理がアクティブになるまで、これ以上バッチは生成されません。</span><span class="sxs-lookup"><span data-stu-id="e63d3-115">Further batches will not be generated till the batching is activated for this party</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e63d3-116">説明</span><span class="sxs-lookup"><span data-stu-id="e63d3-116">Explanation</span></span>  
 <span data-ttu-id="e63d3-117">この警告は、アクティベーションの範囲の終点に達したため、バッチ処理オーケストレーション インスタンスが非アクティブになったことを示します。</span><span class="sxs-lookup"><span data-stu-id="e63d3-117">This Warning indicates that the batching orchestration instance has been deactivated because the end of the activation range has been reached.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e63d3-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="e63d3-118">User Action</span></span>  
 <span data-ttu-id="e63d3-119">このエラーを解決するには、次の操作を行ってバッチ処理プロセスを再開します。</span><span class="sxs-lookup"><span data-stu-id="e63d3-119">To resolve this error, restart the batching process by doing the following:</span></span>  
  
1.  <span data-ttu-id="e63d3-120">BizTalk Server 管理コンソールを開き、[EDI のプロパティ] ダイアログ ボックスの [インターチェンジのバッチ作成用の設定] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="e63d3-120">Open the BizTalk Server Administration Console, and move to the Interchange Batch Creation Settings Page of the EDI Properties dialog box.</span></span>  
  
2.  <span data-ttu-id="e63d3-121">終了条件をリセットしをクリックして、オーケストレーションを再起動**開始**です。</span><span class="sxs-lookup"><span data-stu-id="e63d3-121">Reset the end criteria, and then restart the orchestration by clicking **Start**.</span></span>  
  
3.  <span data-ttu-id="e63d3-122">クリックした日時より前の開始 日時が場合**開始**、 をクリックして**はい**開始日時を現在の日時に更新します。</span><span class="sxs-lookup"><span data-stu-id="e63d3-122">If the Start datetime is prior to the time when you clicked **Start**, click **Yes** to update the Start datetime to the current datetime.</span></span>