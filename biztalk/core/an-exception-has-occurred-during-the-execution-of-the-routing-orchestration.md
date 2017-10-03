---
title: "ルーティング オーケストレーションの実行中に例外が発生しました |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68ec8921-ba05-496e-8dcc-fd8994fcb8b7
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e865ec091330a863cb2bab90bbafd9b891edb05
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="an-exception-has-occurred-during-the-execution-of-the-routing-orchestration"></a><span data-ttu-id="89916-102">ルーティング オーケストレーションの実行中に例外が発生しました</span><span class="sxs-lookup"><span data-stu-id="89916-102">An exception has occurred during the execution of the routing orchestration</span></span>
## <a name="details"></a><span data-ttu-id="89916-103">詳細</span><span class="sxs-lookup"><span data-stu-id="89916-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="89916-104">製品名</span><span class="sxs-lookup"><span data-stu-id="89916-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="89916-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="89916-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="89916-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="89916-106">Event ID</span></span>|-|  
|<span data-ttu-id="89916-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="89916-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="89916-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="89916-108"> EDI</span></span>|  
|<span data-ttu-id="89916-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="89916-109">Component</span></span>|<span data-ttu-id="89916-110">バッチ処理エンジン</span><span class="sxs-lookup"><span data-stu-id="89916-110">Batching Engine</span></span>|  
|<span data-ttu-id="89916-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="89916-111">Symbolic Name</span></span>|<span data-ttu-id="89916-112">ExceptionOccuredDuringRouting</span><span class="sxs-lookup"><span data-stu-id="89916-112">ExceptionOccuredDuringRouting</span></span>|  
|<span data-ttu-id="89916-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="89916-113">Message Text</span></span>|<span data-ttu-id="89916-114">ルーティング オーケストレーションの実行中に例外が発生しました。</span><span class="sxs-lookup"><span data-stu-id="89916-114">An exception has occured during the execution of the routing Orchestration.</span></span> <span data-ttu-id="89916-115">ErrorMessage = {0}</span><span class="sxs-lookup"><span data-stu-id="89916-115">ErrorMessage = {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="89916-116">説明</span><span class="sxs-lookup"><span data-stu-id="89916-116">Explanation</span></span>  
 <span data-ttu-id="89916-117">このエラー/警告/情報イベントは、ErrorMessage フィールドに示されたエラー状態のために、ルーティング オーケストレーションが XML バッチ要素の各コピーを正しく処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="89916-117">This Error/Warning/Information event indicates that the routing orchestration could not process each copy of the XML batch element correctly because of the error condition indicated in ErrorMessage field.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="89916-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="89916-118">User Action</span></span>  
 <span data-ttu-id="89916-119">このエラーを解決するには、ErrorMessage フィールドからエラーの状態を特定し、エラーを解決してメッセージを再送信します。</span><span class="sxs-lookup"><span data-stu-id="89916-119">To resolve this error, determine what the error condition is from the ErrorMessage field, resolve the error, and resubmit the message.</span></span>