---
title: アグリーメントの解決は、プロトコルのコンテキスト プロパティに基づく |Microsoft Docs
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
ms.openlocfilehash: a2cac1ea6e940385fceac541df96582f93eb058e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008171"
---
# <a name="agreement-resolution-based-on-the-context-properties-for-protocol-has-failed"></a><span data-ttu-id="774e1-102">プロトコルに対するコンテキスト プロパティに基づくアグリーメントの解決が失敗しました</span><span class="sxs-lookup"><span data-stu-id="774e1-102">Agreement Resolution based on the context properties for Protocol has failed</span></span>
## <a name="details"></a><span data-ttu-id="774e1-103">詳細</span><span class="sxs-lookup"><span data-stu-id="774e1-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="774e1-104">製品名</span><span class="sxs-lookup"><span data-stu-id="774e1-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="774e1-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="774e1-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="774e1-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="774e1-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="774e1-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="774e1-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="774e1-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="774e1-108"> EDI</span></span> |
|    <span data-ttu-id="774e1-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="774e1-109">Component</span></span>    |                                       <span data-ttu-id="774e1-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="774e1-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="774e1-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="774e1-111">Symbolic Name</span></span>  |                    <span data-ttu-id="774e1-112">AgreementResolutionContextPropertiesLookupFailed</span><span class="sxs-lookup"><span data-stu-id="774e1-112">AgreementResolutionContextPropertiesLookupFailed</span></span>                    |
|  <span data-ttu-id="774e1-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="774e1-113">Message Text</span></span>   |   <span data-ttu-id="774e1-114">コンテキスト プロパティに基づくアグリーメント解決{0}プロトコルが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="774e1-114">Agreement Resolution based on the context properties for {0} Protocol has failed.</span></span>    |
  
## <a name="explanation"></a><span data-ttu-id="774e1-115">説明</span><span class="sxs-lookup"><span data-stu-id="774e1-115">Explanation</span></span>  
 <span data-ttu-id="774e1-116">このエラー/警告/情報イベントは、BizTalk Server がユーザーによって指定されたコンテキスト プロパティに基づいてアグリーメントを解決できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="774e1-116">This Error/Warning/Information event indicates BizTalk Server was not able to resolve to an Agreement based on the context properties that are provided by the customer.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="774e1-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="774e1-117">User Action</span></span>  
 <span data-ttu-id="774e1-118">このエラーを解決するには、アグリーメントの解決が実行されるように、BizTalk メッセージの一部としてコンテキスト プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="774e1-118">To resolve this error, please provide the context properties as part of the BizTalk message such that Agreement Resolution can happen.</span></span>