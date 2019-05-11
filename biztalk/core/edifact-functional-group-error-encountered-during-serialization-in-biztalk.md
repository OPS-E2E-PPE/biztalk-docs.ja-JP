---
title: シリアル化中に発生したエラーです。 Edifact 機能グループが、次のエラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed81bc79-d99c-4305-805f-ab38eae91ea0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e8750a1ae4070543a9463b95827f14d10ab5180
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530787"
---
# <a name="error-encountered-during-serialization-the-edifact-functional-group-had-the-following-errors"></a><span data-ttu-id="88442-103">シリアル化中に発生したエラーです。</span><span class="sxs-lookup"><span data-stu-id="88442-103">Error encountered during serialization.</span></span> <span data-ttu-id="88442-104">Edifact 機能グループには、次のエラーがありました</span><span class="sxs-lookup"><span data-stu-id="88442-104">The Edifact functional group had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="88442-105">詳細</span><span class="sxs-lookup"><span data-stu-id="88442-105">Details</span></span>  
  
|                 |                                                                                                                                                                                     |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="88442-106">製品名</span><span class="sxs-lookup"><span data-stu-id="88442-106">Product Name</span></span>   |                                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                  |
| <span data-ttu-id="88442-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="88442-107">Product Version</span></span> |                                                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                              |
|    <span data-ttu-id="88442-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="88442-108">Event ID</span></span>     |                                                                                          -                                                                                          |
|  <span data-ttu-id="88442-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="88442-109">Event Source</span></span>   |                                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="88442-110">EDI</span><span class="sxs-lookup"><span data-stu-id="88442-110">EDI</span></span>                                                |
|    <span data-ttu-id="88442-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="88442-111">Component</span></span>    |                                                                                     <span data-ttu-id="88442-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="88442-112">EDI Engine</span></span>                                                                                      |
|  <span data-ttu-id="88442-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="88442-113">Symbolic Name</span></span>  |                                                                            <span data-ttu-id="88442-114">EfactFunctionalGroupSendError</span><span class="sxs-lookup"><span data-stu-id="88442-114">EfactFunctionalGroupSendError</span></span>                                                                            |
|  <span data-ttu-id="88442-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="88442-115">Message Text</span></span>   | <span data-ttu-id="88442-116">シリアル化中に発生したエラーです。</span><span class="sxs-lookup"><span data-stu-id="88442-116">Error encountered during serialization.</span></span> <span data-ttu-id="88442-117">Edifact 機能グループ id '{0}'、id を持つインターチェンジ内で'{1}'、送信者 id '{2}'、受信者 id'{3}' 次のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="88442-117">The Edifact functional group with id '{0}', in interchange with id '{1}', with sender id '{2}', receiver id '{3}' had the following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="88442-118">説明</span><span class="sxs-lookup"><span data-stu-id="88442-118">Explanation</span></span>  
 <span data-ttu-id="88442-119">このエラー/警告/情報イベントは、EDI 送信パイプラインでは、グループに示されたエラーのため、送信 EDIFACT インターチェンジ内の機能グループをシリアル化するときに、エラーが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="88442-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing a functional group within an outgoing EDIFACT interchange because of the stated errors with the group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="88442-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="88442-120">User Action</span></span>  
 <span data-ttu-id="88442-121">このエラーを解決するには、エラー メッセージの情報を使用して機能グループでエラーを特定し、ドキュメントで問題の解決方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="88442-121">To resolve this error, use the information in the error message to identify the error in the functional group and then determine the problem resolution in the documentation.</span></span>