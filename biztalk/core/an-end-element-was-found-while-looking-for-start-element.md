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
ms.openlocfilehash: b44cd404242c19ebbfbc92b358fb33de9b510b95
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360191"
---
# <a name="an-end-element-was-found-while-looking-for-start-element"></a><span data-ttu-id="34d7e-102">開始要素の中に、終了要素が見つかりました</span><span class="sxs-lookup"><span data-stu-id="34d7e-102">An End Element was found while looking for Start Element</span></span>
## <a name="details"></a><span data-ttu-id="34d7e-103">詳細</span><span class="sxs-lookup"><span data-stu-id="34d7e-103">Details</span></span>  
  
|                 |                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="34d7e-104">製品名</span><span class="sxs-lookup"><span data-stu-id="34d7e-104">Product Name</span></span>   |        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]         |
| <span data-ttu-id="34d7e-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="34d7e-105">Product Version</span></span> |                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                     |
|    <span data-ttu-id="34d7e-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="34d7e-106">Event ID</span></span>     |                                                 -                                                 |
|  <span data-ttu-id="34d7e-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="34d7e-107">Event Source</span></span>   |      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="34d7e-108">EDI</span><span class="sxs-lookup"><span data-stu-id="34d7e-108">EDI</span></span>       |
|    <span data-ttu-id="34d7e-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="34d7e-109">Component</span></span>    |                                            <span data-ttu-id="34d7e-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="34d7e-110">EDI Engine</span></span>                                             |
|  <span data-ttu-id="34d7e-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="34d7e-111">Symbolic Name</span></span>  |                             <span data-ttu-id="34d7e-112">EndElementFoundWhenLookingForStartElement</span><span class="sxs-lookup"><span data-stu-id="34d7e-112">EndElementFoundWhenLookingForStartElement</span></span>                             |
|  <span data-ttu-id="34d7e-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="34d7e-113">Message Text</span></span>   | <span data-ttu-id="34d7e-114">名前の EndElement{0}検出されましたが、名前の StartElement の検索中に{1}、深さ {2}</span><span class="sxs-lookup"><span data-stu-id="34d7e-114">An EndElement with name {0} was found, while looking for StartElement with name {1}, at depth {2}</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="34d7e-115">説明</span><span class="sxs-lookup"><span data-stu-id="34d7e-115">Explanation</span></span>  
 <span data-ttu-id="34d7e-116">このエラー/警告/情報イベントは、BizTalk Server を処理できなかったこと (解析後) 受信 XML メッセージまたは送信 XML メッセージ (シリアル化) する前に、XML メッセージの検証に失敗したためことを示します。</span><span class="sxs-lookup"><span data-stu-id="34d7e-116">This Error/Warning/Information event indicates that BizTalk Server could not process an incoming XML message (after parsing) or an outgoing XML message (before serialization) because the XML message failed validation.</span></span> <span data-ttu-id="34d7e-117">XML メッセージに、ヘッダーまたはデータ要素の終了タグが含まれていませんでした。</span><span class="sxs-lookup"><span data-stu-id="34d7e-117">The XML message did not contain an end tag for a header or data element.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="34d7e-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="34d7e-118">User Action</span></span>  
 <span data-ttu-id="34d7e-119">このエラーを解決するには、XML メッセージに適切な終了タグまたはトレーラーを追加してし、メッセージを再送信します。</span><span class="sxs-lookup"><span data-stu-id="34d7e-119">To resolve this error, add the appropriate end tag or trailer to the XML message, and then resend the message.</span></span>