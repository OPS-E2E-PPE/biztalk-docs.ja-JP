---
title: グローバル設定の Edifact トランザクション セット制御番号の上限に達しているに受信確認の生成に失敗しました |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6adc02d7-ebc4-4da0-a19a-3a423d63499d
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5e8bf660045bbfd1fb105f2538605302b08ab95
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006499"
---
# <a name="acknowledgement-generation-has-failed-as-maximum-limit-of-edifact-transaction-set-control-number-has-been-reached-for-global-settings"></a><span data-ttu-id="c33ec-102">グローバルの設定の EDIFACT トランザクション セット制御番号が上限に到達したため、受信確認の生成に失敗しました</span><span class="sxs-lookup"><span data-stu-id="c33ec-102">Acknowledgement generation has failed as maximum limit of Edifact transaction set control number has been reached for global settings</span></span>
## <a name="details"></a><span data-ttu-id="c33ec-103">詳細</span><span class="sxs-lookup"><span data-stu-id="c33ec-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c33ec-104">製品名</span><span class="sxs-lookup"><span data-stu-id="c33ec-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="c33ec-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c33ec-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="c33ec-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c33ec-106">Event ID</span></span>|-|  
|<span data-ttu-id="c33ec-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c33ec-107">Event Source</span></span>|<span data-ttu-id="c33ec-108">BizTalk Server EDI</span><span class="sxs-lookup"><span data-stu-id="c33ec-108">BizTalk Server EDI</span></span>|  
|<span data-ttu-id="c33ec-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c33ec-109">Component</span></span>|<span data-ttu-id="c33ec-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="c33ec-110">EDI Engine</span></span>|  
|<span data-ttu-id="c33ec-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c33ec-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="c33ec-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c33ec-112">Message Text</span></span>|<span data-ttu-id="c33ec-113">Guest の設定の EDIFACT トランザクション セット制御番号が、許容される上限に到達したため、受信確認の生成に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="c33ec-113">Acknowledgement generation has failed as max limit of acceptable Edifact transaction set control number has reached for Guest settings.</span></span> <span data-ttu-id="c33ec-114">パートナー アグリーメント マネージャーで、[Global configuration sender role] の [UNH 1] フィールドに移動して、カウンターをリセットしてください。</span><span class="sxs-lookup"><span data-stu-id="c33ec-114">Reset counter by navigating to Global configuration sender role screen, field UNH 1 in Partner Agreement manager.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c33ec-115">説明</span><span class="sxs-lookup"><span data-stu-id="c33ec-115">Explanation</span></span>  
 <span data-ttu-id="c33ec-116">このエラー/警告/情報イベントは、受信確認のトランザクション セット参照番号 (UNH1) で入力された制御番号が UNH1 の最大許容値より大きいために、BizTalk Server が EDIFACT インターチェンジの受信確認を生成できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="c33ec-116">This Error/Warning/Information event indicates that BizTalk Server could not generate an acknowledgment to the EDIFACT interchange because the control number that it entered in the Transaction set reference number (UNH1) of the acknowledgment is greater than the maximum value allowed for UNH1.</span></span> <span data-ttu-id="c33ec-117">この場合、BizTalk Server は EDI グローバル プロパティを使用して受信確認を作成しました。</span><span class="sxs-lookup"><span data-stu-id="c33ec-117">In this instance, BizTalk Server used the EDI global properties to create the acknowledgment.</span></span>  
  
 <span data-ttu-id="c33ec-118">トランザクション セット参照番号の最大値は、参照番号で使用する桁数によって決まります。</span><span class="sxs-lookup"><span data-stu-id="c33ec-118">The maximum value of the transaction set reference number depends upon the number of digits used for the reference number.</span></span> <span data-ttu-id="c33ec-119">最大文字数は、参照番号が 14 文字、プレフィックスが 13 文字、サフィックスが 13 文字、3 つすべてのフィールドの組み合わせで 14 文字です。</span><span class="sxs-lookup"><span data-stu-id="c33ec-119">The maximum number of characters is 14 for the reference number, 13 for the prefix and suffix, and 14 for all three fields combined.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c33ec-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c33ec-120">User Action</span></span>  
 <span data-ttu-id="c33ec-121">このエラーを解決するには、[UNG および UNH セグメントの定義] ページのトランザクション セット参照番号 (UNH1) の参照番号フィールド (UNH1.2) を最大値よりも小さい値に設定し直します。</span><span class="sxs-lookup"><span data-stu-id="c33ec-121">To resolve this error, reset the reference number field (UNH1.2) of the Transaction set reference number (UNH1) in the UNG and UNH Segment Definition Page to a value that is lower than the maximum limit.</span></span> <span data-ttu-id="c33ec-122">BizTalk Server 管理コンソールの [EDI グローバル プロパティ] ダイアログ ボックスで、このプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="c33ec-122">Set this property in the EDI Global Properties dialog box in the BizTalk Server Administration Console.</span></span>