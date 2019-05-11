---
title: 除外条件に違反しました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e508da6-7edc-45c0-a7ab-f23337dc1b54
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a69740d9d5f5514ee3fadcb76a11fe760729ca1c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388297"
---
# <a name="exclusion-condition-violated"></a><span data-ttu-id="6b5fe-102">除外条件に違反しました</span><span class="sxs-lookup"><span data-stu-id="6b5fe-102">Exclusion Condition Violated</span></span>
## <a name="details"></a><span data-ttu-id="6b5fe-103">詳細</span><span class="sxs-lookup"><span data-stu-id="6b5fe-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="6b5fe-104">製品名</span><span class="sxs-lookup"><span data-stu-id="6b5fe-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="6b5fe-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="6b5fe-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="6b5fe-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="6b5fe-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="6b5fe-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="6b5fe-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="6b5fe-108">EDI</span><span class="sxs-lookup"><span data-stu-id="6b5fe-108">EDI</span></span> |
|    <span data-ttu-id="6b5fe-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6b5fe-109">Component</span></span>    |                                       <span data-ttu-id="6b5fe-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="6b5fe-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="6b5fe-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="6b5fe-111">Symbolic Name</span></span>  |                       <span data-ttu-id="6b5fe-112">X12DeExclusionConditionViolatedDescription</span><span class="sxs-lookup"><span data-stu-id="6b5fe-112">X12DeExclusionConditionViolatedDescription</span></span>                       |
|  <span data-ttu-id="6b5fe-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="6b5fe-113">Message Text</span></span>   |       <span data-ttu-id="6b5fe-114">除外条件に違反しました。詳細については、インスタンスのフィールドの値を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b5fe-114">Exclusion Condition Violated, refer to field value in instance for details</span></span>       |
  
## <a name="explanation"></a><span data-ttu-id="6b5fe-115">説明</span><span class="sxs-lookup"><span data-stu-id="6b5fe-115">Explanation</span></span>  
 <span data-ttu-id="6b5fe-116">このエラー/警告/情報イベントは、デザイン時 (XML 検証ツール使用時) または実行時に、インスタンス内のセグメントがクロスフィールド検証の除外ルールに違反したため、受信側または送信側のいずれかで X12 インターチェンジの検証が失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="6b5fe-116">This Error/Warning/Information event indicates that validation of an X12 interchange failed either at design time (using the XML validation tool) or at run time, on either the receive side or the send side, because a segment in the instance failed a cross-field validation exclusion rule.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6b5fe-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="6b5fe-117">User Action</span></span>  
 <span data-ttu-id="6b5fe-118">このエラーを解決するには、除外ルールに違反したセグメントがクロスフィールド検証を通過するように変更されたことを確認し、検証プロセスを再度実行します。</span><span class="sxs-lookup"><span data-stu-id="6b5fe-118">To resolve this error, ensure that the segment that failed the exclusion rule is changed so that it passes cross-field validation, and then run the validation process again.</span></span>