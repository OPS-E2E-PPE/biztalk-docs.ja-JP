---
title: "X12 の上限にエラー確認の生成に失敗しましたトランザクション パーティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c78a7cef-24ae-4d09-9043-2f53c301302d
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5b82a8251504e1f9ff7b62c4e1cc813d4740a83
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error-ack-generation-has-failed-as-maximum-limit-of-x12-transaction-party"></a><span data-ttu-id="ad9e8-102">X12 の上限にエラー確認の生成に失敗しましたトランザクション パーティ</span><span class="sxs-lookup"><span data-stu-id="ad9e8-102">Error-Ack generation has failed as maximum limit of X12 transaction-party</span></span>
## <a name="details"></a><span data-ttu-id="ad9e8-103">詳細</span><span class="sxs-lookup"><span data-stu-id="ad9e8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ad9e8-104">製品名</span><span class="sxs-lookup"><span data-stu-id="ad9e8-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="ad9e8-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="ad9e8-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="ad9e8-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ad9e8-106">Event ID</span></span>|-|  
|<span data-ttu-id="ad9e8-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="ad9e8-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]<span data-ttu-id="ad9e8-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="ad9e8-108"> EDI</span></span>|  
|<span data-ttu-id="ad9e8-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ad9e8-109">Component</span></span>|<span data-ttu-id="ad9e8-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="ad9e8-110">EDI Engine</span></span>|  
|<span data-ttu-id="ad9e8-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="ad9e8-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="ad9e8-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="ad9e8-112">Message Text</span></span>|<span data-ttu-id="ad9e8-113">パーティ {0} の X12 トランザクション セット制御番号が、許容される上限に到達したため、受信確認の生成に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="ad9e8-113">Acknowledgement generation has failed as max limit of acceptable X12 transaction set control number has reached for party {0}.</span></span> <span data-ttu-id="ad9e8-114">パートナー アグリーメント マネージャーで、[Party in sender role] の [ST 2] フィールドに移動して、カウンターをリセットしてください。</span><span class="sxs-lookup"><span data-stu-id="ad9e8-114">Reset counter by navigating to Party in sender role screen, field ST 2 in Partner Agreement manager.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ad9e8-115">説明</span><span class="sxs-lookup"><span data-stu-id="ad9e8-115">Explanation</span></span>  
 <span data-ttu-id="ad9e8-116">このエラー/警告/情報イベントは、受信確認のトランザクション セット参照番号 (ST2) で入力された制御番号が ST2 の最大許容値より大きいために、BizTalk Server が X12 インターチェンジの受信確認を生成できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="ad9e8-116">This Error/Warning/Information event indicates that BizTalk Server could not generate an acknowledgment to the X12 interchange because the control number that it entered in the Transaction set control number (ST2) of the acknowledgment is greater than the maximum value allowed for ST2.</span></span> <span data-ttu-id="ad9e8-117">この場合、BizTalk Server は EDI パーティのプロパティを使用して受信確認を作成しました。</span><span class="sxs-lookup"><span data-stu-id="ad9e8-117">In this instance, BizTalk Server used the EDI party properties to create the acknowledgment.</span></span>  
  
 <span data-ttu-id="ad9e8-118">トランザクション セット制御番号の最大値は、制御番号で使用する桁数によって決まります。</span><span class="sxs-lookup"><span data-stu-id="ad9e8-118">The maximum value of the transaction set control number depends upon the number of digits used for the control number.</span></span> <span data-ttu-id="ad9e8-119">3 つのフィールドを合わせた最大長は 9 文字です。プレフィックス フィールドとサフィックス フィールドの最大長は 8 文字です。</span><span class="sxs-lookup"><span data-stu-id="ad9e8-119">The maximum length of all three fields is 9; the maximum length of the prefix and suffix fields is 8.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ad9e8-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="ad9e8-120">User Action</span></span>  
 <span data-ttu-id="ad9e8-121">このエラーを解決するには、[GS および ST セグメントの定義] ページのトランザクション セット制御番号 (ST2) の制御番号フィールド (ST2.2) を最大値よりも小さい値に設定し直します。</span><span class="sxs-lookup"><span data-stu-id="ad9e8-121">To resolve this error, reset the control number field (ST2.2) of the Transaction set control number (ST2) in the GS and ST Segment Definition Page to a value that is lower than the maximum limit.</span></span> <span data-ttu-id="ad9e8-122">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールの [EDI グローバル プロパティ] ダイアログ ボックスでこのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="ad9e8-122">Set this property in the EDI Global Properties dialog box in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>