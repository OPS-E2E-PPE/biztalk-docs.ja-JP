---
title: "Database が失敗しましたからの読み取りバッチの説明 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f959aa35-d957-45b0-bfac-1134b5087d0c
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66a9049c9f3964b231d7c1370784bccd78fd0836
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="reading-batch-descriptions-from-database-failed"></a><span data-ttu-id="5b190-102">データベースからのバッチの説明の読み取りが失敗しました</span><span class="sxs-lookup"><span data-stu-id="5b190-102">Reading Batch Descriptions from database failed</span></span>
## <a name="details"></a><span data-ttu-id="5b190-103">詳細</span><span class="sxs-lookup"><span data-stu-id="5b190-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5b190-104">製品名</span><span class="sxs-lookup"><span data-stu-id="5b190-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="5b190-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="5b190-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="5b190-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="5b190-106">Event ID</span></span>|-|  
|<span data-ttu-id="5b190-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="5b190-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="5b190-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="5b190-108"> EDI</span></span>|  
|<span data-ttu-id="5b190-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5b190-109">Component</span></span>|<span data-ttu-id="5b190-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="5b190-110">EDI Engine</span></span>|  
|<span data-ttu-id="5b190-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="5b190-111">Symbolic Name</span></span>|<span data-ttu-id="5b190-112">LoadBatchFiltersFailed</span><span class="sxs-lookup"><span data-stu-id="5b190-112">LoadBatchFiltersFailed</span></span>|  
|<span data-ttu-id="5b190-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="5b190-113">Message Text</span></span>|<span data-ttu-id="5b190-114">データベースからのバッチの説明の読み取りが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="5b190-114">Reading BatchDescriptions from database failed.</span></span> <span data-ttu-id="5b190-115">エラー: {0}。</span><span class="sxs-lookup"><span data-stu-id="5b190-115">Error: {0}.</span></span> <span data-ttu-id="5b190-116">スタック トレース: {1} です。</span><span class="sxs-lookup"><span data-stu-id="5b190-116">Stack Trace: {1}.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5b190-117">説明</span><span class="sxs-lookup"><span data-stu-id="5b190-117">Explanation</span></span>  
 <span data-ttu-id="5b190-118">このエラー/警告/情報イベントは、BizTalk Server が、受信メッセージのコンテキスト プロパティを比較するために構成されたバッチ用に指定されたフィルターを読み込めなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="5b190-118">This Error/Warning/Information event indicates BizTalk Server was unable to load the filters specified for the configured batches to compare context properties of incoming messages.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5b190-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="5b190-119">User Action</span></span>  
 <span data-ttu-id="5b190-120">このエラーを解決するには、管理データベースが起動していて、接続できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5b190-120">To resolve this error, ensure that the Management database is up and can be connected.</span></span>