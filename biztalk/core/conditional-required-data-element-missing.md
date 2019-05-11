---
title: 条件付きの必須データ要素がありません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5105c03-fa26-4c38-a276-c656f3076d5f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68e67804d10a1fc3f920f3fadfdfc3a0aff81cae
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356524"
---
# <a name="conditional-required-data-element-missing"></a><span data-ttu-id="a94d4-102">必須の条件付きデータ要素がありません</span><span class="sxs-lookup"><span data-stu-id="a94d4-102">Conditional required data element missing</span></span>
## <a name="details"></a><span data-ttu-id="a94d4-103">詳細</span><span class="sxs-lookup"><span data-stu-id="a94d4-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="a94d4-104">製品名</span><span class="sxs-lookup"><span data-stu-id="a94d4-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="a94d4-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="a94d4-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="a94d4-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="a94d4-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="a94d4-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="a94d4-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="a94d4-108">EDI</span><span class="sxs-lookup"><span data-stu-id="a94d4-108">EDI</span></span> |
|    <span data-ttu-id="a94d4-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a94d4-109">Component</span></span>    |                                       <span data-ttu-id="a94d4-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="a94d4-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="a94d4-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="a94d4-111">Symbolic Name</span></span>  |                 <span data-ttu-id="a94d4-112">X12DeConditionalRequiredDataElementMissingDescription</span><span class="sxs-lookup"><span data-stu-id="a94d4-112">X12DeConditionalRequiredDataElementMissingDescription</span></span>                  |
|  <span data-ttu-id="a94d4-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="a94d4-113">Message Text</span></span>   |                       <span data-ttu-id="a94d4-114">必須の条件付きデータ要素がありません</span><span class="sxs-lookup"><span data-stu-id="a94d4-114">Conditional required data element missing</span></span>                        |
  
## <a name="explanation"></a><span data-ttu-id="a94d4-115">説明</span><span class="sxs-lookup"><span data-stu-id="a94d4-115">Explanation</span></span>  
 <span data-ttu-id="a94d4-116">このエラー/警告/情報イベントは、X12ConditionDesignatorX ルールで必要になるデータ要素がインターチェンジに存在していないため、EDI 受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="a94d4-116">This Error/Warning/Information event indicates that the EDI receive pipeline could not process the incoming interchange because a data element that is required by the X12ConditionDesignatorX rule does not exist in the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a94d4-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="a94d4-117">User Action</span></span>  
 <span data-ttu-id="a94d4-118">このエラーは、BizTalk Server の構成や操作ではなく、受信インターチェンジの問題である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a94d4-118">This error is likely an issue with the incoming interchange, not with the configuration or operation of BizTalk Server.</span></span> <span data-ttu-id="a94d4-119">このエラーを解決するには、インターチェンジの送信者に連絡し、インターチェンジに使用されている文字または UNB1.1 フィールドで識別されている文字セットのどちらかを変更し、それらを一致させる必要があることを伝えます。</span><span class="sxs-lookup"><span data-stu-id="a94d4-119">To resolve this error, contact the sender of the interchange and indicate that they need to change either the characters used in the interchange or the character set identified in field UNB1.1 so that they match.</span></span>