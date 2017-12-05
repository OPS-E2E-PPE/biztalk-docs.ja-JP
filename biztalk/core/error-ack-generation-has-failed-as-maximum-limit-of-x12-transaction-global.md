---
title: "X12 グローバル トランザクションの上限にエラー確認の生成に失敗しました |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8bbcae14-6e5c-4f79-87c6-311b4b54c7ff
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1eaef5e736ad01a9b49a3b46188b85b85a97e06
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="error-ack-generation-has-failed-as-maximum-limit-of-x12-transaction-global"></a><span data-ttu-id="19580-102">X12 グローバル トランザクションの上限にエラー確認の生成に失敗しました</span><span class="sxs-lookup"><span data-stu-id="19580-102">Error-Ack generation has failed as maximum limit of X12 transaction-global</span></span>
## <a name="details"></a><span data-ttu-id="19580-103">詳細</span><span class="sxs-lookup"><span data-stu-id="19580-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="19580-104">製品名</span><span class="sxs-lookup"><span data-stu-id="19580-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="19580-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="19580-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="19580-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="19580-106">Event ID</span></span>|-|  
|<span data-ttu-id="19580-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="19580-107">Event Source</span></span>|<span data-ttu-id="19580-108">BizTalk Server EDI</span><span class="sxs-lookup"><span data-stu-id="19580-108">BizTalk Server EDI</span></span>|  
|<span data-ttu-id="19580-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="19580-109">Component</span></span>|<span data-ttu-id="19580-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="19580-110">EDI Engine</span></span>|  
|<span data-ttu-id="19580-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="19580-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="19580-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="19580-112">Message Text</span></span>|<span data-ttu-id="19580-113">Guest の設定の X12 トランザクション セット制御番号が、許容される上限に到達したため、受信確認の生成に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="19580-113">Acknowledgement generation has failed as max limit of acceptable X12 transaction set control number has reached for Guest settings.</span></span> <span data-ttu-id="19580-114">パートナー アグリーメント マネージャーで、[Global configuration sender role] の [ST 2] フィールドに移動して、カウンターをリセットしてください。</span><span class="sxs-lookup"><span data-stu-id="19580-114">Reset counter by navigating to Global configuration sender role screen, field ST 2 in Partner Agreement manager</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="19580-115">説明</span><span class="sxs-lookup"><span data-stu-id="19580-115">Explanation</span></span>  
 <span data-ttu-id="19580-116">このエラー/警告/情報イベントは、受信確認のトランザクション セット参照番号 (ST2) で入力された制御番号が ST2 の最大許容値より大きいために、BizTalk Server が X12 インターチェンジの受信確認を生成できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="19580-116">This Error/Warning/Information event indicates that BizTalk Server could not generate an acknowledgment to the X12 interchange because the control number that it entered in the Transaction set control number (ST2) of the acknowledgment is greater than the maximum value allowed for ST2.</span></span> <span data-ttu-id="19580-117">この場合、BizTalk Server は EDI グローバル プロパティを使用して受信確認を作成しました。</span><span class="sxs-lookup"><span data-stu-id="19580-117">In this instance, BizTalk Server used the EDI global properties to create the acknowledgment.</span></span>  
  
 <span data-ttu-id="19580-118">トランザクション セット制御番号の最大値は、制御番号で使用する桁数によって決まります。</span><span class="sxs-lookup"><span data-stu-id="19580-118">The maximum value of the transaction set control number depends upon the number of digits used for the control number.</span></span> <span data-ttu-id="19580-119">3 つのフィールドを合わせた最大長は 9 文字です。プレフィックス フィールドとサフィックス フィールドの最大長は 8 文字です。</span><span class="sxs-lookup"><span data-stu-id="19580-119">The maximum length of all three fields is 9; the maximum length of the prefix and suffix fields is 8.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="19580-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="19580-120">User Action</span></span>  
 <span data-ttu-id="19580-121">このエラーを解決するには、[GS および ST セグメントの定義] ページのトランザクション セット制御番号 (ST2) の制御番号フィールド (ST2.2) を最大値よりも小さい値に設定し直します。</span><span class="sxs-lookup"><span data-stu-id="19580-121">To resolve this error, reset the control number field (ST2.2) of the Transaction set control number (ST2) in the GS and ST Segment Definition Page to a value that is lower than the maximum limit.</span></span> <span data-ttu-id="19580-122">BizTalk Server 管理コンソールの [EDI グローバル プロパティ] ダイアログ ボックスで、このプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="19580-122">Set this property in the EDI Global Properties dialog box in the BizTalk Server Administration Console.</span></span>