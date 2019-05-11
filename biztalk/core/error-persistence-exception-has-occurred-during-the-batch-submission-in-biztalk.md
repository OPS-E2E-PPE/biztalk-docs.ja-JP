---
title: バッチ処理オーケストレーションでバッチ送信中に永続化例外が発生しました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf6e832f-9d01-46e7-aaf5-2b402d509fac
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99cb8d0456152b5a4e3dc24d9f0d71eeb414eb80
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347023"
---
# <a name="a-persistence-exception-has-occurred-during-the-batch-submission-in-the-batching-orchestration"></a><span data-ttu-id="4753b-102">バッチ処理オーケストレーションでバッチ送信中に永続化例外が発生しました</span><span class="sxs-lookup"><span data-stu-id="4753b-102">A persistence exception has occurred during the batch submission in the batching Orchestration</span></span>
## <a name="details"></a><span data-ttu-id="4753b-103">詳細</span><span class="sxs-lookup"><span data-stu-id="4753b-103">Details</span></span>  
  
|                 |                                                                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="4753b-104">製品名</span><span class="sxs-lookup"><span data-stu-id="4753b-104">Product Name</span></span>   |                                                     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                     |
| <span data-ttu-id="4753b-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="4753b-105">Product Version</span></span> |                                                                 [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                 |
|    <span data-ttu-id="4753b-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4753b-106">Event ID</span></span>     |                                                                                             -                                                                                              |
|  <span data-ttu-id="4753b-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="4753b-107">Event Source</span></span>   |                                                   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="4753b-108">EDI</span><span class="sxs-lookup"><span data-stu-id="4753b-108">EDI</span></span>                                                   |
|    <span data-ttu-id="4753b-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="4753b-109">Component</span></span>    |                                                                                      <span data-ttu-id="4753b-110">バッチ処理エンジン</span><span class="sxs-lookup"><span data-stu-id="4753b-110">Batching Engine</span></span>                                                                                       |
|  <span data-ttu-id="4753b-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="4753b-111">Symbolic Name</span></span>  |                                                                                <span data-ttu-id="4753b-112">PersistenceExceptionOccured</span><span class="sxs-lookup"><span data-stu-id="4753b-112">PersistenceExceptionOccured</span></span>                                                                                 |
|  <span data-ttu-id="4753b-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="4753b-113">Message Text</span></span>   | <span data-ttu-id="4753b-114">バッチ処理オーケストレーションでバッチ送信中に永続化例外が発生しました。</span><span class="sxs-lookup"><span data-stu-id="4753b-114">A persistence exception has occured during the batch submission in the batching Orchestration.</span></span> <span data-ttu-id="4753b-115">バッチ Id = {0}、ErrorMessage ={1}します。</span><span class="sxs-lookup"><span data-stu-id="4753b-115">Batch Id = {0}, ErrorMessage = {1}.</span></span> <span data-ttu-id="4753b-116">送信ポート サブスクリプションを確認し、それらを修正してください。</span><span class="sxs-lookup"><span data-stu-id="4753b-116">Please check your send port subscriptions and fix them.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="4753b-117">説明</span><span class="sxs-lookup"><span data-stu-id="4753b-117">Explanation</span></span>  
 <span data-ttu-id="4753b-118">このエラー/警告/情報イベントは、BizTalk Server 送信できなかったこと、バッチ インターチェンジのインターチェンジをサブスクライブした送信ポートがないため、ことを示します。</span><span class="sxs-lookup"><span data-stu-id="4753b-118">This Error/Warning/Information event indicates that BizTalk Server could not send a batched interchange because no send port subscribed to the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4753b-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="4753b-119">User Action</span></span>  
 <span data-ttu-id="4753b-120">このエラーを解決するには、送信ポートには、次のフィルター プロパティを設定して、その送信ポートがバッチにはサブスクライブすることを確認します。EDI です。DestinationPartyName = \<PartyName\>、EDI です。BatchEncodingType = EDIFACT または X12、および EDI です。ToBeBatched = False。</span><span class="sxs-lookup"><span data-stu-id="4753b-120">To resolve this error, ensure that a send port subscribes to the batch by setting the following filter properties for the send port: EDI.DestinationPartyName = \<PartyName\>, EDI.BatchEncodingType = EDIFACT or X12, and EDI.ToBeBatched = False.</span></span>