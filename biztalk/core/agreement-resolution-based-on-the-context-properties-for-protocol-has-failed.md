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
ms.openlocfilehash: e5cb408e59f6817be9aa06f94d3b83d90f07c494
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359921"
---
# <a name="agreement-resolution-based-on-the-context-properties-for-protocol-has-failed"></a><span data-ttu-id="a2116-102">アグリーメントのコンテキスト プロパティ プロトコルに基づく解決が失敗しました</span><span class="sxs-lookup"><span data-stu-id="a2116-102">Agreement Resolution based on the context properties for Protocol has failed</span></span>
## <a name="details"></a><span data-ttu-id="a2116-103">詳細</span><span class="sxs-lookup"><span data-stu-id="a2116-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="a2116-104">製品名</span><span class="sxs-lookup"><span data-stu-id="a2116-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="a2116-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="a2116-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="a2116-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="a2116-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="a2116-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="a2116-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="a2116-108">EDI</span><span class="sxs-lookup"><span data-stu-id="a2116-108">EDI</span></span> |
|    <span data-ttu-id="a2116-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a2116-109">Component</span></span>    |                                       <span data-ttu-id="a2116-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="a2116-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="a2116-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="a2116-111">Symbolic Name</span></span>  |                    <span data-ttu-id="a2116-112">AgreementResolutionContextPropertiesLookupFailed</span><span class="sxs-lookup"><span data-stu-id="a2116-112">AgreementResolutionContextPropertiesLookupFailed</span></span>                    |
|  <span data-ttu-id="a2116-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="a2116-113">Message Text</span></span>   |   <span data-ttu-id="a2116-114">コンテキスト プロパティに基づくアグリーメント解決{0}プロトコルが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="a2116-114">Agreement Resolution based on the context properties for {0} Protocol has failed.</span></span>    |
  
## <a name="explanation"></a><span data-ttu-id="a2116-115">説明</span><span class="sxs-lookup"><span data-stu-id="a2116-115">Explanation</span></span>  
 <span data-ttu-id="a2116-116">このエラー/警告/情報イベントは、BizTalk Server で、顧客が用意されているコンテキスト プロパティに基づいてアグリーメントを解決できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="a2116-116">This Error/Warning/Information event indicates BizTalk Server was not able to resolve to an Agreement based on the context properties that are provided by the customer.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a2116-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="a2116-117">User Action</span></span>  
 <span data-ttu-id="a2116-118">このエラーを解決するには、コンテキスト プロパティの BizTalk メッセージの一部としてでの指定は、アグリーメントの解決が実行されるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="a2116-118">To resolve this error, please provide the context properties as part of the BizTalk message such that Agreement Resolution can happen.</span></span>