---
title: "無効なコントロールの構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f9bb104-7ea1-429a-8540-49f4d598fd46
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa21ceae70798242a153978adeaf5b75478b3b49
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-control-structure"></a><span data-ttu-id="619fa-102">制御構造が無効です。</span><span class="sxs-lookup"><span data-stu-id="619fa-102">Invalid Control Structure</span></span>
## <a name="details"></a><span data-ttu-id="619fa-103">詳細</span><span class="sxs-lookup"><span data-stu-id="619fa-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="619fa-104">製品名</span><span class="sxs-lookup"><span data-stu-id="619fa-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="619fa-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="619fa-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="619fa-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="619fa-106">Event ID</span></span>|-|  
|<span data-ttu-id="619fa-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="619fa-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="619fa-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="619fa-108"> EDI</span></span>|  
|<span data-ttu-id="619fa-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="619fa-109">Component</span></span>|<span data-ttu-id="619fa-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="619fa-110">EDI Engine</span></span>|  
|<span data-ttu-id="619fa-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="619fa-111">Symbolic Name</span></span>|<span data-ttu-id="619fa-112">X12Ta1InvalidControlStructureDescription</span><span class="sxs-lookup"><span data-stu-id="619fa-112">X12Ta1InvalidControlStructureDescription</span></span>|  
|<span data-ttu-id="619fa-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="619fa-113">Message Text</span></span>|<span data-ttu-id="619fa-114">制御構造が無効です。</span><span class="sxs-lookup"><span data-stu-id="619fa-114">Invalid Control Structure</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="619fa-115">説明</span><span class="sxs-lookup"><span data-stu-id="619fa-115">Explanation</span></span>  
 <span data-ttu-id="619fa-116">このエラー/警告/情報イベントは、BizTalk Server が TA1 受信確認の構造を TA1Schema に対して検証できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="619fa-116">This Error/Warning/Information event indicates that BizTalk Server could not validate the structure of the TA1 acknowledgment against the TA1Schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="619fa-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="619fa-117">User Action</span></span>  
 <span data-ttu-id="619fa-118">このエラーを解決するには、TA1 受信確認が TA1Schema に準拠していない理由を特定し、問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="619fa-118">To resolve this error, determine why the TA1 acknowledgment does not conform to the TA1Schema, and resolve the issue.</span></span>