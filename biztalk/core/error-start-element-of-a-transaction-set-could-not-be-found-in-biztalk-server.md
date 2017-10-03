---
title: "トランザクション セットの開始要素が見つからなかったために、トランザクション セットの処理後に発生したエラー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d5380aee-1632-4cdf-98a1-aff87574ce4f
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 224b08046d1733aa8426909d7dddac4b10e48c8e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error-encountered-after-processing-transaction-sets-because-the-start-element-of-a-transaction-set-could-not-be-found"></a><span data-ttu-id="0ce90-102">トランザクション セットの開始要素が見つからなかったため、トランザクション セットの処理後にエラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="0ce90-102">Error encountered after processing Transaction Set(s) because the Start element of a Transaction set could not be found</span></span>
## <a name="details"></a><span data-ttu-id="0ce90-103">詳細</span><span class="sxs-lookup"><span data-stu-id="0ce90-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0ce90-104">製品名</span><span class="sxs-lookup"><span data-stu-id="0ce90-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="0ce90-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="0ce90-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="0ce90-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0ce90-106">Event ID</span></span>|-|  
|<span data-ttu-id="0ce90-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="0ce90-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0ce90-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="0ce90-108"> EDI</span></span>|  
|<span data-ttu-id="0ce90-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0ce90-109">Component</span></span>|<span data-ttu-id="0ce90-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="0ce90-110">EDI Engine</span></span>|  
|<span data-ttu-id="0ce90-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="0ce90-111">Symbolic Name</span></span>|<span data-ttu-id="0ce90-112">InvalidEfactBiboXmlFormat</span><span class="sxs-lookup"><span data-stu-id="0ce90-112">InvalidEfactBiboXmlFormat</span></span>|  
|<span data-ttu-id="0ce90-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="0ce90-113">Message Text</span></span>|<span data-ttu-id="0ce90-114">{0} トランザクション セットを処理した後でエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="0ce90-114">Error encountered after processing {0} Transaction Set(s).</span></span> <span data-ttu-id="0ce90-115">トランザクション セットの開始要素が見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="0ce90-115">Start element of a Transaction set could not be found.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0ce90-116">説明</span><span class="sxs-lookup"><span data-stu-id="0ce90-116">Explanation</span></span>  
 <span data-ttu-id="0ce90-117">このエラー/警告/情報イベントは、受信パイプラインが ST または UNH ヘッダーを見つけられなかったため、EDI 受信パイプラインで受信トランザクション セットを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="0ce90-117">This Error/Warning/Information event indicates that the EDI receive pipeline could not process an incoming transaction set because the receive pipeline could not find the ST or UNH header.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0ce90-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="0ce90-118">User Action</span></span>  
 <span data-ttu-id="0ce90-119">このエラーを解決するには、インターチェンジの送信者に連絡し、エラーのあったトランザクション セットが ST01 または UNH1 セグメントで始まるようにしてもらいます。</span><span class="sxs-lookup"><span data-stu-id="0ce90-119">To resolve this error, contact the sender of the interchange, and have them ensure that the transaction set in error begins with an ST01 or UNH1 segment.</span></span>