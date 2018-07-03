---
title: シリアル化中にエラーが発生しました。 Edifact 機能グループが、次のエラー |Microsoft Docs
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
ms.openlocfilehash: 0cd5ce1a94a47c5094862decfe1bb1dbb9c1efb0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977603"
---
# <a name="error-encountered-during-serialization-the-edifact-functional-group-had-the-following-errors"></a><span data-ttu-id="fc921-103">シリアル化中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="fc921-103">Error encountered during serialization.</span></span> <span data-ttu-id="fc921-104">EDIFACT 機能グループに次のエラーがありました</span><span class="sxs-lookup"><span data-stu-id="fc921-104">The Edifact functional group had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="fc921-105">詳細</span><span class="sxs-lookup"><span data-stu-id="fc921-105">Details</span></span>  
  
|                 |                                                                                                                                                                                     |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="fc921-106">製品名</span><span class="sxs-lookup"><span data-stu-id="fc921-106">Product Name</span></span>   |                                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                  |
| <span data-ttu-id="fc921-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="fc921-107">Product Version</span></span> |                                                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                              |
|    <span data-ttu-id="fc921-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="fc921-108">Event ID</span></span>     |                                                                                          -                                                                                          |
|  <span data-ttu-id="fc921-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="fc921-109">Event Source</span></span>   |                                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="fc921-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="fc921-110"> EDI</span></span>                                                |
|    <span data-ttu-id="fc921-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="fc921-111">Component</span></span>    |                                                                                     <span data-ttu-id="fc921-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="fc921-112">EDI Engine</span></span>                                                                                      |
|  <span data-ttu-id="fc921-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="fc921-113">Symbolic Name</span></span>  |                                                                            <span data-ttu-id="fc921-114">EfactFunctionalGroupSendError</span><span class="sxs-lookup"><span data-stu-id="fc921-114">EfactFunctionalGroupSendError</span></span>                                                                            |
|  <span data-ttu-id="fc921-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="fc921-115">Message Text</span></span>   | <span data-ttu-id="fc921-116">シリアル化中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="fc921-116">Error encountered during serialization.</span></span> <span data-ttu-id="fc921-117">Edifact 機能グループ id '{0}'、id を持つインターチェンジ内で'{1}'、送信者 id '{2}'、受信者 id'{3}' 次のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="fc921-117">The Edifact functional group with id '{0}', in interchange with id '{1}', with sender id '{2}', receiver id '{3}' had the following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="fc921-118">説明</span><span class="sxs-lookup"><span data-stu-id="fc921-118">Explanation</span></span>  
 <span data-ttu-id="fc921-119">このエラー/警告/情報イベントは、示されたエラーがグループで発生したため、送信 EDIFACT インターチェンジ内の機能グループのシリアル化中に EDI 送信パイプラインでエラーが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="fc921-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing a functional group within an outgoing EDIFACT interchange because of the stated errors with the group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fc921-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="fc921-120">User Action</span></span>  
 <span data-ttu-id="fc921-121">このエラーを解決するには、エラー メッセージの情報を使用して機能グループのエラーを特定し、ドキュメントで問題解決の方法を確認してください。</span><span class="sxs-lookup"><span data-stu-id="fc921-121">To resolve this error, use the information in the error message to identify the error in the functional group and then determine the problem resolution in the documentation.</span></span>