---
title: 開始要素の中に、終了要素が見つかりました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f7690744-a795-47cc-bc66-a0314a4cc320
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e200f4ffd8d822a5c2bb1a0bad74a60e84a408a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992435"
---
# <a name="an-end-element-was-found-while-looking-for-start-element"></a><span data-ttu-id="e07c4-102">StartElement の検索中に EndElement が見つかりました</span><span class="sxs-lookup"><span data-stu-id="e07c4-102">An End Element was found while looking for Start Element</span></span>
## <a name="details"></a><span data-ttu-id="e07c4-103">詳細</span><span class="sxs-lookup"><span data-stu-id="e07c4-103">Details</span></span>  
  
|                 |                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="e07c4-104">製品名</span><span class="sxs-lookup"><span data-stu-id="e07c4-104">Product Name</span></span>   |        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]         |
| <span data-ttu-id="e07c4-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="e07c4-105">Product Version</span></span> |                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                     |
|    <span data-ttu-id="e07c4-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e07c4-106">Event ID</span></span>     |                                                 -                                                 |
|  <span data-ttu-id="e07c4-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="e07c4-107">Event Source</span></span>   |      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e07c4-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="e07c4-108"> EDI</span></span>       |
|    <span data-ttu-id="e07c4-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e07c4-109">Component</span></span>    |                                            <span data-ttu-id="e07c4-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="e07c4-110">EDI Engine</span></span>                                             |
|  <span data-ttu-id="e07c4-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="e07c4-111">Symbolic Name</span></span>  |                             <span data-ttu-id="e07c4-112">EndElementFoundWhenLookingForStartElement</span><span class="sxs-lookup"><span data-stu-id="e07c4-112">EndElementFoundWhenLookingForStartElement</span></span>                             |
|  <span data-ttu-id="e07c4-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="e07c4-113">Message Text</span></span>   | <span data-ttu-id="e07c4-114">名前の EndElement{0}検出されましたが、名前の StartElement の検索中に{1}、深さ {2}</span><span class="sxs-lookup"><span data-stu-id="e07c4-114">An EndElement with name {0} was found, while looking for StartElement with name {1}, at depth {2}</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="e07c4-115">説明</span><span class="sxs-lookup"><span data-stu-id="e07c4-115">Explanation</span></span>  
 <span data-ttu-id="e07c4-116">このエラー/警告/情報イベントは、XML メッセージが検証に失敗したため、BizTalk Server が受信 XML メッセージ (解析後) または送信 XML メッセージ (シリアル化前) を処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="e07c4-116">This Error/Warning/Information event indicates that BizTalk Server could not process an incoming XML message (after parsing) or an outgoing XML message (before serialization) because the XML message failed validation.</span></span> <span data-ttu-id="e07c4-117">XML メッセージに、ヘッダーまたはデータ要素の終了タグが含まれていませんでした。</span><span class="sxs-lookup"><span data-stu-id="e07c4-117">The XML message did not contain an end tag for a header or data element.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e07c4-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="e07c4-118">User Action</span></span>  
 <span data-ttu-id="e07c4-119">このエラーを解決するには、XML メッセージに適切な終了タグまたはトレーラーを追加し、メッセージを再送信します。</span><span class="sxs-lookup"><span data-stu-id="e07c4-119">To resolve this error, add the appropriate end tag or trailer to the XML message, and then resend the message.</span></span>