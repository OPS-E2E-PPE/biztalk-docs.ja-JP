---
title: 'クロス フィールド検証規則に違反しました: |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d606a80-9046-4572-9cfb-a3434ed8073e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ba6e7b5e81caf3b091c146755ba37896fb1120b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238234"
---
# <a name="cross-field-validation-rule-violated"></a><span data-ttu-id="87a8c-102">クロス フィールド検証規則に違反しました</span><span class="sxs-lookup"><span data-stu-id="87a8c-102">Cross field validation rule violated</span></span>
## <a name="details"></a><span data-ttu-id="87a8c-103">詳細</span><span class="sxs-lookup"><span data-stu-id="87a8c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="87a8c-104">製品名</span><span class="sxs-lookup"><span data-stu-id="87a8c-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="87a8c-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="87a8c-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="87a8c-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="87a8c-106">Event ID</span></span>|-|  
|<span data-ttu-id="87a8c-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="87a8c-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="87a8c-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="87a8c-108"> EDI</span></span>|  
|<span data-ttu-id="87a8c-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="87a8c-109">Component</span></span>|<span data-ttu-id="87a8c-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="87a8c-110">EDI Engine</span></span>|  
|<span data-ttu-id="87a8c-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="87a8c-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="87a8c-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="87a8c-112">Message Text</span></span>|<span data-ttu-id="87a8c-113">クロス フィールド検証規則に違反しました</span><span class="sxs-lookup"><span data-stu-id="87a8c-113">Cross field validation rule violated</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="87a8c-114">説明</span><span class="sxs-lookup"><span data-stu-id="87a8c-114">Explanation</span></span>  
 <span data-ttu-id="87a8c-115">このエラー/警告/情報イベントは、X12 インターチェンジが受信パイプラインまたは送信パイプラインでのクロスフィールド検証に失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="87a8c-115">This Error/Warning/Information event indicates that the X12 interchange failed cross-field validation in the receive pipeline or the send pipeline.</span></span> <span data-ttu-id="87a8c-116">これは、X12ConditionDesignator_Check フラグが "Yes" に設定されていて、インターチェンジの少なくとも 1 つの要素が、接頭辞 "X12ConditionDesignatorX" によって識別されたルールに違反していることを示します。</span><span class="sxs-lookup"><span data-stu-id="87a8c-116">This indicates that the X12ConditionDesignator_Check flag is set to "Yes", and that at least one element in the interchange failed a rule identified by the prefix "X12ConditionDesignatorX".</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="87a8c-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="87a8c-117">User Action</span></span>  
 <span data-ttu-id="87a8c-118">このエラーを解決するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="87a8c-118">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="87a8c-119">どのデータ要素がクロスフィールド検証ルールに違反しているかを特定します。</span><span class="sxs-lookup"><span data-stu-id="87a8c-119">Identify which data element failed a cross-field validation rule.</span></span> <span data-ttu-id="87a8c-120">インターチェンジの送信者に連絡を取り、インターチェンジを作成するときはルールに従う必要があることを通知します。</span><span class="sxs-lookup"><span data-stu-id="87a8c-120">Contact the sender of the interchange and indicate that the rule must be followed when creating the interchange.</span></span>  
  
-   <span data-ttu-id="87a8c-121">インターチェンジのスキーマを開き、検証に失敗したデータ要素の X12ConditionDesignator_Check フラグを "No" に設定します。</span><span class="sxs-lookup"><span data-stu-id="87a8c-121">Open the schema for the interchange, and set the X12ConditionDesignator_Check flag for the data element that failed validation to "No".</span></span>