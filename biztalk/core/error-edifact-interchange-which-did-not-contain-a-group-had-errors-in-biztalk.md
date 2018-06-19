---
title: シリアル化中にエラーが発生しました。 次のエラーが発生しました、Edifact インターチェンジ、グループが含まれていませんでした |Microsoft ドキュメント
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
ms.openlocfilehash: 72108104b359d4d06233cf9a623097bfd046a0ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241762"
---
# <a name="error-encountered-during-serialization-the-edifact-interchange-which-did-not-contain-a-group-had-the-following-errors"></a><span data-ttu-id="b9b00-103">シリアル化中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="b9b00-103">Error encountered during serialization.</span></span> <span data-ttu-id="b9b00-104">グループを含まない EDIFACT インターチェンジに、次のエラーがありました</span><span class="sxs-lookup"><span data-stu-id="b9b00-104">The Edifact interchange which did not contain a group had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="b9b00-105">詳細</span><span class="sxs-lookup"><span data-stu-id="b9b00-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b9b00-106">製品名</span><span class="sxs-lookup"><span data-stu-id="b9b00-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="b9b00-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="b9b00-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="b9b00-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="b9b00-108">Event ID</span></span>|-|  
|<span data-ttu-id="b9b00-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="b9b00-109">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="b9b00-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="b9b00-110"> EDI</span></span>|  
|<span data-ttu-id="b9b00-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b9b00-111">Component</span></span>|<span data-ttu-id="b9b00-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="b9b00-112">EDI Engine</span></span>|  
|<span data-ttu-id="b9b00-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="b9b00-113">Symbolic Name</span></span>|<span data-ttu-id="b9b00-114">EfactFunctionalGroupSendErrorWithoutGroup</span><span class="sxs-lookup"><span data-stu-id="b9b00-114">EfactFunctionalGroupSendErrorWithoutGroup</span></span>|  
|<span data-ttu-id="b9b00-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="b9b00-115">Message Text</span></span>|<span data-ttu-id="b9b00-116">シリアル化中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="b9b00-116">Error encountered during serialization.</span></span> <span data-ttu-id="b9b00-117">インターチェンジ id '{0}'、送信者 id '{1}' で、グループを含まない Edifact インターチェンジ受信者 id '{2}' には、次のエラーが必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9b00-117">The Edifact interchange which did not contain a group, with interchange id '{0}', with sender id '{1}', receiver id '{2}' had the following errors:</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b9b00-118">説明</span><span class="sxs-lookup"><span data-stu-id="b9b00-118">Explanation</span></span>  
 <span data-ttu-id="b9b00-119">このエラー/警告/情報イベントは、識別されたインターチェンジに、示されたエラーがあったため、EDIFACT の送信インターチェンジのシリアル中に EDI 送信パイプラインでエラーが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="b9b00-119">This Error/Warning/Information event indicates that the EDI send pipeline encountered an error when serializing an outgoing EDIFACT interchange because of the stated errors with the identified interchange.</span></span> <span data-ttu-id="b9b00-120">インターチェンジにグループは含まれないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b9b00-120">Note that the interchange does not contain a group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b9b00-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="b9b00-121">User Action</span></span>  
 <span data-ttu-id="b9b00-122">このエラーを解決するには、エラー メッセージの情報を使用してインターチェンジのエラーを特定し、製品のヘルプで問題の解決方法を確認してください。</span><span class="sxs-lookup"><span data-stu-id="b9b00-122">To resolve this error, use the information in the error message to identify the error in the interchange and then determine the problem resolution in the product help.</span></span>