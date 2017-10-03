---
title: "トランザクション セット制御番号シーケンスが終了パートナーと TPA の |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 67f194ca-3e0f-4ad4-8bc8-88aa7e5193a7
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40d87b1f2681bb07816721971cfbd17d2c3a0b91
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="transaction-set-control-number-sequence-exhausted-for-partner-and-tpa"></a><span data-ttu-id="323fe-102">パートナーと TPA のトランザクション セット制御番号のシーケンスが終了しました</span><span class="sxs-lookup"><span data-stu-id="323fe-102">Transaction set control number sequence exhausted for Partner and TPA</span></span>
## <a name="details"></a><span data-ttu-id="323fe-103">詳細</span><span class="sxs-lookup"><span data-stu-id="323fe-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="323fe-104">製品名</span><span class="sxs-lookup"><span data-stu-id="323fe-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="323fe-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="323fe-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="323fe-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="323fe-106">Event ID</span></span>|-|  
|<span data-ttu-id="323fe-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="323fe-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="323fe-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="323fe-108"> EDI</span></span>|  
|<span data-ttu-id="323fe-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="323fe-109">Component</span></span>|<span data-ttu-id="323fe-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="323fe-110">EDI Engine</span></span>|  
|<span data-ttu-id="323fe-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="323fe-111">Symbolic Name</span></span>|<span data-ttu-id="323fe-112">EdiControlNumberExhaustedForParty</span><span class="sxs-lookup"><span data-stu-id="323fe-112">EdiControlNumberExhaustedForParty</span></span>|  
|<span data-ttu-id="323fe-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="323fe-113">Message Text</span></span>|<span data-ttu-id="323fe-114">トランザクション セット制御番号のシーケンスが終了 TPA '{2}' の 'パートナー '{1} です。</span><span class="sxs-lookup"><span data-stu-id="323fe-114">Transaction set control number sequence exhausted for Partner '{1}' for the TPA '{2}'.</span></span> <span data-ttu-id="323fe-115">{2} - BizTalk Server 管理コンソールを使用して EDI プロパティでシーケンスをリセットします。</span><span class="sxs-lookup"><span data-stu-id="323fe-115">Reset the sequence in {2} - EDI Properties using BizTalk Server Administration.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="323fe-116">説明</span><span class="sxs-lookup"><span data-stu-id="323fe-116">Explanation</span></span>  
 <span data-ttu-id="323fe-117">このエラー/警告/情報イベントは、BizTalk Server がドキュメントのため、トランザクション セット制御の範囲が使い果たされた {2} でアグリーメントを処理することを示します。</span><span class="sxs-lookup"><span data-stu-id="323fe-117">This Error/Warning/Information event indicates BizTalk Server was not able to process the document because the Transaction set control range has been used up for the agreement in {2}.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="323fe-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="323fe-118">User Action</span></span>  
 <span data-ttu-id="323fe-119">このエラーを解決するのには、チェックを {2} アグリーメントの制御番号をリセットまたは制御番号の範囲を増やすか、アグリーメントでは、制御番号範囲指定に対するリセット ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="323fe-119">To resolve this error, please tick the checkbox to reset the control number for the {2} agreement or increase the control number range or hit the reset button against the control number range specification in the agreement.</span></span>