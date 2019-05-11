---
title: 検証に失敗したため、バッチ要素が中断されています |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea5e19e8-4592-40f4-bffe-85ab27653fd5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0198f6091b1d7dd6e4ade10260e8f8ffe5b59765
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298981"
---
# <a name="the-batch-element-is-being-suspended-as-it-failed-validation"></a><span data-ttu-id="2f341-102">検証に失敗したため、バッチ要素が中断されています</span><span class="sxs-lookup"><span data-stu-id="2f341-102">The batch element is being suspended as it failed validation</span></span>
## <a name="details"></a><span data-ttu-id="2f341-103">詳細</span><span class="sxs-lookup"><span data-stu-id="2f341-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="2f341-104">製品名</span><span class="sxs-lookup"><span data-stu-id="2f341-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="2f341-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="2f341-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="2f341-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="2f341-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="2f341-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="2f341-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="2f341-108">EDI</span><span class="sxs-lookup"><span data-stu-id="2f341-108">EDI</span></span> |
|    <span data-ttu-id="2f341-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2f341-109">Component</span></span>    |                                    <span data-ttu-id="2f341-110">バッチ処理エンジン</span><span class="sxs-lookup"><span data-stu-id="2f341-110">Batching Engine</span></span>                                     |
|  <span data-ttu-id="2f341-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="2f341-111">Symbolic Name</span></span>  |                                 <span data-ttu-id="2f341-112">BatchElementSuspended</span><span class="sxs-lookup"><span data-stu-id="2f341-112">BatchElementSuspended</span></span>                                  |
|  <span data-ttu-id="2f341-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="2f341-113">Message Text</span></span>   |    <span data-ttu-id="2f341-114">検証に失敗したため、バッチ要素を中断されています。</span><span class="sxs-lookup"><span data-stu-id="2f341-114">The batch element is being suspended as it failed validation.</span></span> <span data-ttu-id="2f341-115">エラーです。 {0}</span><span class="sxs-lookup"><span data-stu-id="2f341-115">The error is : {0}</span></span>    |
  
## <a name="explanation"></a><span data-ttu-id="2f341-116">説明</span><span class="sxs-lookup"><span data-stu-id="2f341-116">Explanation</span></span>  
 <span data-ttu-id="2f341-117">このエラー/警告/情報イベントは、バッチ処理オーケストレーションが、トランザクション セットをバッチ インターチェンジをトランザクション セットには、バッチ処理オーケストレーションによって行われる検証が失敗したために追加できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="2f341-117">This Error/Warning/Information event indicates that the batching orchestration could not add a transaction set to a batched interchange because the transaction set failed the validation performed by the batching orchestration.</span></span> <span data-ttu-id="2f341-118">検証に失敗したトランザクションが設定されていないインターチェンジが生成されます。</span><span class="sxs-lookup"><span data-stu-id="2f341-118">The interchange will be generated without the transaction set that failed validation.</span></span> <span data-ttu-id="2f341-119">バッチ処理オーケストレーションは、EDI を設定します。"True"に BatchElementValidationFailure コンテキスト プロパティです。</span><span class="sxs-lookup"><span data-stu-id="2f341-119">The batching orchestration sets the EDI.BatchElementValidationFailure context property to "True".</span></span> <span data-ttu-id="2f341-120">BatchSuspend オーケストレーションはそのコンテキスト プロパティに基づいてメッセージを取得するには、エラー情報を送信しは中断されます。</span><span class="sxs-lookup"><span data-stu-id="2f341-120">The BatchSuspend orchestration picks up the message based upon that context property, posts error information, and then is suspended.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2f341-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="2f341-121">User Action</span></span>  
 <span data-ttu-id="2f341-122">このエラーを解決するを示す、トランザクション セットの送信者にどのようなエラーが発生したエラー メッセージに記載されています。</span><span class="sxs-lookup"><span data-stu-id="2f341-122">To resolve this error, indicate to the sender of the transaction set what error occurred, as indicated in the error message.</span></span> <span data-ttu-id="2f341-123">検証が失敗する原因となった問題を解決して、トランザクション セットを再送信し、送信者に依頼します。</span><span class="sxs-lookup"><span data-stu-id="2f341-123">Have the sender resolve the issue that caused it to fail validation, and then resend the transaction set.</span></span>