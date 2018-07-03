---
title: 解析中にエラーが発生しました。 Edifact インターチェンジで次のエラーが |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2fa8f9d5-5b7c-47c9-96d3-77be280b78e9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86d891abe7ca75dbbe9052f221970e235b390269
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988211"
---
# <a name="error-encountered-during-parsing-the-edifact-interchange-had-the-following-errors"></a><span data-ttu-id="d95ba-103">解析中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="d95ba-103">Error encountered during parsing.</span></span> <span data-ttu-id="d95ba-104">EDIFACT インターチェンジに次のエラーがありました</span><span class="sxs-lookup"><span data-stu-id="d95ba-104">The Edifact interchange had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="d95ba-105">詳細</span><span class="sxs-lookup"><span data-stu-id="d95ba-105">Details</span></span>  
  
|                 |                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="d95ba-106">製品名</span><span class="sxs-lookup"><span data-stu-id="d95ba-106">Product Name</span></span>   |                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                             |
| <span data-ttu-id="d95ba-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d95ba-107">Product Version</span></span> |                                         [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                         |
|    <span data-ttu-id="d95ba-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d95ba-108">Event ID</span></span>     |                                                                     -                                                                      |
|  <span data-ttu-id="d95ba-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d95ba-109">Event Source</span></span>   |                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="d95ba-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="d95ba-110"> EDI</span></span>                           |
|    <span data-ttu-id="d95ba-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d95ba-111">Component</span></span>    |                                                                 <span data-ttu-id="d95ba-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="d95ba-112">EDI Engine</span></span>                                                                 |
|  <span data-ttu-id="d95ba-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d95ba-113">Symbolic Name</span></span>  |                                                        <span data-ttu-id="d95ba-114">EfactInterchangeReceiveError</span><span class="sxs-lookup"><span data-stu-id="d95ba-114">EfactInterchangeReceiveError</span></span>                                                        |
|  <span data-ttu-id="d95ba-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d95ba-115">Message Text</span></span>   | <span data-ttu-id="d95ba-116">解析中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="d95ba-116">Error encountered during parsing.</span></span> <span data-ttu-id="d95ba-117">Edifact インターチェンジ id '{0}'、送信者 id'{1}'、受信者 id '{2}' 次のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="d95ba-117">The Edifact interchange with id '{0}', with sender id '{1}', receiver id '{2}' had the following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="d95ba-118">説明</span><span class="sxs-lookup"><span data-stu-id="d95ba-118">Explanation</span></span>  
 <span data-ttu-id="d95ba-119">このエラー/警告/情報イベントは、示されたエラーがインターチェンジにあるため、受信 EDIFACT インターチェンジを解析しているときに EDI 受信パイプラインでエラーが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="d95ba-119">This Error/Warning/Information event indicates that the EDI receive pipeline encountered an error when parsing an incoming EDIFACT interchange because of the stated errors in the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d95ba-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d95ba-120">User Action</span></span>  
 <span data-ttu-id="d95ba-121">このエラーを解決するには、エラー メッセージの情報を使用してインターチェンジのエラーを特定し、製品のヘルプで問題の解決方法を確認してください。</span><span class="sxs-lookup"><span data-stu-id="d95ba-121">To resolve this error, use the information in the error message to identify the error in the interchange and then determine the problem resolution in the product help.</span></span>