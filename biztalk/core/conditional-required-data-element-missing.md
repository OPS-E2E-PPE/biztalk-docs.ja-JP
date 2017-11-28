---
title: "条件付きの必須データ要素がありません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a5105c03-fa26-4c38-a276-c656f3076d5f
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d77a25e60af0d8287515d6fb3a7e2797d5af0b3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="conditional-required-data-element-missing"></a><span data-ttu-id="ce1e1-102">必須の条件付きデータ要素がありません</span><span class="sxs-lookup"><span data-stu-id="ce1e1-102">Conditional required data element missing</span></span>
## <a name="details"></a><span data-ttu-id="ce1e1-103">詳細</span><span class="sxs-lookup"><span data-stu-id="ce1e1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ce1e1-104">製品名</span><span class="sxs-lookup"><span data-stu-id="ce1e1-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="ce1e1-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="ce1e1-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="ce1e1-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ce1e1-106">Event ID</span></span>|-|  
|<span data-ttu-id="ce1e1-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="ce1e1-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="ce1e1-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="ce1e1-108"> EDI</span></span>|  
|<span data-ttu-id="ce1e1-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ce1e1-109">Component</span></span>|<span data-ttu-id="ce1e1-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="ce1e1-110">EDI Engine</span></span>|  
|<span data-ttu-id="ce1e1-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="ce1e1-111">Symbolic Name</span></span>|<span data-ttu-id="ce1e1-112">X12DeConditionalRequiredDataElementMissingDescription</span><span class="sxs-lookup"><span data-stu-id="ce1e1-112">X12DeConditionalRequiredDataElementMissingDescription</span></span>|  
|<span data-ttu-id="ce1e1-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="ce1e1-113">Message Text</span></span>|<span data-ttu-id="ce1e1-114">必須の条件付きデータ要素がありません</span><span class="sxs-lookup"><span data-stu-id="ce1e1-114">Conditional required data element missing</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ce1e1-115">説明</span><span class="sxs-lookup"><span data-stu-id="ce1e1-115">Explanation</span></span>  
 <span data-ttu-id="ce1e1-116">このエラー/警告/情報イベントは、X12ConditionDesignatorX ルールで必要になるデータ要素がインターチェンジに存在していないため、EDI 受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="ce1e1-116">This Error/Warning/Information event indicates that the EDI receive pipeline could not process the incoming interchange because a data element that is required by the X12ConditionDesignatorX rule does not exist in the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ce1e1-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="ce1e1-117">User Action</span></span>  
 <span data-ttu-id="ce1e1-118">このエラーは、BizTalk Server の構成や操作ではなく、受信インターチェンジの問題である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ce1e1-118">This error is likely an issue with the incoming interchange, not with the configuration or operation of BizTalk Server.</span></span> <span data-ttu-id="ce1e1-119">このエラーを解決するには、インターチェンジの送信者に連絡し、インターチェンジに使用されている文字または UNB1.1 フィールドで識別されている文字セットのどちらかを変更し、それらを一致させる必要があることを伝えます。</span><span class="sxs-lookup"><span data-stu-id="ce1e1-119">To resolve this error, contact the sender of the interchange and indicate that they need to change either the characters used in the interchange or the character set identified in field UNB1.1 so that they match.</span></span>