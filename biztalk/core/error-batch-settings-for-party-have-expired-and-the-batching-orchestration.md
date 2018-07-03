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
ms.openlocfilehash: 471d42035f0c8c279fd25e8bb5ba480f7e0f962a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990059"
---
# <a name="the-batch-settings-for-party-have-expired-and-the-batching-orchestration-is-being-terminated"></a><span data-ttu-id="9746e-102">パーティのバッチの設定が期限切れになったため、バッチ処理オーケストレーションが終了しています</span><span class="sxs-lookup"><span data-stu-id="9746e-102">The batch settings for party have expired and the batching orchestration is being terminated</span></span>
## <a name="details"></a><span data-ttu-id="9746e-103">詳細</span><span class="sxs-lookup"><span data-stu-id="9746e-103">Details</span></span>  
  
|                 |                                                                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="9746e-104">製品名</span><span class="sxs-lookup"><span data-stu-id="9746e-104">Product Name</span></span>   |                                                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                   |
| <span data-ttu-id="9746e-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="9746e-105">Product Version</span></span> |                                                              [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                               |
|    <span data-ttu-id="9746e-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="9746e-106">Event ID</span></span>     |                                                                                           -                                                                                           |
|  <span data-ttu-id="9746e-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="9746e-107">Event Source</span></span>   |                                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="9746e-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="9746e-108"> EDI</span></span>                                                 |
|    <span data-ttu-id="9746e-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9746e-109">Component</span></span>    |                                                                                    <span data-ttu-id="9746e-110">バッチ処理エンジン</span><span class="sxs-lookup"><span data-stu-id="9746e-110">Batching Engine</span></span>                                                                                    |
|  <span data-ttu-id="9746e-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="9746e-111">Symbolic Name</span></span>  |                                                                                 <span data-ttu-id="9746e-112">BatchSettingsExpired</span><span class="sxs-lookup"><span data-stu-id="9746e-112">BatchSettingsExpired</span></span>                                                                                  |
|  <span data-ttu-id="9746e-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="9746e-113">Message Text</span></span>   | <span data-ttu-id="9746e-114">パーティのバッチ設定{0}期限が切れていると、バッチ処理オーケストレーションが終了しています。</span><span class="sxs-lookup"><span data-stu-id="9746e-114">The batch settings for party {0} have expired and the batching orchestration is being terminated.</span></span> <span data-ttu-id="9746e-115">このパーティのバッチ処理がアクティブになるまで、これ以上バッチは生成されません。</span><span class="sxs-lookup"><span data-stu-id="9746e-115">Further batches will not be generated till the batching is activated for this party</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="9746e-116">説明</span><span class="sxs-lookup"><span data-stu-id="9746e-116">Explanation</span></span>  
 <span data-ttu-id="9746e-117">この警告は、アクティベーションの範囲の終点に達したため、バッチ処理オーケストレーション インスタンスが非アクティブになったことを示します。</span><span class="sxs-lookup"><span data-stu-id="9746e-117">This Warning indicates that the batching orchestration instance has been deactivated because the end of the activation range has been reached.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9746e-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="9746e-118">User Action</span></span>  
 <span data-ttu-id="9746e-119">このエラーを解決するには、次の操作を行ってバッチ処理プロセスを再開します。</span><span class="sxs-lookup"><span data-stu-id="9746e-119">To resolve this error, restart the batching process by doing the following:</span></span>  
  
1.  <span data-ttu-id="9746e-120">BizTalk Server 管理コンソールを開き、[EDI のプロパティ] ダイアログ ボックスの [インターチェンジのバッチ作成用の設定] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="9746e-120">Open the BizTalk Server Administration Console, and move to the Interchange Batch Creation Settings Page of the EDI Properties dialog box.</span></span>  
  
2.  <span data-ttu-id="9746e-121">最後の条件をリセットしをクリックして、オーケストレーションを再起動**開始**します。</span><span class="sxs-lookup"><span data-stu-id="9746e-121">Reset the end criteria, and then restart the orchestration by clicking **Start**.</span></span>  
  
3.  <span data-ttu-id="9746e-122">クリックした日時より前の開始 日時が場合**開始**、 をクリックして**はい**開始日時を現在の日時に更新します。</span><span class="sxs-lookup"><span data-stu-id="9746e-122">If the Start datetime is prior to the time when you clicked **Start**, click **Yes** to update the Start datetime to the current datetime.</span></span>