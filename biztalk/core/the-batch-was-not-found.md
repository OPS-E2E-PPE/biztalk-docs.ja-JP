---
title: バッチが見つかりませんでした |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e967e1a-b87f-4c87-a157-a6f63ba96d78
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 564cacb8d1389f03404939a0c9c7f557b6fa7393
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298829"
---
# <a name="the-batch-was-not-found"></a><span data-ttu-id="98761-102">バッチが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="98761-102">The batch was not found</span></span>
## <a name="details"></a><span data-ttu-id="98761-103">詳細</span><span class="sxs-lookup"><span data-stu-id="98761-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="98761-104">製品名</span><span class="sxs-lookup"><span data-stu-id="98761-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="98761-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="98761-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="98761-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="98761-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="98761-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="98761-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="98761-108">EDI</span><span class="sxs-lookup"><span data-stu-id="98761-108">EDI</span></span> |
|    <span data-ttu-id="98761-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="98761-109">Component</span></span>    |                                       <span data-ttu-id="98761-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="98761-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="98761-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="98761-111">Symbolic Name</span></span>  |                                   <span data-ttu-id="98761-112">Err_BatchNotFound</span><span class="sxs-lookup"><span data-stu-id="98761-112">Err_BatchNotFound</span></span>                                    |
|  <span data-ttu-id="98761-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="98761-113">Message Text</span></span>   |                                <span data-ttu-id="98761-114">バッチが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="98761-114">The batch was not found.</span></span>                                |
  
## <a name="explanation"></a><span data-ttu-id="98761-115">説明</span><span class="sxs-lookup"><span data-stu-id="98761-115">Explanation</span></span>  
 <span data-ttu-id="98761-116">このエラー/警告/情報イベントは、バッチの開始/停止中、またはバッチ オーケストレーションがメッセージのバッチ処理を試行中に、BizTalk Server がバッチを見つけられなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="98761-116">This Error/Warning/Information event indicates BizTalk Server was unable to find a batch during the start/stop of a batch or while the Batching Orchestration was trying to batch a message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="98761-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="98761-117">User Action</span></span>  
 <span data-ttu-id="98761-118">このエラーを解決するには、各バッチが親アグリーメントの [アグリーメントのプロパティ] に存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="98761-118">To resolve this error, ensure that the respective batch is present in the Agreement properties of the containing Agreement.</span></span>