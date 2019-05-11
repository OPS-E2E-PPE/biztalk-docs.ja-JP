---
title: Database が失敗しましたからバッチの説明の読み取り |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f959aa35-d957-45b0-bfac-1134b5087d0c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca3eed2b26b01840104ba1219dd6acde7e2b0ae2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398287"
---
# <a name="reading-batch-descriptions-from-database-failed"></a><span data-ttu-id="5c7fb-102">データベースからバッチの説明の読み取りに失敗しました</span><span class="sxs-lookup"><span data-stu-id="5c7fb-102">Reading Batch Descriptions from database failed</span></span>
## <a name="details"></a><span data-ttu-id="5c7fb-103">詳細</span><span class="sxs-lookup"><span data-stu-id="5c7fb-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="5c7fb-104">製品名</span><span class="sxs-lookup"><span data-stu-id="5c7fb-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="5c7fb-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="5c7fb-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="5c7fb-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="5c7fb-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="5c7fb-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="5c7fb-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="5c7fb-108">EDI</span><span class="sxs-lookup"><span data-stu-id="5c7fb-108">EDI</span></span> |
|    <span data-ttu-id="5c7fb-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5c7fb-109">Component</span></span>    |                                       <span data-ttu-id="5c7fb-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="5c7fb-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="5c7fb-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="5c7fb-111">Symbolic Name</span></span>  |                                 <span data-ttu-id="5c7fb-112">LoadBatchFiltersFailed</span><span class="sxs-lookup"><span data-stu-id="5c7fb-112">LoadBatchFiltersFailed</span></span>                                 |
|  <span data-ttu-id="5c7fb-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="5c7fb-113">Message Text</span></span>   |     <span data-ttu-id="5c7fb-114">バッチの説明、データベースからの読み取りが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="5c7fb-114">Reading BatchDescriptions from database failed.</span></span> <span data-ttu-id="5c7fb-115">エラー:{0}します。</span><span class="sxs-lookup"><span data-stu-id="5c7fb-115">Error: {0}.</span></span> <span data-ttu-id="5c7fb-116">スタック トレース:{1}します。</span><span class="sxs-lookup"><span data-stu-id="5c7fb-116">Stack Trace: {1}.</span></span>      |
  
## <a name="explanation"></a><span data-ttu-id="5c7fb-117">説明</span><span class="sxs-lookup"><span data-stu-id="5c7fb-117">Explanation</span></span>  
 <span data-ttu-id="5c7fb-118">このエラー/警告/情報イベントは、BizTalk Server が構成されているバッチで受信メッセージのコンテキスト プロパティを比較する指定されたフィルターを読み込むことを示します。</span><span class="sxs-lookup"><span data-stu-id="5c7fb-118">This Error/Warning/Information event indicates BizTalk Server was unable to load the filters specified for the configured batches to compare context properties of incoming messages.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5c7fb-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="5c7fb-119">User Action</span></span>  
 <span data-ttu-id="5c7fb-120">このエラーを解決するのには、管理データベースが稼働して、接続できることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5c7fb-120">To resolve this error, ensure that the Management database is up and can be connected.</span></span>