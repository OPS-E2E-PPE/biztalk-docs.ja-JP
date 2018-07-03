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
ms.openlocfilehash: d6b9b55dc5cd61bc4c8c806f2dc42259cadf2f69
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977709"
---
# <a name="transaction-set-duplicate-control-number-found"></a><span data-ttu-id="64986-102">トランザクション セットの重複する制御番号が見つかりました</span><span class="sxs-lookup"><span data-stu-id="64986-102">Transaction Set duplicate control number found</span></span>
## <a name="details"></a><span data-ttu-id="64986-103">詳細</span><span class="sxs-lookup"><span data-stu-id="64986-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="64986-104">製品名</span><span class="sxs-lookup"><span data-stu-id="64986-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="64986-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="64986-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="64986-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="64986-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="64986-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="64986-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="64986-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="64986-108"> EDI</span></span> |
|    <span data-ttu-id="64986-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="64986-109">Component</span></span>    |                                       <span data-ttu-id="64986-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="64986-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="64986-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="64986-111">Symbolic Name</span></span>  |                          <span data-ttu-id="64986-112">X12TsDuplicateNumberFoundDescription</span><span class="sxs-lookup"><span data-stu-id="64986-112">X12TsDuplicateNumberFoundDescription</span></span>                          |
|  <span data-ttu-id="64986-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="64986-113">Message Text</span></span>   |                     <span data-ttu-id="64986-114">トランザクション セットの重複する制御番号が見つかりました</span><span class="sxs-lookup"><span data-stu-id="64986-114">Transaction Set duplicate control number found</span></span>                     |
  
## <a name="explanation"></a><span data-ttu-id="64986-115">説明</span><span class="sxs-lookup"><span data-stu-id="64986-115">Explanation</span></span>  
 <span data-ttu-id="64986-116">このエラー/警告/情報イベントは、インターチェンジのいずれかのグループ内のトランザクション セット制御番号が、そのグループ内の別のトランザクション セットの制御番号と同じであったため、受信パイプラインで受信 X12 インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="64986-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because the transaction set control number for a transaction set in a group of that interchange was the same as the control number for another transaction set in that group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="64986-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="64986-117">User Action</span></span>  
 <span data-ttu-id="64986-118">このエラーを解決するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="64986-118">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="64986-119">受信インターチェンジのトランザクション セットのトランザクション セット制御番号を変更し、グループ内でトランザクション セットの制御番号が重複しないようにします。</span><span class="sxs-lookup"><span data-stu-id="64986-119">Change the transaction set control numbers of transaction sets in incoming interchange so there are no duplicate control numbers for transaction sets in a group.</span></span>  
  
-   <span data-ttu-id="64986-120">次のようにして、重複するトランザクション セット制御番号の有無の確認を無効化します。</span><span class="sxs-lookup"><span data-stu-id="64986-120">Disable the check for duplicate transaction set control numbers as follows:</span></span>  
  
    1.  <span data-ttu-id="64986-121">BizTalk Server 管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="64986-121">Open the BizTalk Server Administration Console.</span></span>  
  
    2.  <span data-ttu-id="64986-122">インターチェンジを送信したパーティの [EDI のプロパティ] ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="64986-122">Open the EDI Properties dialog box for the party that sent the interchange.</span></span>  
  
    3.  <span data-ttu-id="64986-123">X12 インターチェンジの場合、[EDI のプロパティ] ダイアログ ボックスの [X12 インターチェンジ処理のプロパティ] ページで、[グループ内で重複している ST2 (トランザクション セット制御番号) を確認する] をオフにします。</span><span class="sxs-lookup"><span data-stu-id="64986-123">For X12 interchanges, clear the "Check for duplicate ST2 (Transaction set control number) in group" in the X12 Interchange Processing Properties Page of the EDI Properties dialog box.</span></span>  
  
    4.  <span data-ttu-id="64986-124">EDIFACT インターチェンジの場合、オフ、"チェックが重複している unh1 (トランザクション セット参照番号) グループで"EDIFACT インターチェンジ処理プロパティ ページで、[EDI のプロパティ] ダイアログ ボックスのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="64986-124">For EDIFACT interchanges, clear the "Check for duplicate UNH1 (Transaction set reference number) in group" property in the EDIFACT Interchange Processing Properties Page of the EDI Properties dialog box.</span></span>