---
title: シリアル化中に発生したエラーです。 Edifact インターチェンジ、グループが含まれていませんでしたが、次のエラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af693139-e4cd-4bcb-922c-79caa148d3b7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2faef5b896440a6f412187016d145e33e2ab0868
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348882"
---
# <a name="error-encountered-during-serialization-the-edifact-interchange-which-did-not-contain-a-group-had-the-following-errors"></a><span data-ttu-id="22ffc-103">シリアル化中に発生したエラーです。</span><span class="sxs-lookup"><span data-stu-id="22ffc-103">Error encountered during serialization.</span></span> <span data-ttu-id="22ffc-104">グループを含まない Edifact インターチェンジには、次のエラーがありました</span><span class="sxs-lookup"><span data-stu-id="22ffc-104">The Edifact interchange which did not contain a group had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="22ffc-105">詳細</span><span class="sxs-lookup"><span data-stu-id="22ffc-105">Details</span></span>  
  
|                 |                                                                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="22ffc-106">製品名</span><span class="sxs-lookup"><span data-stu-id="22ffc-106">Product Name</span></span>   |                                                     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                      |
| <span data-ttu-id="22ffc-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="22ffc-107">Product Version</span></span> |                                                                 [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                  |
|    <span data-ttu-id="22ffc-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="22ffc-108">Event ID</span></span>     |                                                                                              -                                                                                              |
|  <span data-ttu-id="22ffc-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="22ffc-109">Event Source</span></span>   |                                                   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="22ffc-110">EDI</span><span class="sxs-lookup"><span data-stu-id="22ffc-110">EDI</span></span>                                                    |
|    <span data-ttu-id="22ffc-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="22ffc-111">Component</span></span>    |                                                                                         <span data-ttu-id="22ffc-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="22ffc-112">EDI Engine</span></span>                                                                                          |
|  <span data-ttu-id="22ffc-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="22ffc-113">Symbolic Name</span></span>  |                                                                          <span data-ttu-id="22ffc-114">EfactFunctionalGroupSendErrorWithoutGroup</span><span class="sxs-lookup"><span data-stu-id="22ffc-114">EfactFunctionalGroupSendErrorWithoutGroup</span></span>                                                                          |
|  <span data-ttu-id="22ffc-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="22ffc-115">Message Text</span></span>   | <span data-ttu-id="22ffc-116">シリアル化中に発生したエラーです。</span><span class="sxs-lookup"><span data-stu-id="22ffc-116">Error encountered during serialization.</span></span> <span data-ttu-id="22ffc-117">Edifact インターチェンジのインターチェンジ id を持つ、グループを含まない '{0}'、送信者 id'{1}'、受信者 id '{2}' 次のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="22ffc-117">The Edifact interchange which did not contain a group, with interchange id '{0}', with sender id '{1}', receiver id '{2}' had the following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="22ffc-118">説明</span><span class="sxs-lookup"><span data-stu-id="22ffc-118">Explanation</span></span>  
 <span data-ttu-id="22ffc-119">このエラー/警告/情報イベントは、EDI 送信パイプラインでは、識別されたインターチェンジで示されたエラーのため送信 EDIFACT インターチェンジをシリアル化するときに、エラーが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="22ffc-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing an outgoing EDIFACT interchange because of the stated errors with the identified interchange.</span></span> <span data-ttu-id="22ffc-120">インターチェンジにグループが含まれていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="22ffc-120">Note that the interchange does not contain a group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="22ffc-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="22ffc-121">User Action</span></span>  
 <span data-ttu-id="22ffc-122">このエラーを解決するには、エラー メッセージの情報を使用して、インターチェンジでエラーを特定し、製品のヘルプで問題の解決方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="22ffc-122">To resolve this error, use the information in the error message to identify the error in the interchange and then determine the problem resolution in the product help.</span></span>