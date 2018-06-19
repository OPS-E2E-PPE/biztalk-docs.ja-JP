---
title: 解析中にエラーが発生しました。 Edifact 機能グループのインターチェンジに次のエラーが発生しました |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77ca78b3-8a1f-4da5-9c15-524ab6802457
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6af00ae6500419fcb3ed687da89415e7594f1adc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241058"
---
# <a name="error-encountered-during-parsing-the-edifact-functional-group-in-interchange-had-the-following-errors"></a><span data-ttu-id="22016-103">解析中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="22016-103">Error encountered during parsing.</span></span> <span data-ttu-id="22016-104">インターチェンジ内の EDIFACT 機能グループに次のエラーがありました</span><span class="sxs-lookup"><span data-stu-id="22016-104">The Edifact functional group in interchange had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="22016-105">詳細</span><span class="sxs-lookup"><span data-stu-id="22016-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="22016-106">製品名</span><span class="sxs-lookup"><span data-stu-id="22016-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="22016-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="22016-107">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="22016-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="22016-108">Event ID</span></span>|-|  
|<span data-ttu-id="22016-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="22016-109">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="22016-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="22016-110"> EDI</span></span>|  
|<span data-ttu-id="22016-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="22016-111">Component</span></span>|<span data-ttu-id="22016-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="22016-112">EDI Engine</span></span>|  
|<span data-ttu-id="22016-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="22016-113">Symbolic Name</span></span>|<span data-ttu-id="22016-114">EfactFunctionalGroupReceiveError</span><span class="sxs-lookup"><span data-stu-id="22016-114">EfactFunctionalGroupReceiveError</span></span>|  
|<span data-ttu-id="22016-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="22016-115">Message Text</span></span>|<span data-ttu-id="22016-116">解析中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="22016-116">Error encountered during parsing.</span></span> <span data-ttu-id="22016-117">Edifact 機能グループ id '{0}'、id '{1}' を持つインターチェンジの送信者 id '{2}' に受信者 id '{3}' では、次のエラーがありました。</span><span class="sxs-lookup"><span data-stu-id="22016-117">The Edifact functional group with id '{0}', in interchange with id '{1}', with sender id '{2}', receiver id '{3}' had the following errors:</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="22016-118">説明</span><span class="sxs-lookup"><span data-stu-id="22016-118">Explanation</span></span>  
 <span data-ttu-id="22016-119">このエラー/警告/情報イベントは、識別された機能グループに、示されたエラーがあったため、EDIFACT の受信インターチェンジを解析しているときに EDI 受信パイプラインでエラーが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="22016-119">This Error/Warning/Information event indicates that the EDI receive pipeline encountered an error when parsing an incoming EDIFACT interchange because of the stated errors with the identified functional group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="22016-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="22016-120">User Action</span></span>  
 <span data-ttu-id="22016-121">このエラーを解決するには、エラー メッセージの情報を使用してグループのエラーを特定し、製品のヘルプで問題の解決方法を確認してください。</span><span class="sxs-lookup"><span data-stu-id="22016-121">To resolve this error, use the information in the error message to identify the error in the group and then determine the problem resolution in the product help.</span></span>