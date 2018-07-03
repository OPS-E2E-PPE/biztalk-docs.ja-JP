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
ms.openlocfilehash: fab810e4cfadc77c8fafe34b5cb78aaa417dfe5c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015067"
---
# <a name="the-batch-was-not-found"></a><span data-ttu-id="637cf-102">バッチが見つかりませんでした</span><span class="sxs-lookup"><span data-stu-id="637cf-102">The batch was not found</span></span>
## <a name="details"></a><span data-ttu-id="637cf-103">詳細</span><span class="sxs-lookup"><span data-stu-id="637cf-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="637cf-104">製品名</span><span class="sxs-lookup"><span data-stu-id="637cf-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="637cf-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="637cf-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="637cf-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="637cf-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="637cf-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="637cf-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="637cf-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="637cf-108"> EDI</span></span> |
|    <span data-ttu-id="637cf-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="637cf-109">Component</span></span>    |                                       <span data-ttu-id="637cf-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="637cf-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="637cf-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="637cf-111">Symbolic Name</span></span>  |                                   <span data-ttu-id="637cf-112">Err_BatchNotFound</span><span class="sxs-lookup"><span data-stu-id="637cf-112">Err_BatchNotFound</span></span>                                    |
|  <span data-ttu-id="637cf-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="637cf-113">Message Text</span></span>   |                                <span data-ttu-id="637cf-114">バッチが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="637cf-114">The batch was not found.</span></span>                                |
  
## <a name="explanation"></a><span data-ttu-id="637cf-115">説明</span><span class="sxs-lookup"><span data-stu-id="637cf-115">Explanation</span></span>  
 <span data-ttu-id="637cf-116">このエラー/警告/情報イベントは、バッチの開始/停止中、またはバッチ オーケストレーションがメッセージのバッチ処理を試行中に、BizTalk Server がバッチを見つけられなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="637cf-116">This Error/Warning/Information event indicates BizTalk Server was unable to find a batch during the start/stop of a batch or while the Batching Orchestration was trying to batch a message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="637cf-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="637cf-117">User Action</span></span>  
 <span data-ttu-id="637cf-118">このエラーを解決するには、各バッチが親アグリーメントの [アグリーメントのプロパティ] に存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="637cf-118">To resolve this error, ensure that the respective batch is present in the Agreement properties of the containing Agreement.</span></span>