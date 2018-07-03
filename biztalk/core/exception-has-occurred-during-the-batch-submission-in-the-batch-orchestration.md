---
title: バッチ処理オーケストレーションでバッチ送信中に例外が発生しました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c58b2fa9-d036-4e09-a0f8-77a2f983881a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 838e9aff43dd260fd4af8e46ca88782c2389dfc7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971531"
---
# <a name="an-exception-has-occurred-during-the-batch-submission-in-the-batching-orchestration"></a><span data-ttu-id="719e3-102">バッチ処理オーケストレーションでのバッチ送信中に例外が発生しました</span><span class="sxs-lookup"><span data-stu-id="719e3-102">An exception has occurred during the batch submission in the batching orchestration</span></span>
## <a name="details"></a><span data-ttu-id="719e3-103">詳細</span><span class="sxs-lookup"><span data-stu-id="719e3-103">Details</span></span>  
  
|                 |                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="719e3-104">製品名</span><span class="sxs-lookup"><span data-stu-id="719e3-104">Product Name</span></span>   |                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                  |
| <span data-ttu-id="719e3-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="719e3-105">Product Version</span></span> |                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                              |
|    <span data-ttu-id="719e3-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="719e3-106">Event ID</span></span>     |                                                          -                                                          |
|  <span data-ttu-id="719e3-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="719e3-107">Event Source</span></span>   |               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="719e3-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="719e3-108"> EDI</span></span>                |
|    <span data-ttu-id="719e3-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="719e3-109">Component</span></span>    |                                                   <span data-ttu-id="719e3-110">バッチ処理エンジン</span><span class="sxs-lookup"><span data-stu-id="719e3-110">Batching Engine</span></span>                                                   |
|  <span data-ttu-id="719e3-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="719e3-111">Symbolic Name</span></span>  |                                                  <span data-ttu-id="719e3-112">ExceptionOccured</span><span class="sxs-lookup"><span data-stu-id="719e3-112">ExceptionOccured</span></span>                                                   |
|  <span data-ttu-id="719e3-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="719e3-113">Message Text</span></span>   | <span data-ttu-id="719e3-114">バッチ処理オーケストレーションでのバッチ送信中に例外が発生しました。</span><span class="sxs-lookup"><span data-stu-id="719e3-114">An exception has occured during the batch submission in the batching Orchestration.</span></span> <span data-ttu-id="719e3-115">バッチ Id = {0}、エラー メッセージ {1}</span><span class="sxs-lookup"><span data-stu-id="719e3-115">Batch Id= {0}, ErrorMessage {1}</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="719e3-116">説明</span><span class="sxs-lookup"><span data-stu-id="719e3-116">Explanation</span></span>  
 <span data-ttu-id="719e3-117">このエラー/警告/情報イベントは、ErrorMessage フィールドに示されたエラー状態のために、バッチ処理オーケストレーションがバッチにバッチ要素を追加できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="719e3-117">This Error/Warning/Information event indicates that the batching orchestration could not add a batch element to a batch because of the error condition indicated in the ErrorMessage field.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="719e3-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="719e3-118">User Action</span></span>  
 <span data-ttu-id="719e3-119">このエラーを解決するには、ErrorMessage フィールドからエラーの状態を判断し、エラーを解決してメッセージを再送信します。</span><span class="sxs-lookup"><span data-stu-id="719e3-119">To resolve this error, determine what the error condition is from the ErrorMessage field, resolve the error, and then resubmit the message.</span></span>