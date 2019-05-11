---
title: トランザクション セット制御番号シーケンスがパートナーと TPA の |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67f194ca-3e0f-4ad4-8bc8-88aa7e5193a7
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89f917dc3688755816c29dea82ae153133dcca05
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279708"
---
# <a name="transaction-set-control-number-sequence-exhausted-for-partner-and-tpa"></a><span data-ttu-id="d1a14-102">トランザクション セット制御番号シーケンスがパートナーと TPA の</span><span class="sxs-lookup"><span data-stu-id="d1a14-102">Transaction set control number sequence exhausted for Partner and TPA</span></span>
## <a name="details"></a><span data-ttu-id="d1a14-103">詳細</span><span class="sxs-lookup"><span data-stu-id="d1a14-103">Details</span></span>  
  
|                 |                                                                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="d1a14-104">製品名</span><span class="sxs-lookup"><span data-stu-id="d1a14-104">Product Name</span></span>   |                                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                           |
| <span data-ttu-id="d1a14-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d1a14-105">Product Version</span></span> |                                                       [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                       |
|    <span data-ttu-id="d1a14-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d1a14-106">Event ID</span></span>     |                                                                                   -                                                                                    |
|  <span data-ttu-id="d1a14-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d1a14-107">Event Source</span></span>   |                                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="d1a14-108">EDI</span><span class="sxs-lookup"><span data-stu-id="d1a14-108">EDI</span></span>                                         |
|    <span data-ttu-id="d1a14-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d1a14-109">Component</span></span>    |                                                                               <span data-ttu-id="d1a14-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="d1a14-110">EDI Engine</span></span>                                                                               |
|  <span data-ttu-id="d1a14-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d1a14-111">Symbolic Name</span></span>  |                                                                   <span data-ttu-id="d1a14-112">EdiControlNumberExhaustedForParty</span><span class="sxs-lookup"><span data-stu-id="d1a14-112">EdiControlNumberExhaustedForParty</span></span>                                                                    |
|  <span data-ttu-id="d1a14-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d1a14-113">Message Text</span></span>   | <span data-ttu-id="d1a14-114">トランザクション セット制御番号シーケンスがパートナー '{1}'for 'TPA{2}'。</span><span class="sxs-lookup"><span data-stu-id="d1a14-114">Transaction set control number sequence exhausted for Partner '{1}' for the TPA '{2}'.</span></span> <span data-ttu-id="d1a14-115">シーケンスをリセット{2}- BizTalk Server 管理コンソールを使用して EDI のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="d1a14-115">Reset the sequence in {2} - EDI Properties using BizTalk Server Administration.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="d1a14-116">説明</span><span class="sxs-lookup"><span data-stu-id="d1a14-116">Explanation</span></span>  
 <span data-ttu-id="d1a14-117">このエラー/警告/情報イベントは、BizTalk Server がドキュメントのため、トランザクション セット制御の範囲が使用されたアグリーメントに処理することを示します{2}します。</span><span class="sxs-lookup"><span data-stu-id="d1a14-117">This Error/Warning/Information event indicates BizTalk Server was not able to process the document because the Transaction set control range has been used up for the agreement in {2}.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d1a14-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d1a14-118">User Action</span></span>  
 <span data-ttu-id="d1a14-119">このエラーを解決するのには、制御番号をリセットするチェック ボックスをオンしてください、{2}契約または増加コントロール番号の範囲または契約書に制御番号の範囲指定に対するリセット ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1a14-119">To resolve this error, please tick the checkbox to reset the control number for the {2} agreement or increase the control number range or hit the reset button against the control number range specification in the agreement.</span></span>