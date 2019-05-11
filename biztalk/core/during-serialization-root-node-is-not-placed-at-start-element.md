---
title: シリアル化中にルート ノードがない開始要素に配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9ea4aa6f-0f9c-4b7b-b7f6-24a5ce954048
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4403e9fb895ca05d4438f1e280d79008519918d9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350672"
---
# <a name="during-serialization-root-node-is-not-placed-at-start-element"></a><span data-ttu-id="bf9d4-102">シリアル化中にルート ノードが開始要素に配置されません</span><span class="sxs-lookup"><span data-stu-id="bf9d4-102">During serialization root node is not placed at start element</span></span>
## <a name="details"></a><span data-ttu-id="bf9d4-103">詳細</span><span class="sxs-lookup"><span data-stu-id="bf9d4-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="bf9d4-104">製品名</span><span class="sxs-lookup"><span data-stu-id="bf9d4-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="bf9d4-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="bf9d4-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="bf9d4-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="bf9d4-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="bf9d4-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="bf9d4-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="bf9d4-108">EDI</span><span class="sxs-lookup"><span data-stu-id="bf9d4-108">EDI</span></span> |
|    <span data-ttu-id="bf9d4-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="bf9d4-109">Component</span></span>    |                                       <span data-ttu-id="bf9d4-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="bf9d4-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="bf9d4-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="bf9d4-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="bf9d4-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="bf9d4-112">Message Text</span></span>   |             <span data-ttu-id="bf9d4-113">シリアル化中にルート ノードが開始要素に配置されません</span><span class="sxs-lookup"><span data-stu-id="bf9d4-113">During serialization root node is not placed at start element</span></span>              |
  
## <a name="explanation"></a><span data-ttu-id="bf9d4-114">説明</span><span class="sxs-lookup"><span data-stu-id="bf9d4-114">Explanation</span></span>  
 <span data-ttu-id="bf9d4-115">このエラー/警告/情報イベントは、トランザクション セットが ST または UNH ヘッダーで始まらないため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="bf9d4-115">This Error/Warning/Information event indicates that the receive pipeline could not process an incoming interchange because the transaction set does not start with an ST or UNH header.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bf9d4-116">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="bf9d4-116">User Action</span></span>  
 <span data-ttu-id="bf9d4-117">このエラーを解決するには、インターチェンジの各トランザクション セットが ST セグメント (X12 インターチェンジの場合) または UNH セグメント (EDIFACT インターチェンジの場合) で始まることを確認し、インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="bf9d4-117">To resolve this error, ensure that each of the transaction sets in an interchange starts with an ST segment (for X12 interchanges) or an UNH segment (for EDIFACT interchanges), and then resubmit the interchange.</span></span>