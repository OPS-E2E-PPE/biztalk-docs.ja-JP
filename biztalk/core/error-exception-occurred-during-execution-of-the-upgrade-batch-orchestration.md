---
title: "アップグレード バッチ オーケストレーションの実行中に例外が発生しました |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2221a498-98aa-43ab-bc4e-34dcbd92dcf0
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54cd439e180365010ec8881ce7165022dd7826d6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="an-exception-has-occurred-during-the-execution-of-the-upgrade-batch-orchestration"></a><span data-ttu-id="9d9f4-102">アップグレード バッチ オーケストレーションの実行中に例外が発生しました</span><span class="sxs-lookup"><span data-stu-id="9d9f4-102">An exception has occurred during the execution of the upgrade batch orchestration</span></span>
## <a name="details"></a><span data-ttu-id="9d9f4-103">詳細</span><span class="sxs-lookup"><span data-stu-id="9d9f4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9d9f4-104">製品名</span><span class="sxs-lookup"><span data-stu-id="9d9f4-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="9d9f4-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="9d9f4-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="9d9f4-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="9d9f4-106">Event ID</span></span>|-|  
|<span data-ttu-id="9d9f4-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="9d9f4-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]<span data-ttu-id="9d9f4-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="9d9f4-108"> EDI</span></span>|  
|<span data-ttu-id="9d9f4-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9d9f4-109">Component</span></span>|<span data-ttu-id="9d9f4-110">バッチ処理エンジン</span><span class="sxs-lookup"><span data-stu-id="9d9f4-110">Batching Engine</span></span>|  
|<span data-ttu-id="9d9f4-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="9d9f4-111">Symbolic Name</span></span>|<span data-ttu-id="9d9f4-112">ExceptionOccuredDuringUpgrade</span><span class="sxs-lookup"><span data-stu-id="9d9f4-112">ExceptionOccuredDuringUpgrade</span></span>|  
|<span data-ttu-id="9d9f4-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="9d9f4-113">Message Text</span></span>|<span data-ttu-id="9d9f4-114">アップグレード バッチ オーケストレーションの実行中に例外が発生しました。</span><span class="sxs-lookup"><span data-stu-id="9d9f4-114">An exception has occurred during the execution of the upgrade batch Orchestration.</span></span> <span data-ttu-id="9d9f4-115">ErrorMessage = {0}</span><span class="sxs-lookup"><span data-stu-id="9d9f4-115">ErrorMessage = {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9d9f4-116">説明</span><span class="sxs-lookup"><span data-stu-id="9d9f4-116">Explanation</span></span>  
 <span data-ttu-id="9d9f4-117">このエラー/警告/情報イベントは、ErrorMessage フィールドに示されたエラー状態のために、アップグレード バッチ オーケストレーションでメッセージを正しく処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="9d9f4-117">The Error/Warning/Information event indicates that the upgrade batch orchestration could not process the message correctly because of the error condition indicated in ErrorMessage field.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9d9f4-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="9d9f4-118">User Action</span></span>  
 <span data-ttu-id="9d9f4-119">このエラーを解決するには、ErrorMessage フィールドからエラーの状態を判断し、エラーを解決してメッセージを再送信します。</span><span class="sxs-lookup"><span data-stu-id="9d9f4-119">To resolve this error, determine what the error condition is from the ErrorMessage field, resolve the error, and then resubmit the message.</span></span>