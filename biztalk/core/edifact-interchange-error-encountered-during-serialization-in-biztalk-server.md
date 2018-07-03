---
title: シリアル化中にエラーが発生しました。 Edifact インターチェンジで次のエラーが |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ebc933ac-161a-41e5-b67d-9f15e569d5c9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb97be1be3c623673d2429a20598c748a8d73de7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000827"
---
# <a name="error-encountered-during-serialization-the-edifact-interchange-had-the-following-errors"></a><span data-ttu-id="29743-103">シリアル化中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="29743-103">Error encountered during serialization.</span></span> <span data-ttu-id="29743-104">EDIFACT インターチェンジに次のエラーがありました</span><span class="sxs-lookup"><span data-stu-id="29743-104">The Edifact interchange had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="29743-105">詳細</span><span class="sxs-lookup"><span data-stu-id="29743-105">Details</span></span>  
  
|                 |                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="29743-106">製品名</span><span class="sxs-lookup"><span data-stu-id="29743-106">Product Name</span></span>   |                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                |
| <span data-ttu-id="29743-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="29743-107">Product Version</span></span> |                                            [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                            |
|    <span data-ttu-id="29743-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="29743-108">Event ID</span></span>     |                                                                        -                                                                         |
|  <span data-ttu-id="29743-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="29743-109">Event Source</span></span>   |                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="29743-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="29743-110"> EDI</span></span>                              |
|    <span data-ttu-id="29743-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="29743-111">Component</span></span>    |                                                                    <span data-ttu-id="29743-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="29743-112">EDI Engine</span></span>                                                                    |
|  <span data-ttu-id="29743-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="29743-113">Symbolic Name</span></span>  |                                                            <span data-ttu-id="29743-114">EfactInterchangeSendError</span><span class="sxs-lookup"><span data-stu-id="29743-114">EfactInterchangeSendError</span></span>                                                             |
|  <span data-ttu-id="29743-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="29743-115">Message Text</span></span>   | <span data-ttu-id="29743-116">シリアル化中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="29743-116">Error encountered during serialization.</span></span> <span data-ttu-id="29743-117">Edifact インターチェンジ id '{0}'、送信者 id'{1}'、受信者 id '{2}' 次のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="29743-117">The Edifact interchange with id '{0}', with sender id '{1}', receiver id '{2}' had the following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="29743-118">説明</span><span class="sxs-lookup"><span data-stu-id="29743-118">Explanation</span></span>  
 <span data-ttu-id="29743-119">このエラー/警告/情報イベントは、識別されたインターチェンジに、示されたエラーがあったため、EDIFACT の送信インターチェンジのシリアル中に EDI 送信パイプラインでエラーが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="29743-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing an outgoing EDIFACT interchange because of the stated errors with the identified interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="29743-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="29743-120">User Action</span></span>  
 <span data-ttu-id="29743-121">このエラーを解決するには、エラー メッセージの情報を使用してインターチェンジのエラーを特定し、製品のヘルプで問題の解決方法を確認してください。</span><span class="sxs-lookup"><span data-stu-id="29743-121">To resolve this error, use the information in the error message to identify the error in the interchange and then determine the problem resolution in the product help.</span></span>