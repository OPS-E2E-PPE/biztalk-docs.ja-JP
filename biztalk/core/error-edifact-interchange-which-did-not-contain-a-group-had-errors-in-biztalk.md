---
title: シリアル化中にエラーが発生しました。 Edifact インターチェンジ、グループが含まれていませんでしたが、次のエラー |Microsoft Docs
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
ms.openlocfilehash: f06625ad9689349b0aa47453c5aa2cc50cf9d807
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988299"
---
# <a name="error-encountered-during-serialization-the-edifact-interchange-which-did-not-contain-a-group-had-the-following-errors"></a><span data-ttu-id="7d19d-103">シリアル化中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="7d19d-103">Error encountered during serialization.</span></span> <span data-ttu-id="7d19d-104">グループを含まない EDIFACT インターチェンジに、次のエラーがありました</span><span class="sxs-lookup"><span data-stu-id="7d19d-104">The Edifact interchange which did not contain a group had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="7d19d-105">詳細</span><span class="sxs-lookup"><span data-stu-id="7d19d-105">Details</span></span>  
  
|                 |                                                                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="7d19d-106">製品名</span><span class="sxs-lookup"><span data-stu-id="7d19d-106">Product Name</span></span>   |                                                     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                      |
| <span data-ttu-id="7d19d-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="7d19d-107">Product Version</span></span> |                                                                 [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                  |
|    <span data-ttu-id="7d19d-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7d19d-108">Event ID</span></span>     |                                                                                              -                                                                                              |
|  <span data-ttu-id="7d19d-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="7d19d-109">Event Source</span></span>   |                                                   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="7d19d-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="7d19d-110"> EDI</span></span>                                                    |
|    <span data-ttu-id="7d19d-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7d19d-111">Component</span></span>    |                                                                                         <span data-ttu-id="7d19d-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="7d19d-112">EDI Engine</span></span>                                                                                          |
|  <span data-ttu-id="7d19d-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="7d19d-113">Symbolic Name</span></span>  |                                                                          <span data-ttu-id="7d19d-114">EfactFunctionalGroupSendErrorWithoutGroup</span><span class="sxs-lookup"><span data-stu-id="7d19d-114">EfactFunctionalGroupSendErrorWithoutGroup</span></span>                                                                          |
|  <span data-ttu-id="7d19d-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="7d19d-115">Message Text</span></span>   | <span data-ttu-id="7d19d-116">シリアル化中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="7d19d-116">Error encountered during serialization.</span></span> <span data-ttu-id="7d19d-117">Edifact インターチェンジのインターチェンジ id を持つ、グループを含まない '{0}'、送信者 id'{1}'、受信者 id '{2}' 次のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="7d19d-117">The Edifact interchange which did not contain a group, with interchange id '{0}', with sender id '{1}', receiver id '{2}' had the following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="7d19d-118">説明</span><span class="sxs-lookup"><span data-stu-id="7d19d-118">Explanation</span></span>  
 <span data-ttu-id="7d19d-119">このエラー/警告/情報イベントは、識別されたインターチェンジに、示されたエラーがあったため、EDIFACT の送信インターチェンジのシリアル中に EDI 送信パイプラインでエラーが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="7d19d-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing an outgoing EDIFACT interchange because of the stated errors with the identified interchange.</span></span> <span data-ttu-id="7d19d-120">インターチェンジにグループは含まれないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7d19d-120">Note that the interchange does not contain a group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7d19d-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="7d19d-121">User Action</span></span>  
 <span data-ttu-id="7d19d-122">このエラーを解決するには、エラー メッセージの情報を使用してインターチェンジのエラーを特定し、製品のヘルプで問題の解決方法を確認してください。</span><span class="sxs-lookup"><span data-stu-id="7d19d-122">To resolve this error, use the information in the error message to identify the error in the interchange and then determine the problem resolution in the product help.</span></span>