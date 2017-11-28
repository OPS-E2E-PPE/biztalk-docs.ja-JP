---
title: "検証が失敗したバッチ要素が中断されています |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea5e19e8-4592-40f4-bffe-85ab27653fd5
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7022041d8d47e1bfa52eb7ef45764c17ed1a2d8d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-batch-element-is-being-suspended-as-it-failed-validation"></a><span data-ttu-id="cd037-102">検証に失敗したため、バッチ要素を中断しています</span><span class="sxs-lookup"><span data-stu-id="cd037-102">The batch element is being suspended as it failed validation</span></span>
## <a name="details"></a><span data-ttu-id="cd037-103">詳細</span><span class="sxs-lookup"><span data-stu-id="cd037-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cd037-104">製品名</span><span class="sxs-lookup"><span data-stu-id="cd037-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="cd037-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="cd037-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="cd037-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="cd037-106">Event ID</span></span>|-|  
|<span data-ttu-id="cd037-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="cd037-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="cd037-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="cd037-108"> EDI</span></span>|  
|<span data-ttu-id="cd037-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="cd037-109">Component</span></span>|<span data-ttu-id="cd037-110">バッチ処理エンジン</span><span class="sxs-lookup"><span data-stu-id="cd037-110">Batching Engine</span></span>|  
|<span data-ttu-id="cd037-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="cd037-111">Symbolic Name</span></span>|<span data-ttu-id="cd037-112">BatchElementSuspended</span><span class="sxs-lookup"><span data-stu-id="cd037-112">BatchElementSuspended</span></span>|  
|<span data-ttu-id="cd037-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="cd037-113">Message Text</span></span>|<span data-ttu-id="cd037-114">検証に失敗したため、バッチ要素を中断しています。</span><span class="sxs-lookup"><span data-stu-id="cd037-114">The batch element is being suspended as it failed validation.</span></span> <span data-ttu-id="cd037-115">エラー: {0}</span><span class="sxs-lookup"><span data-stu-id="cd037-115">The error is : {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cd037-116">説明</span><span class="sxs-lookup"><span data-stu-id="cd037-116">Explanation</span></span>  
 <span data-ttu-id="cd037-117">このエラー/警告/情報イベントは、トランザクション セットが、バッチ処理オーケストレーションによって実行された検証に失敗したため、バッチ処理オーケストレーションが、バッチ化されたインターチェンジにトランザクション セットを追加できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="cd037-117">This Error/Warning/Information event indicates that the batching orchestration could not add a transaction set to a batched interchange because the transaction set failed the validation performed by the batching orchestration.</span></span> <span data-ttu-id="cd037-118">インターチェンジは、検証に失敗したトランザクション セットなしで生成されます。</span><span class="sxs-lookup"><span data-stu-id="cd037-118">The interchange will be generated without the transaction set that failed validation.</span></span> <span data-ttu-id="cd037-119">バッチ処理オーケストレーションは EDI.BatchElementValidationFailure コンテキスト プロパティを "True" に設定します。</span><span class="sxs-lookup"><span data-stu-id="cd037-119">The batching orchestration sets the EDI.BatchElementValidationFailure context property to "True".</span></span> <span data-ttu-id="cd037-120">BatchSuspend オーケストレーションは、そのコンテキスト プロパティに基づいてメッセージを取得し、エラー情報を送信してから中断します。</span><span class="sxs-lookup"><span data-stu-id="cd037-120">The BatchSuspend orchestration picks up the message based upon that context property, posts error information, and then is suspended.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cd037-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="cd037-121">User Action</span></span>  
 <span data-ttu-id="cd037-122">このエラーを解決するには、エラー メッセージに示されているように、発生したエラーをトランザクション セットの送信者に示します。</span><span class="sxs-lookup"><span data-stu-id="cd037-122">To resolve this error, indicate to the sender of the transaction set what error occurred, as indicated in the error message.</span></span> <span data-ttu-id="cd037-123">送信者に対して、検証に失敗する理由となった問題を解決し、トランザクション セットを再送信するように依頼します。</span><span class="sxs-lookup"><span data-stu-id="cd037-123">Have the sender resolve the issue that caused it to fail validation, and then resend the transaction set.</span></span>