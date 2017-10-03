---
title: "パーティの設定の Edifact トランザクション セット制御番号の上限に達しているに受信確認の生成に失敗しました |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bcbb6374-0403-42b0-892b-b35157a2c74a
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1879d55de163615d5a4fab19cd50839e7ab2b17f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="acknowledgement-generation-has-failed-as-maximum-limit-of-edifact-transaction-set-control-number-has-been-reached-for-party-settings"></a><span data-ttu-id="f5ed5-102">パーティの設定の EDIFACT トランザクション セット制御番号が上限に到達したため、受信確認の生成に失敗しました</span><span class="sxs-lookup"><span data-stu-id="f5ed5-102">Acknowledgement generation has failed as maximum limit of Edifact transaction set control number has been reached for party settings</span></span>
## <a name="details"></a><span data-ttu-id="f5ed5-103">詳細</span><span class="sxs-lookup"><span data-stu-id="f5ed5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f5ed5-104">製品名</span><span class="sxs-lookup"><span data-stu-id="f5ed5-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="f5ed5-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f5ed5-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="f5ed5-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f5ed5-106">Event ID</span></span>|-|  
|<span data-ttu-id="f5ed5-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f5ed5-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]<span data-ttu-id="f5ed5-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="f5ed5-108"> EDI</span></span>|  
|<span data-ttu-id="f5ed5-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f5ed5-109">Component</span></span>|<span data-ttu-id="f5ed5-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="f5ed5-110">EDI Engine</span></span>|  
|<span data-ttu-id="f5ed5-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f5ed5-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="f5ed5-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f5ed5-112">Message Text</span></span>|<span data-ttu-id="f5ed5-113">パーティ {0} の EDIFACT トランザクション セット制御番号が、許容される上限に到達したため、受信確認の生成に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="f5ed5-113">Acknowledgement generation has failed as max limit of acceptable Edifact transaction set control number has reached for party {0}.</span></span> <span data-ttu-id="f5ed5-114">パートナー アグリーメント マネージャーで、[Party in sender role] の [UNH 1] フィールドに移動して、カウンターをリセットしてください。</span><span class="sxs-lookup"><span data-stu-id="f5ed5-114">Reset counter by navigating to Party in sender role screen, field UNH 1 in Partner Agreement manager.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f5ed5-115">説明</span><span class="sxs-lookup"><span data-stu-id="f5ed5-115">Explanation</span></span>  
 <span data-ttu-id="f5ed5-116">このエラー/警告/情報イベントは、受信確認のトランザクション セット参照番号 (UNH1) で入力された制御番号が UNH1 の最大許容値より大きいために、BizTalk Server が EDIFACT インターチェンジの受信確認を生成できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="f5ed5-116">This Error/Warning/Information event indicates that BizTalk Server could not generate an acknowledgment to the EDIFACT interchange because the control number that it entered in the Transaction set reference number (UNH1) of the acknowledgment is greater than the maximum value allowed for UNH1.</span></span> <span data-ttu-id="f5ed5-117">この場合、BizTalk Server は EDI パーティのプロパティを使用して受信確認を作成しました。</span><span class="sxs-lookup"><span data-stu-id="f5ed5-117">In this instance, BizTalk Server used the EDI party properties to create the acknowledgment.</span></span>  
  
 <span data-ttu-id="f5ed5-118">トランザクション セット参照番号の最大値は、参照番号で使用する桁数によって決まります。</span><span class="sxs-lookup"><span data-stu-id="f5ed5-118">The maximum value of the transaction set reference number depends upon the number of digits used for the reference number.</span></span> <span data-ttu-id="f5ed5-119">最大文字数は、参照番号が 14 文字、プレフィックスが 13 文字、サフィックスが 13 文字、3 つすべてのフィールドの組み合わせで 14 文字です。</span><span class="sxs-lookup"><span data-stu-id="f5ed5-119">The maximum number of characters is 14 for the reference number, 13 for the prefix and suffix, and 14 for all three fields combined.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f5ed5-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f5ed5-120">User Action</span></span>  
 <span data-ttu-id="f5ed5-121">このエラーを解決するには、[UNG および UNH セグメントの定義] ページのトランザクション セット参照番号 (UNH1) の参照番号フィールド (UNH1.2) を最大値よりも小さい値に設定し直します。</span><span class="sxs-lookup"><span data-stu-id="f5ed5-121">To resolve this error, reset the reference number field (UNH1.2) of the Transaction set reference number (UNH1) in the UNG and UNH Segment Definition Page to a value that is lower than the maximum limit.</span></span> <span data-ttu-id="f5ed5-122">[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 管理コンソールの [EDI のプロパティ] ダイアログ ボックスで、このプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="f5ed5-122">Set this property in the EDI Properties dialog box in the [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] Administration Console.</span></span>