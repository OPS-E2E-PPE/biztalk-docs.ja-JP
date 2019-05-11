---
title: トランザクション セットの重複する制御番号が見つかりました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1b2779a0-b365-4c4b-81c7-8f9284748b6e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f273d7e66f4ebe942044e30adccbc7994720a99
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279720"
---
# <a name="transaction-set-duplicate-control-number-found"></a><span data-ttu-id="0e6f4-102">トランザクション セットの重複する制御番号が見つかりました</span><span class="sxs-lookup"><span data-stu-id="0e6f4-102">Transaction Set duplicate control number found</span></span>
## <a name="details"></a><span data-ttu-id="0e6f4-103">詳細</span><span class="sxs-lookup"><span data-stu-id="0e6f4-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="0e6f4-104">製品名</span><span class="sxs-lookup"><span data-stu-id="0e6f4-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="0e6f4-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="0e6f4-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="0e6f4-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0e6f4-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="0e6f4-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="0e6f4-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="0e6f4-108">EDI</span><span class="sxs-lookup"><span data-stu-id="0e6f4-108">EDI</span></span> |
|    <span data-ttu-id="0e6f4-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0e6f4-109">Component</span></span>    |                                       <span data-ttu-id="0e6f4-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="0e6f4-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="0e6f4-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="0e6f4-111">Symbolic Name</span></span>  |                          <span data-ttu-id="0e6f4-112">X12TsDuplicateNumberFoundDescription</span><span class="sxs-lookup"><span data-stu-id="0e6f4-112">X12TsDuplicateNumberFoundDescription</span></span>                          |
|  <span data-ttu-id="0e6f4-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="0e6f4-113">Message Text</span></span>   |                     <span data-ttu-id="0e6f4-114">トランザクション セットの重複する制御番号が見つかりました</span><span class="sxs-lookup"><span data-stu-id="0e6f4-114">Transaction Set duplicate control number found</span></span>                     |
  
## <a name="explanation"></a><span data-ttu-id="0e6f4-115">説明</span><span class="sxs-lookup"><span data-stu-id="0e6f4-115">Explanation</span></span>  
 <span data-ttu-id="0e6f4-116">このエラー/警告/情報イベントは、受信パイプラインで受信を処理できなかったことを示します X12 インターチェンジのトランザクション セット制御番号のトランザクション セットのグループのため、インターチェンジは別の制御番号と同じです。トランザクションは、そのグループに設定します。</span><span class="sxs-lookup"><span data-stu-id="0e6f4-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because the transaction set control number for a transaction set in a group of that interchange was the same as the control number for another transaction set in that group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0e6f4-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="0e6f4-117">User Action</span></span>  
 <span data-ttu-id="0e6f4-118">このエラーを解決するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0e6f4-118">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="0e6f4-119">グループの変更をトランザクション セットのトランザクションの重複した制御番号がないため、受信インターチェンジのトランザクションの数を設定するコントロールを設定します。</span><span class="sxs-lookup"><span data-stu-id="0e6f4-119">Change the transaction set control numbers of transaction sets in incoming interchange so there are no duplicate control numbers for transaction sets in a group.</span></span>  
  
-   <span data-ttu-id="0e6f4-120">次のように、重複するトランザクション セット制御番号のチェックを無効にします。</span><span class="sxs-lookup"><span data-stu-id="0e6f4-120">Disable the check for duplicate transaction set control numbers as follows:</span></span>  
  
    1.  <span data-ttu-id="0e6f4-121">BizTalk Server 管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="0e6f4-121">Open the BizTalk Server Administration Console.</span></span>  
  
    2.  <span data-ttu-id="0e6f4-122">インターチェンジの送信元パーティの EDI のプロパティ ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="0e6f4-122">Open the EDI Properties dialog box for the party that sent the interchange.</span></span>  
  
    3.  <span data-ttu-id="0e6f4-123">X12 インターチェンジのチェック ボックスをオフの場合、"重複している St2 (トランザクション セット制御番号) グループで"x12 EDI のプロパティ ダイアログ ボックスの処理のプロパティ ページをインターチェンジします。</span><span class="sxs-lookup"><span data-stu-id="0e6f4-123">For X12 interchanges, clear the "Check for duplicate ST2 (Transaction set control number) in group" in the X12 Interchange Processing Properties Page of the EDI Properties dialog box.</span></span>  
  
    4.  <span data-ttu-id="0e6f4-124">EDIFACT インターチェンジの場合、オフ、"チェックが重複している unh1 (トランザクション セット参照番号) グループで"EDIFACT インターチェンジ処理プロパティ ページで、[EDI のプロパティ] ダイアログ ボックスのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="0e6f4-124">For EDIFACT interchanges, clear the "Check for duplicate UNH1 (Transaction set reference number) in group" property in the EDIFACT Interchange Processing Properties Page of the EDI Properties dialog box.</span></span>