---
title: 解析中に発生したエラーです。 X12 インターチェンジの機能グループが、次のエラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2229c83-89bd-491f-9504-4afbf0084297
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ad6e795290ad6020d403eb1d1e5492633e4ed97
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348556"
---
# <a name="error-encountered-during-parsing-the-x12-functional-group-in-the-interchange-had-the-following-errors"></a><span data-ttu-id="58f46-103">解析中に発生したエラーです。</span><span class="sxs-lookup"><span data-stu-id="58f46-103">Error encountered during parsing.</span></span> <span data-ttu-id="58f46-104">X12 インターチェンジの機能グループには、次のエラーがありました</span><span class="sxs-lookup"><span data-stu-id="58f46-104">The X12 functional group in the interchange had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="58f46-105">詳細</span><span class="sxs-lookup"><span data-stu-id="58f46-105">Details</span></span>  
  
|                 |                                                                                                                                                                           |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="58f46-106">製品名</span><span class="sxs-lookup"><span data-stu-id="58f46-106">Product Name</span></span>   |                                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                             |
| <span data-ttu-id="58f46-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="58f46-107">Product Version</span></span> |                                                        [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                         |
|    <span data-ttu-id="58f46-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="58f46-108">Event ID</span></span>     |                                                                                     -                                                                                     |
|  <span data-ttu-id="58f46-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="58f46-109">Event Source</span></span>   |                                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="58f46-110">EDI</span><span class="sxs-lookup"><span data-stu-id="58f46-110">EDI</span></span>                                           |
|    <span data-ttu-id="58f46-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="58f46-111">Component</span></span>    |                                                                                <span data-ttu-id="58f46-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="58f46-112">EDI Engine</span></span>                                                                                 |
|  <span data-ttu-id="58f46-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="58f46-113">Symbolic Name</span></span>  |                                                                      <span data-ttu-id="58f46-114">X12FunctionalGroupReceiveError</span><span class="sxs-lookup"><span data-stu-id="58f46-114">X12FunctionalGroupReceiveError</span></span>                                                                       |
|  <span data-ttu-id="58f46-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="58f46-115">Message Text</span></span>   | <span data-ttu-id="58f46-116">解析中に発生したエラーです。</span><span class="sxs-lookup"><span data-stu-id="58f46-116">Error encountered during parsing.</span></span> <span data-ttu-id="58f46-117">X12 機能グループ id '{0}'、id を持つインターチェンジ内で'{1}'、送信者 id '{2}'、受信者 id'{3}' 次のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="58f46-117">The X12 functional group with id '{0}', in interchange with id '{1}', with sender id '{2}', receiver id '{3}' had the following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="58f46-118">説明</span><span class="sxs-lookup"><span data-stu-id="58f46-118">Explanation</span></span>  
 <span data-ttu-id="58f46-119">このエラー/警告/情報イベントは、EDI が受信することを示しますパイプライン、受信 X12 の解析中にエラーが発生しましたインターチェンジで識別された機能グループ、示されたエラーが原因です。</span><span class="sxs-lookup"><span data-stu-id="58f46-119">This Error/Warning/Information event indicates that the EDI receive pipeline encountered an error when parsing an incoming X12 interchange because of the stated errors with the identified functional group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="58f46-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="58f46-120">User Action</span></span>  
 <span data-ttu-id="58f46-121">このエラーを解決するには、エラー メッセージの情報を使用してグループのエラーを特定し、製品のヘルプで問題の解決方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="58f46-121">To resolve this error, use the information in the error message to identify the error in the group and then determine the problem resolution in the product help.</span></span>