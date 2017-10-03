---
title: "不足しているか、無効または重複したトランザクション セット識別子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8580aab2-9fa4-43fb-b643-10621926591e
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75251d0210be4ed34a74ba0f3f5cadf84d9941b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="missing-or-invalid-or-duplicate-transaction-set-identifier"></a><span data-ttu-id="6a71a-102">トランザクション セット識別子が見つからないか、無効か、重複しています</span><span class="sxs-lookup"><span data-stu-id="6a71a-102">Missing or invalid or duplicate Transaction set identifier</span></span>
## <a name="details"></a><span data-ttu-id="6a71a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="6a71a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6a71a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="6a71a-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="6a71a-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="6a71a-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="6a71a-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="6a71a-106">Event ID</span></span>|-|  
|<span data-ttu-id="6a71a-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="6a71a-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="6a71a-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="6a71a-108"> EDI</span></span>|  
|<span data-ttu-id="6a71a-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6a71a-109">Component</span></span>|<span data-ttu-id="6a71a-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="6a71a-110">EDI Engine</span></span>|  
|<span data-ttu-id="6a71a-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="6a71a-111">Symbolic Name</span></span>|<span data-ttu-id="6a71a-112">X12TsMissingOrInvalidTsIdentiferDescription2</span><span class="sxs-lookup"><span data-stu-id="6a71a-112">X12TsMissingOrInvalidTsIdentiferDescription2</span></span>|  
|<span data-ttu-id="6a71a-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="6a71a-113">Message Text</span></span>|<span data-ttu-id="6a71a-114">重複するトランザクション セット識別子 '{0}' が見つからないか無効です</span><span class="sxs-lookup"><span data-stu-id="6a71a-114">Missing or invalid or duplicate Transaction set identifier '{0}'</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6a71a-115">説明</span><span class="sxs-lookup"><span data-stu-id="6a71a-115">Explanation</span></span>  
 <span data-ttu-id="6a71a-116">このエラー/警告/情報イベントは、トランザクション セット ID の値 (ST01 フィールド) がないか、重複していたか、値が無効であったため、受信または送信パイプラインで X12 インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="6a71a-116">This Error/Warning/Information event indicates that the receive or send pipeline could not process the X12 interchange because the value of the transaction set identifier (in the ST01 field) was missing, a duplicate, or had an invalid value.</span></span> <span data-ttu-id="6a71a-117">このエラーが発生する場合は、ドキュメント スキーマに ST ヘッダーと SE トレーラーがない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6a71a-117">This can occur if the document schema does not have an ST header and an SE trailer.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6a71a-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="6a71a-118">User Action</span></span>  
 <span data-ttu-id="6a71a-119">このエラーを解決するには、インターチェンジに ST01 フィールドの値があり、スキーマに ST ヘッダーと SE トレーラーのエントリがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6a71a-119">To resolve this error, make sure that the interchange has a value for the ST01 field and that the schema has an entry for the ST header and SE trailer.</span></span> <span data-ttu-id="6a71a-120">ST01 の値が、3 桁の有効なドキュメント型の識別子であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6a71a-120">Verify that the value of ST01 is a valid three-digit document-type designator.</span></span> <span data-ttu-id="6a71a-121">ST01 フィールドが、別のトランザクション セットの ST01 フィールドと重複していないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="6a71a-121">Verify that the ST01 field is not a duplicate with the ST01 field of another transaction set.</span></span>