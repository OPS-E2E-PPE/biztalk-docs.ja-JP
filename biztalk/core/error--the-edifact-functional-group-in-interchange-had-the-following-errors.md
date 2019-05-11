---
title: 解析中に発生したエラーです。 インターチェンジ内の Edifact 機能グループには、次のエラーが発生しました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77ca78b3-8a1f-4da5-9c15-524ab6802457
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2b818d745366b84b41f1b44399fd699ebd68987
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389007"
---
# <a name="error-encountered-during-parsing-the-edifact-functional-group-in-interchange-had-the-following-errors"></a><span data-ttu-id="6721a-103">解析中に発生したエラーです。</span><span class="sxs-lookup"><span data-stu-id="6721a-103">Error encountered during parsing.</span></span> <span data-ttu-id="6721a-104">インターチェンジ内の Edifact 機能グループには、次のエラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="6721a-104">The Edifact functional group in interchange had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="6721a-105">詳細</span><span class="sxs-lookup"><span data-stu-id="6721a-105">Details</span></span>  
  
|                 |                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="6721a-106">製品名</span><span class="sxs-lookup"><span data-stu-id="6721a-106">Product Name</span></span>   |                                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                               |
| <span data-ttu-id="6721a-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="6721a-107">Product Version</span></span> |                                                          [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                           |
|    <span data-ttu-id="6721a-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="6721a-108">Event ID</span></span>     |                                                                                       -                                                                                       |
|  <span data-ttu-id="6721a-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="6721a-109">Event Source</span></span>   |                                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="6721a-110">EDI</span><span class="sxs-lookup"><span data-stu-id="6721a-110">EDI</span></span>                                             |
|    <span data-ttu-id="6721a-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6721a-111">Component</span></span>    |                                                                                  <span data-ttu-id="6721a-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="6721a-112">EDI Engine</span></span>                                                                                   |
|  <span data-ttu-id="6721a-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="6721a-113">Symbolic Name</span></span>  |                                                                       <span data-ttu-id="6721a-114">EfactFunctionalGroupReceiveError</span><span class="sxs-lookup"><span data-stu-id="6721a-114">EfactFunctionalGroupReceiveError</span></span>                                                                        |
|  <span data-ttu-id="6721a-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="6721a-115">Message Text</span></span>   | <span data-ttu-id="6721a-116">解析中に発生したエラーです。</span><span class="sxs-lookup"><span data-stu-id="6721a-116">Error encountered during parsing.</span></span> <span data-ttu-id="6721a-117">Edifact 機能グループ id '{0}'、id を持つインターチェンジ内で'{1}'、送信者 id '{2}'、受信者 id'{3}' 次のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="6721a-117">The Edifact functional group with id '{0}', in interchange with id '{1}', with sender id '{2}', receiver id '{3}' had the following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="6721a-118">説明</span><span class="sxs-lookup"><span data-stu-id="6721a-118">Explanation</span></span>  
 <span data-ttu-id="6721a-119">このエラー/警告/情報イベントを示します、EDI 受信パイプラインでは、識別された機能グループで、示されたエラーのため、受信 EDIFACT インターチェンジの解析中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="6721a-119">This Error/Warning/Information event indicates that the EDI receive pipeline encountered an error when parsing an incoming EDIFACT interchange because of the stated errors with the identified functional group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6721a-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="6721a-120">User Action</span></span>  
 <span data-ttu-id="6721a-121">このエラーを解決するには、エラー メッセージの情報を使用してグループのエラーを特定し、製品のヘルプで問題の解決方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="6721a-121">To resolve this error, use the information in the error message to identify the error in the group and then determine the problem resolution in the product help.</span></span>