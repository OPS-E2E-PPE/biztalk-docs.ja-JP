---
title: トランザクション セット制御番号の不一致 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2c4b0c3f-f3be-4c2c-8719-8e40aa7122b9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3081249fba97e9bf478c8435952c8e5c5ecb914
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279936"
---
# <a name="transaction-set-control-number-mismatch"></a><span data-ttu-id="5d1ef-102">トランザクション セット制御番号が一致していません</span><span class="sxs-lookup"><span data-stu-id="5d1ef-102">Transaction Set Control Number Mismatch</span></span>
## <a name="details"></a><span data-ttu-id="5d1ef-103">詳細</span><span class="sxs-lookup"><span data-stu-id="5d1ef-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="5d1ef-104">製品名</span><span class="sxs-lookup"><span data-stu-id="5d1ef-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="5d1ef-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="5d1ef-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="5d1ef-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="5d1ef-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="5d1ef-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="5d1ef-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="5d1ef-108">EDI</span><span class="sxs-lookup"><span data-stu-id="5d1ef-108">EDI</span></span> |
|    <span data-ttu-id="5d1ef-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5d1ef-109">Component</span></span>    |                                       <span data-ttu-id="5d1ef-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="5d1ef-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="5d1ef-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="5d1ef-111">Symbolic Name</span></span>  |                         <span data-ttu-id="5d1ef-112">X12TsControlNumberMismatchDescription</span><span class="sxs-lookup"><span data-stu-id="5d1ef-112">X12TsControlNumberMismatchDescription</span></span>                          |
|  <span data-ttu-id="5d1ef-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="5d1ef-113">Message Text</span></span>   |                        <span data-ttu-id="5d1ef-114">トランザクション セット制御番号が一致していません</span><span class="sxs-lookup"><span data-stu-id="5d1ef-114">Transaction Set Control Number Mismatch</span></span>                         |
  
## <a name="explanation"></a><span data-ttu-id="5d1ef-115">説明</span><span class="sxs-lookup"><span data-stu-id="5d1ef-115">Explanation</span></span>  
 <span data-ttu-id="5d1ef-116">このエラー/警告/情報イベントは、トランザクション セットの SE02 フィールドに含まれている制御番号と ST02 フィールド内の制御番号が一致しなかったため、EDI 受信パイプラインで受信トランザクション セットが拒否されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="5d1ef-116">This Error/Warning/Information event indicates that the EDI receive pipeline rejected the incoming transaction set because the control number contained in the SE02 field of the transaction set did not match the control number in the ST02 field.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5d1ef-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="5d1ef-117">User Action</span></span>  
 <span data-ttu-id="5d1ef-118">このエラーを解決するには、トランザクション セットの送信者に、拒否されたトランザクション セットの SE02 フィールド内の制御番号を ST02 フィールド内の制御番号と同じになるように変更してもらい、インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="5d1ef-118">To resolve this error, have the sender of the transaction set change the control number in the SE02 field of the rejected transaction set to be the same as the control number in the ST02 field, and then resend the interchange.</span></span>