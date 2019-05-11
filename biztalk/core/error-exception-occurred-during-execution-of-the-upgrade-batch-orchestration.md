---
title: アップグレード バッチ オーケストレーションの実行中に例外が発生しました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2221a498-98aa-43ab-bc4e-34dcbd92dcf0
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df73d4fa4d8d59caed5c8e8f34e52d2b60d4c7cf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348433"
---
# <a name="an-exception-has-occurred-during-the-execution-of-the-upgrade-batch-orchestration"></a><span data-ttu-id="0d821-102">アップグレード バッチ オーケストレーションの実行中に例外が発生しました</span><span class="sxs-lookup"><span data-stu-id="0d821-102">An exception has occurred during the execution of the upgrade batch orchestration</span></span>
## <a name="details"></a><span data-ttu-id="0d821-103">詳細</span><span class="sxs-lookup"><span data-stu-id="0d821-103">Details</span></span>  
  
|                 |                                                                                                       |
|-----------------|-------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="0d821-104">製品名</span><span class="sxs-lookup"><span data-stu-id="0d821-104">Product Name</span></span>   |          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]           |
| <span data-ttu-id="0d821-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="0d821-105">Product Version</span></span> |                      [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                       |
|    <span data-ttu-id="0d821-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0d821-106">Event ID</span></span>     |                                                   -                                                   |
|  <span data-ttu-id="0d821-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="0d821-107">Event Source</span></span>   |                                          <span data-ttu-id="0d821-108">BizTalk Server EDI</span><span class="sxs-lookup"><span data-stu-id="0d821-108">BizTalk Server EDI</span></span>                                           |
|    <span data-ttu-id="0d821-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0d821-109">Component</span></span>    |                                            <span data-ttu-id="0d821-110">バッチ処理エンジン</span><span class="sxs-lookup"><span data-stu-id="0d821-110">Batching Engine</span></span>                                            |
|  <span data-ttu-id="0d821-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="0d821-111">Symbolic Name</span></span>  |                                     <span data-ttu-id="0d821-112">ExceptionOccuredDuringUpgrade</span><span class="sxs-lookup"><span data-stu-id="0d821-112">ExceptionOccuredDuringUpgrade</span></span>                                     |
|  <span data-ttu-id="0d821-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="0d821-113">Message Text</span></span>   | <span data-ttu-id="0d821-114">アップグレード バッチ オーケストレーションの実行中に例外が発生しました。</span><span class="sxs-lookup"><span data-stu-id="0d821-114">An exception has occurred during the execution of the upgrade batch Orchestration.</span></span> <span data-ttu-id="0d821-115">ErrorMessage = {0}</span><span class="sxs-lookup"><span data-stu-id="0d821-115">ErrorMessage = {0}</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="0d821-116">説明</span><span class="sxs-lookup"><span data-stu-id="0d821-116">Explanation</span></span>  
 <span data-ttu-id="0d821-117">このエラー/警告/情報イベントは、ErrorMessage フィールドに示されたエラー状態のために、アップグレード バッチ オーケストレーションでメッセージを正しく処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="0d821-117">The Error/Warning/Information event indicates that the upgrade batch orchestration could not process the message correctly because of the error condition indicated in ErrorMessage field.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0d821-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="0d821-118">User Action</span></span>  
 <span data-ttu-id="0d821-119">このエラーを解決するには、ErrorMessage フィールドからエラーの状態を判断し、エラーを解決してメッセージを再送信します。</span><span class="sxs-lookup"><span data-stu-id="0d821-119">To resolve this error, determine what the error condition is from the ErrorMessage field, resolve the error, and then resubmit the message.</span></span>