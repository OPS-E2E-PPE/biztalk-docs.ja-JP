---
title: シリアル化中にエラーが発生しました。 Edifact トランザクション セットの機能グループに含まれているが次のエラーで中断されています |Microsoft ドキュメント
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
ms.openlocfilehash: bb09bfecc2efc5e6878b7cc3d0149f2b56c07b68
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241434"
---
# <a name="error-encountered-during-serialization-the-edifact-transaction-set-contained-in-functional-group-is-being-suspended-with-following-errors"></a><span data-ttu-id="9a389-103">シリアル化中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="9a389-103">Error encountered during serialization.</span></span> <span data-ttu-id="9a389-104">機能グループに含まれる EDIFACT トランザクション セットが次のエラーで中断されています</span><span class="sxs-lookup"><span data-stu-id="9a389-104">The Edifact transaction set contained in functional group is being suspended with following errors</span></span>
## <a name="details"></a><span data-ttu-id="9a389-105">詳細</span><span class="sxs-lookup"><span data-stu-id="9a389-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9a389-106">製品名</span><span class="sxs-lookup"><span data-stu-id="9a389-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="9a389-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="9a389-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="9a389-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="9a389-108">Event ID</span></span>|-|  
|<span data-ttu-id="9a389-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="9a389-109">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="9a389-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="9a389-110"> EDI</span></span>|  
|<span data-ttu-id="9a389-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9a389-111">Component</span></span>|<span data-ttu-id="9a389-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="9a389-112">EDI Engine</span></span>|  
|<span data-ttu-id="9a389-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="9a389-113">Symbolic Name</span></span>|<span data-ttu-id="9a389-114">EfactTransactionSetSendError</span><span class="sxs-lookup"><span data-stu-id="9a389-114">EfactTransactionSetSendError</span></span>|  
|<span data-ttu-id="9a389-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="9a389-115">Message Text</span></span>|<span data-ttu-id="9a389-116">シリアル化中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="9a389-116">Error encountered during serialization.</span></span> <span data-ttu-id="9a389-117">Edifact トランザクション セット id '{0}' id '{1}' の機能グループに含まれている次のエラーで送信者 id '{3}' と ' {2}'、id を持つインターチェンジの受信者 id '{4}' が中断されています。</span><span class="sxs-lookup"><span data-stu-id="9a389-117">The Edifact transaction set with id '{0}' contained in functional group with id '{1}', in interchange with id '{2}', with sender id '{3}', receiver id '{4}' is being suspended with following errors:</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9a389-118">説明</span><span class="sxs-lookup"><span data-stu-id="9a389-118">Explanation</span></span>  
 <span data-ttu-id="9a389-119">このエラー/警告/情報イベントは、識別されたトランザクション セットに、示されたエラーがあったため、EDIFACT の送信インターチェンジのシリアル化中に EDI 送信パイプラインでエラーが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="9a389-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing an outgoing EDIFACT interchange because of the stated errors with the identified transaction set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9a389-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="9a389-120">User Action</span></span>  
 <span data-ttu-id="9a389-121">このエラーを解決するには、エラー メッセージの情報を使用してトランザクション セットのエラーを特定し、製品のヘルプで問題の解決方法を確認してください。</span><span class="sxs-lookup"><span data-stu-id="9a389-121">To resolve this error, use the information in the error message to identify the error in the transaction set and then determine the problem resolution in the product help.</span></span>