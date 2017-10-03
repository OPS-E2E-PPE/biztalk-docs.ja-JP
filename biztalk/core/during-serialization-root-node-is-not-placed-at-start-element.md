---
title: "シリアル化中にルート ノードがない開始要素に配置 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9ea4aa6f-0f9c-4b7b-b7f6-24a5ce954048
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3dced7e36802dd9d9ec9620272fc8a96bd6b590
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="during-serialization-root-node-is-not-placed-at-start-element"></a><span data-ttu-id="7b0e8-102">シリアル化中にルート ノードが開始要素に配置されません</span><span class="sxs-lookup"><span data-stu-id="7b0e8-102">During serialization root node is not placed at start element</span></span>
## <a name="details"></a><span data-ttu-id="7b0e8-103">詳細</span><span class="sxs-lookup"><span data-stu-id="7b0e8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7b0e8-104">製品名</span><span class="sxs-lookup"><span data-stu-id="7b0e8-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="7b0e8-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="7b0e8-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="7b0e8-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7b0e8-106">Event ID</span></span>|-|  
|<span data-ttu-id="7b0e8-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="7b0e8-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="7b0e8-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="7b0e8-108"> EDI</span></span>|  
|<span data-ttu-id="7b0e8-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7b0e8-109">Component</span></span>|<span data-ttu-id="7b0e8-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="7b0e8-110">EDI Engine</span></span>|  
|<span data-ttu-id="7b0e8-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="7b0e8-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="7b0e8-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="7b0e8-112">Message Text</span></span>|<span data-ttu-id="7b0e8-113">シリアル化中にルート ノードが開始要素に配置されません</span><span class="sxs-lookup"><span data-stu-id="7b0e8-113">During serialization root node is not placed at start element</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7b0e8-114">説明</span><span class="sxs-lookup"><span data-stu-id="7b0e8-114">Explanation</span></span>  
 <span data-ttu-id="7b0e8-115">このエラー/警告/情報イベントは、トランザクション セットが ST または UNH ヘッダーで始まらないため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="7b0e8-115">This Error/Warning/Information event indicates that the receive pipeline could not process an incoming interchange because the transaction set does not start with an ST or UNH header.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7b0e8-116">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="7b0e8-116">User Action</span></span>  
 <span data-ttu-id="7b0e8-117">このエラーを解決するには、インターチェンジの各トランザクション セットが ST セグメント (X12 インターチェンジの場合) または UNH セグメント (EDIFACT インターチェンジの場合) で始まることを確認し、インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="7b0e8-117">To resolve this error, ensure that each of the transaction sets in an interchange starts with an ST segment (for X12 interchanges) or an UNH segment (for EDIFACT interchanges), and then resubmit the interchange.</span></span>