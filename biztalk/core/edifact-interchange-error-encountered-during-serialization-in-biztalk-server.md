---
title: シリアル化中に発生したエラーです。 Edifact インターチェンジで次のエラーが |Microsoft Docs
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
ms.openlocfilehash: 346135947ea0b0f154178d67f29335a13a95526a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350022"
---
# <a name="error-encountered-during-serialization-the-edifact-interchange-had-the-following-errors"></a><span data-ttu-id="25efc-103">シリアル化中に発生したエラーです。</span><span class="sxs-lookup"><span data-stu-id="25efc-103">Error encountered during serialization.</span></span> <span data-ttu-id="25efc-104">Edifact インターチェンジには、次のエラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="25efc-104">The Edifact interchange had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="25efc-105">詳細</span><span class="sxs-lookup"><span data-stu-id="25efc-105">Details</span></span>  
  
|                 |                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="25efc-106">製品名</span><span class="sxs-lookup"><span data-stu-id="25efc-106">Product Name</span></span>   |                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                |
| <span data-ttu-id="25efc-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="25efc-107">Product Version</span></span> |                                            [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                            |
|    <span data-ttu-id="25efc-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="25efc-108">Event ID</span></span>     |                                                                        -                                                                         |
|  <span data-ttu-id="25efc-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="25efc-109">Event Source</span></span>   |                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="25efc-110">EDI</span><span class="sxs-lookup"><span data-stu-id="25efc-110">EDI</span></span>                              |
|    <span data-ttu-id="25efc-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="25efc-111">Component</span></span>    |                                                                    <span data-ttu-id="25efc-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="25efc-112">EDI Engine</span></span>                                                                    |
|  <span data-ttu-id="25efc-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="25efc-113">Symbolic Name</span></span>  |                                                            <span data-ttu-id="25efc-114">EfactInterchangeSendError</span><span class="sxs-lookup"><span data-stu-id="25efc-114">EfactInterchangeSendError</span></span>                                                             |
|  <span data-ttu-id="25efc-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="25efc-115">Message Text</span></span>   | <span data-ttu-id="25efc-116">シリアル化中に発生したエラーです。</span><span class="sxs-lookup"><span data-stu-id="25efc-116">Error encountered during serialization.</span></span> <span data-ttu-id="25efc-117">Edifact インターチェンジ id '{0}'、送信者 id'{1}'、受信者 id '{2}' 次のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="25efc-117">The Edifact interchange with id '{0}', with sender id '{1}', receiver id '{2}' had the following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="25efc-118">説明</span><span class="sxs-lookup"><span data-stu-id="25efc-118">Explanation</span></span>  
 <span data-ttu-id="25efc-119">このエラー/警告/情報イベントは、EDI 送信パイプラインでは、識別されたインターチェンジで示されたエラーのため送信 EDIFACT インターチェンジをシリアル化するときに、エラーが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="25efc-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing an outgoing EDIFACT interchange because of the stated errors with the identified interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="25efc-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="25efc-120">User Action</span></span>  
 <span data-ttu-id="25efc-121">このエラーを解決するには、エラー メッセージの情報を使用して、インターチェンジでエラーを特定し、製品のヘルプで問題の解決方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="25efc-121">To resolve this error, use the information in the error message to identify the error in the interchange and then determine the problem resolution in the product help.</span></span>