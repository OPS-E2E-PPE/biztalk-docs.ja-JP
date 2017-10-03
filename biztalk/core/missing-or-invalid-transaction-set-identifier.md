---
title: "存在しないか無効なトランザクション セット識別子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 282c8128-7d23-44e2-bf44-e90e52cb5fb1
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f23f44587abf67e608cff79150d9633f1707ff2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="missing-or-invalid-transaction-set-identifier"></a><span data-ttu-id="0a7fc-102">トランザクション セット識別子が見つからないか無効です</span><span class="sxs-lookup"><span data-stu-id="0a7fc-102">Missing or invalid Transaction set identifier</span></span>
## <a name="details"></a><span data-ttu-id="0a7fc-103">詳細</span><span class="sxs-lookup"><span data-stu-id="0a7fc-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0a7fc-104">製品名</span><span class="sxs-lookup"><span data-stu-id="0a7fc-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="0a7fc-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="0a7fc-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="0a7fc-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0a7fc-106">Event ID</span></span>|-|  
|<span data-ttu-id="0a7fc-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="0a7fc-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0a7fc-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="0a7fc-108"> EDI</span></span>|  
|<span data-ttu-id="0a7fc-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0a7fc-109">Component</span></span>|<span data-ttu-id="0a7fc-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="0a7fc-110">EDI Engine</span></span>|  
|<span data-ttu-id="0a7fc-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="0a7fc-111">Symbolic Name</span></span>|<span data-ttu-id="0a7fc-112">EfactTsMissingOrInvalidTsIdentiferDescription</span><span class="sxs-lookup"><span data-stu-id="0a7fc-112">EfactTsMissingOrInvalidTsIdentiferDescription</span></span>|  
|<span data-ttu-id="0a7fc-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="0a7fc-113">Message Text</span></span>|<span data-ttu-id="0a7fc-114">トランザクション セット識別子が見つからないか無効です</span><span class="sxs-lookup"><span data-stu-id="0a7fc-114">Missing or invalid Transaction set identifier</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0a7fc-115">説明</span><span class="sxs-lookup"><span data-stu-id="0a7fc-115">Explanation</span></span>  
 <span data-ttu-id="0a7fc-116">このエラー/警告/情報イベントは、トランザクション セット ID の値 (UNH2.1 フィールド) がないか、値が無効であったため、受信または送信パイプラインで EDIFACT インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="0a7fc-116">This Error/Warning/Information event indicates that the receive or send pipeline could not process the EDIFACT interchange because the value of the transaction set identifier (in the UNH2.1 field) was missing or had an invalid value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0a7fc-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="0a7fc-117">User Action</span></span>  
 <span data-ttu-id="0a7fc-118">このエラーを解決するには、インターチェンジの UNH2.1 フィールドに値が設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0a7fc-118">To resolve this error, make sure that the interchange has a value for the UNH2.1 field.</span></span> <span data-ttu-id="0a7fc-119">UNH2.1 の値が、ドキュメントの種類を示す有効な 1 桁から 6 桁の指定子であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0a7fc-119">Verify that the value of UNH2.1 is a valid one-digit to six-digit document-type designator.</span></span>