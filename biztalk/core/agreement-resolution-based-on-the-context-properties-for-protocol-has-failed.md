---
title: アグリーメントの解決は、プロトコルが失敗しましたコンテキスト プロパティに基づく |。Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58fccd84-579c-4b5e-872b-33730d4079e8
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76d74ad7aa4a73f4a0befcef32bc8051195cb080
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22229938"
---
# <a name="agreement-resolution-based-on-the-context-properties-for-protocol-has-failed"></a><span data-ttu-id="79d00-102">プロトコルに対するコンテキスト プロパティに基づくアグリーメントの解決が失敗しました</span><span class="sxs-lookup"><span data-stu-id="79d00-102">Agreement Resolution based on the context properties for Protocol has failed</span></span>
## <a name="details"></a><span data-ttu-id="79d00-103">詳細</span><span class="sxs-lookup"><span data-stu-id="79d00-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="79d00-104">製品名</span><span class="sxs-lookup"><span data-stu-id="79d00-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="79d00-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="79d00-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="79d00-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="79d00-106">Event ID</span></span>|-|  
|<span data-ttu-id="79d00-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="79d00-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="79d00-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="79d00-108"> EDI</span></span>|  
|<span data-ttu-id="79d00-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="79d00-109">Component</span></span>|<span data-ttu-id="79d00-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="79d00-110">EDI Engine</span></span>|  
|<span data-ttu-id="79d00-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="79d00-111">Symbolic Name</span></span>|<span data-ttu-id="79d00-112">AgreementResolutionContextPropertiesLookupFailed</span><span class="sxs-lookup"><span data-stu-id="79d00-112">AgreementResolutionContextPropertiesLookupFailed</span></span>|  
|<span data-ttu-id="79d00-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="79d00-113">Message Text</span></span>|<span data-ttu-id="79d00-114">アグリーメントの解決は、プロトコルが失敗した {0} のコンテキスト プロパティに基づいています。</span><span class="sxs-lookup"><span data-stu-id="79d00-114">Agreement Resolution based on the context properties for {0} Protocol has failed.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="79d00-115">説明</span><span class="sxs-lookup"><span data-stu-id="79d00-115">Explanation</span></span>  
 <span data-ttu-id="79d00-116">このエラー/警告/情報イベントは、BizTalk Server がユーザーによって指定されたコンテキスト プロパティに基づいてアグリーメントを解決できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="79d00-116">This Error/Warning/Information event indicates BizTalk Server was not able to resolve to an Agreement based on the context properties that are provided by the customer.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="79d00-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="79d00-117">User Action</span></span>  
 <span data-ttu-id="79d00-118">このエラーを解決するには、アグリーメントの解決が実行されるように、BizTalk メッセージの一部としてコンテキスト プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="79d00-118">To resolve this error, please provide the context properties as part of the BizTalk message such that Agreement Resolution can happen.</span></span>