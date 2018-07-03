---
title: シリアル化中にエラーが発生しました。 X12 トランザクション セットの機能グループに含まれるは、次のエラーで中断されています |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 49b13038-2637-4435-91e9-d6fe2b80ca7a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 745fee9f48d534b750b605268ce63b1c685e3231
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988939"
---
# <a name="error-encountered-during-serialization-the-x12-transaction-set-contained-in-functional-group-is-being-suspended-with-following-errors"></a><span data-ttu-id="d4e6c-103">シリアル化中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="d4e6c-103">Error encountered during serialization.</span></span> <span data-ttu-id="d4e6c-104">機能グループに含まれる X12 トランザクション セットが次のエラーで中断されています</span><span class="sxs-lookup"><span data-stu-id="d4e6c-104">The X12 transaction set contained in functional group is being suspended with following errors</span></span>
## <a name="details"></a><span data-ttu-id="d4e6c-105">詳細</span><span class="sxs-lookup"><span data-stu-id="d4e6c-105">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="d4e6c-106">製品名</span><span class="sxs-lookup"><span data-stu-id="d4e6c-106">Product Name</span></span>   |                                                                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                             |
| <span data-ttu-id="d4e6c-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d4e6c-107">Product Version</span></span> |                                                                                         [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                                         |
|    <span data-ttu-id="d4e6c-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d4e6c-108">Event ID</span></span>     |                                                                                                                     -                                                                                                                      |
|  <span data-ttu-id="d4e6c-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d4e6c-109">Event Source</span></span>   |                                                                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="d4e6c-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="d4e6c-110"> EDI</span></span>                                                                           |
|    <span data-ttu-id="d4e6c-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d4e6c-111">Component</span></span>    |                                                                                                                 <span data-ttu-id="d4e6c-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="d4e6c-112">EDI Engine</span></span>                                                                                                                 |
|  <span data-ttu-id="d4e6c-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d4e6c-113">Symbolic Name</span></span>  |                                                                                                         <span data-ttu-id="d4e6c-114">X12TransactionSetSendError</span><span class="sxs-lookup"><span data-stu-id="d4e6c-114">X12TransactionSetSendError</span></span>                                                                                                         |
|  <span data-ttu-id="d4e6c-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d4e6c-115">Message Text</span></span>   | <span data-ttu-id="d4e6c-116">シリアル化中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="d4e6c-116">Error encountered during serialization.</span></span> <span data-ttu-id="d4e6c-117">X12 トランザクション セット id を持つ '{0}'機能グループ id に含まれている'{1}'、id を持つインターチェンジ内'{2}'、送信者 id '{3}'、受信者 id'{4}' 次のエラーで中断されています。</span><span class="sxs-lookup"><span data-stu-id="d4e6c-117">The X12 transaction set with id '{0}' contained in functional group with id '{1}', in interchange with id '{2}', with sender id '{3}', receiver id '{4}' is being suspended with following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="d4e6c-118">説明</span><span class="sxs-lookup"><span data-stu-id="d4e6c-118">Explanation</span></span>  
 <span data-ttu-id="d4e6c-119">このエラー/警告/情報イベントは、識別されたトランザクション セットに、示されたエラーがあったため、X12 の送信インターチェンジのシリアル化中に EDI 送信パイプラインでエラーが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="d4e6c-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing an outgoing X12 interchange because of the stated errors with the identified transaction set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d4e6c-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d4e6c-120">User Action</span></span>  
 <span data-ttu-id="d4e6c-121">このエラーを解決するには、エラー メッセージの情報を使用してトランザクション セットのエラーを特定し、製品のヘルプで問題の解決方法を確認してください。</span><span class="sxs-lookup"><span data-stu-id="d4e6c-121">To resolve this error, use the information in the error message to identify the error in the transaction set and then determine the problem resolution in the product help.</span></span>