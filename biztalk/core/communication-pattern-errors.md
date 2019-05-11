---
title: 通信方式エラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 06656073-9bae-4d6f-98ae-2714a72ee79c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20a878f34b1e78509bec85fedbc2cf115a7140ad
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357040"
---
# <a name="communication-pattern-errors"></a><span data-ttu-id="147ba-102">通信方式エラー</span><span class="sxs-lookup"><span data-stu-id="147ba-102">Communication Pattern Errors</span></span>
<span data-ttu-id="147ba-103">診断および WCF の通信方式エラーを解決するための情報です。</span><span class="sxs-lookup"><span data-stu-id="147ba-103">Information for diagnosing and resolving WCF Communication Pattern errors.</span></span>  

## <a name="fault-messages-are-not-supported-on-one-way-ports"></a><span data-ttu-id="147ba-104">エラー メッセージは一方向のポートではサポートされていません</span><span class="sxs-lookup"><span data-stu-id="147ba-104">Fault messages are not supported on one-way ports</span></span>
  
|                 |                                                       <span data-ttu-id="147ba-105">エラーの詳細</span><span class="sxs-lookup"><span data-stu-id="147ba-105">Error details</span></span>                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="147ba-106">製品名</span><span class="sxs-lookup"><span data-stu-id="147ba-106">Product Name</span></span>   |                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                     |
| <span data-ttu-id="147ba-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="147ba-107">Product Version</span></span> |                                [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                 |
|    <span data-ttu-id="147ba-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="147ba-108">Event ID</span></span>     |                                                             <span data-ttu-id="147ba-109">0</span><span class="sxs-lookup"><span data-stu-id="147ba-109">0</span></span>                                                             |
|  <span data-ttu-id="147ba-110">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="147ba-110">Event Source</span></span>   |                                                             <span data-ttu-id="147ba-111">0</span><span class="sxs-lookup"><span data-stu-id="147ba-111">0</span></span>                                                             |
|    <span data-ttu-id="147ba-112">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="147ba-112">Component</span></span>    |                                                             <span data-ttu-id="147ba-113">0</span><span class="sxs-lookup"><span data-stu-id="147ba-113">0</span></span>                                                             |
|  <span data-ttu-id="147ba-114">シンボル名</span><span class="sxs-lookup"><span data-stu-id="147ba-114">Symbolic Name</span></span>  |                                                             <span data-ttu-id="147ba-115">0</span><span class="sxs-lookup"><span data-stu-id="147ba-115">0</span></span>                                                             |
|  <span data-ttu-id="147ba-116">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="147ba-116">Message Text</span></span>   | <span data-ttu-id="147ba-117">エラー メッセージは一方向のポートではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="147ba-117">Fault messages are not supported on one-way ports.</span></span> <span data-ttu-id="147ba-118">サービスの説明を修正"{0}「ポートの種類」{1}"し、ウィザードを再実行</span><span class="sxs-lookup"><span data-stu-id="147ba-118">Correct service description "{0}" port type "{1}" and rerun the wizard</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="147ba-119">説明</span><span class="sxs-lookup"><span data-stu-id="147ba-119">Explanation</span></span>  
 <span data-ttu-id="147ba-120">このエラーは、使用するサービスは、一方向サービスと指定したエラーを示します。</span><span class="sxs-lookup"><span data-stu-id="147ba-120">This error indicates the service trying to be consumed is a one-way service and has the fault specified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="147ba-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="147ba-121">User Action</span></span>  
 <span data-ttu-id="147ba-122">要求 - 応答の一方向通信パターンを切り替えることで、サービスを修正します。</span><span class="sxs-lookup"><span data-stu-id="147ba-122">Correct the service by switching the communication pattern from one-way to request-response.</span></span> <span data-ttu-id="147ba-123">または、コード障害を削除します。</span><span class="sxs-lookup"><span data-stu-id="147ba-123">Or remove the fault in the code.</span></span>
 
 