---
title: 解析中に発生したエラーです。 Edifact インターチェンジ、グループが含まれていませんでしたが、次のエラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d6b324fd-f365-41b9-81aa-b6c5c5d3f673
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ace43a641e08265852212d25750977ba5f95398c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350194"
---
# <a name="error-encountered-during-parsing-the-edifact-interchange-which-did-not-contain-a-group-had-the-following-errors"></a><span data-ttu-id="e6af2-103">解析中に発生したエラーです。</span><span class="sxs-lookup"><span data-stu-id="e6af2-103">Error encountered during parsing.</span></span> <span data-ttu-id="e6af2-104">グループを含まない Edifact インターチェンジには、次のエラーがありました</span><span class="sxs-lookup"><span data-stu-id="e6af2-104">The Edifact interchange which did not contain a group had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="e6af2-105">詳細</span><span class="sxs-lookup"><span data-stu-id="e6af2-105">Details</span></span>  
  
|                 |                                                                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="e6af2-106">製品名</span><span class="sxs-lookup"><span data-stu-id="e6af2-106">Product Name</span></span>   |                                                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                   |
| <span data-ttu-id="e6af2-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="e6af2-107">Product Version</span></span> |                                                              [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                               |
|    <span data-ttu-id="e6af2-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e6af2-108">Event ID</span></span>     |                                                                                           -                                                                                           |
|  <span data-ttu-id="e6af2-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="e6af2-109">Event Source</span></span>   |                                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="e6af2-110">EDI</span><span class="sxs-lookup"><span data-stu-id="e6af2-110">EDI</span></span>                                                 |
|    <span data-ttu-id="e6af2-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e6af2-111">Component</span></span>    |                                                                                      <span data-ttu-id="e6af2-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="e6af2-112">EDI Engine</span></span>                                                                                       |
|  <span data-ttu-id="e6af2-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="e6af2-113">Symbolic Name</span></span>  |                                                                     <span data-ttu-id="e6af2-114">EfactFunctionalGroupReceiveErrorWithoutGroup</span><span class="sxs-lookup"><span data-stu-id="e6af2-114">EfactFunctionalGroupReceiveErrorWithoutGroup</span></span>                                                                      |
|  <span data-ttu-id="e6af2-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="e6af2-115">Message Text</span></span>   | <span data-ttu-id="e6af2-116">解析中に発生したエラーです。</span><span class="sxs-lookup"><span data-stu-id="e6af2-116">Error encountered during parsing.</span></span> <span data-ttu-id="e6af2-117">Edifact インターチェンジのインターチェンジ id を持つ、グループを含まない '{0}'、送信者 id'{1}'、受信者 id '{2}' 次のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="e6af2-117">The Edifact interchange which did not contain a group, with interchange id '{0}', with sender id '{1}', receiver id '{2}' had the following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="e6af2-118">説明</span><span class="sxs-lookup"><span data-stu-id="e6af2-118">Explanation</span></span>  
 <span data-ttu-id="e6af2-119">このエラー/警告/情報イベントを示します、EDI 受信パイプラインでは、示されたエラーのため、グループを含まない受信 EDIFACT インターチェンジの解析中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="e6af2-119">This Error/Warning/Information event indicates that the EDI receive pipeline encountered an error when parsing an incoming EDIFACT interchange that did not contain a group because of the stated errors.</span></span> <span data-ttu-id="e6af2-120">グループは、EDIFACT インターチェンジで省略可能なことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e6af2-120">Note that groups are optional in EDIFACT interchanges.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e6af2-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="e6af2-121">User Action</span></span>  
 <span data-ttu-id="e6af2-122">このエラーを解決するには、エラー メッセージの情報を使用してエラーを特定し、製品のヘルプで問題の解決方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="e6af2-122">To resolve this error, use the information in the error message to identify the error and then determine the problem resolution in the product help.</span></span>