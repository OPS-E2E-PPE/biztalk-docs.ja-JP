---
title: シリアル化中に発生したエラーです。 機能グループに含まれる設定の Edifact トランザクションは、次のエラーで中断されています |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24b76086-334b-45fb-85f8-82e3335daac4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f99a67f39f23cad9865bfea8cc0a7a8232a8745
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388835"
---
# <a name="error-encountered-during-serialization-the-edifact-transaction-set-contained-in-functional-group-is-being-suspended-with-following-errors"></a><span data-ttu-id="61bac-103">シリアル化中に発生したエラーです。</span><span class="sxs-lookup"><span data-stu-id="61bac-103">Error encountered during serialization.</span></span> <span data-ttu-id="61bac-104">機能グループに含まれる Edifact トランザクション セットは、次のエラーで中断されています</span><span class="sxs-lookup"><span data-stu-id="61bac-104">The Edifact transaction set contained in functional group is being suspended with following errors</span></span>
## <a name="details"></a><span data-ttu-id="61bac-105">詳細</span><span class="sxs-lookup"><span data-stu-id="61bac-105">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="61bac-106">製品名</span><span class="sxs-lookup"><span data-stu-id="61bac-106">Product Name</span></span>   |                                                                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                               |
| <span data-ttu-id="61bac-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="61bac-107">Product Version</span></span> |                                                                                           [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                                           |
|    <span data-ttu-id="61bac-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="61bac-108">Event ID</span></span>     |                                                                                                                       -                                                                                                                        |
|  <span data-ttu-id="61bac-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="61bac-109">Event Source</span></span>   |                                                                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="61bac-110">EDI</span><span class="sxs-lookup"><span data-stu-id="61bac-110">EDI</span></span>                                                                             |
|    <span data-ttu-id="61bac-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="61bac-111">Component</span></span>    |                                                                                                                   <span data-ttu-id="61bac-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="61bac-112">EDI Engine</span></span>                                                                                                                   |
|  <span data-ttu-id="61bac-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="61bac-113">Symbolic Name</span></span>  |                                                                                                          <span data-ttu-id="61bac-114">EfactTransactionSetSendError</span><span class="sxs-lookup"><span data-stu-id="61bac-114">EfactTransactionSetSendError</span></span>                                                                                                          |
|  <span data-ttu-id="61bac-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="61bac-115">Message Text</span></span>   | <span data-ttu-id="61bac-116">シリアル化中に発生したエラーです。</span><span class="sxs-lookup"><span data-stu-id="61bac-116">Error encountered during serialization.</span></span> <span data-ttu-id="61bac-117">Edifact トランザクション セット id を持つ '{0}'機能グループ id に含まれている'{1}'、id を持つインターチェンジ内'{2}'、送信者 id '{3}'、受信者 id'{4}' 次のエラーで中断されています。</span><span class="sxs-lookup"><span data-stu-id="61bac-117">The Edifact transaction set with id '{0}' contained in functional group with id '{1}', in interchange with id '{2}', with sender id '{3}', receiver id '{4}' is being suspended with following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="61bac-118">説明</span><span class="sxs-lookup"><span data-stu-id="61bac-118">Explanation</span></span>  
 <span data-ttu-id="61bac-119">このエラー/警告/情報イベントは、EDI 送信パイプラインでは、識別されたトランザクション セット、示されたエラーのため送信 EDIFACT インターチェンジをシリアル化するときに、エラーが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="61bac-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing an outgoing EDIFACT interchange because of the stated errors with the identified transaction set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="61bac-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="61bac-120">User Action</span></span>  
 <span data-ttu-id="61bac-121">このエラーを解決するには、エラー メッセージの情報を使用してトランザクション セットのエラーを特定し、製品のヘルプで問題の解決方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="61bac-121">To resolve this error, use the information in the error message to identify the error in the transaction set and then determine the problem resolution in the product help.</span></span>