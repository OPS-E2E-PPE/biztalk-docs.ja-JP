---
title: 重複するグループ制御番号が見つかりました |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1badc033-42fd-4992-ad36-b53047ba7817
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9165414d1a9a743c77c28b087730745d3dcc4c0b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239546"
---
# <a name="duplicate-group-control-number-found"></a><span data-ttu-id="be550-102">重複するグループ制御番号が見つかりました</span><span class="sxs-lookup"><span data-stu-id="be550-102">Duplicate group control number found</span></span>
## <a name="details"></a><span data-ttu-id="be550-103">詳細</span><span class="sxs-lookup"><span data-stu-id="be550-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="be550-104">製品名</span><span class="sxs-lookup"><span data-stu-id="be550-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="be550-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="be550-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="be550-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="be550-106">Event ID</span></span>|-|  
|<span data-ttu-id="be550-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="be550-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="be550-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="be550-108"> EDI</span></span>|  
|<span data-ttu-id="be550-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="be550-109">Component</span></span>|<span data-ttu-id="be550-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="be550-110">EDI Engine</span></span>|  
|<span data-ttu-id="be550-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="be550-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="be550-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="be550-112">Message Text</span></span>|<span data-ttu-id="be550-113">重複するグループ制御番号が見つかりました</span><span class="sxs-lookup"><span data-stu-id="be550-113">Duplicate group control number found</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="be550-114">説明</span><span class="sxs-lookup"><span data-stu-id="be550-114">Explanation</span></span>  
 <span data-ttu-id="be550-115">このエラー/警告/情報イベントは、EDI 受信パイプラインの中に、以前受信したインターチェンジと同じインターチェンジ制御番号、グループ制御番号、またはトランザクション セット制御番号が含まれていたため、EDI 受信パイプラインが受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="be550-115">This Error/Warning/Information event indicates that the EDI receive pipeline could not process an incoming interchange because it had the same interchange, group, or transaction set control number as a previously received interchange.</span></span> <span data-ttu-id="be550-116">重複している制御番号のチェックが有効になっている限り、この重複はエラーになります。</span><span class="sxs-lookup"><span data-stu-id="be550-116">This will result in a failure as long as the appropriate duplicate control number checks are enabled.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="be550-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="be550-117">User Action</span></span>  
 <span data-ttu-id="be550-118">このエラーを解決するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="be550-118">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="be550-119">対応する重複した制御番号の確認が有効になっている場合は、BizTalk Server に送信したインターチェンジで前のインターチェンジと同じグループ制御番号が使用されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="be550-119">Ensure that the interchange sent to BizTalk Server does not have the same group control number as a previous interchange, if the corresponding duplicate control number check is enabled.</span></span>  
  
-   <span data-ttu-id="be550-120">重複するグループ制御番号の確認を無効化します。</span><span class="sxs-lookup"><span data-stu-id="be550-120">Disable the duplicate group control number check.</span></span> <span data-ttu-id="be550-121">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、該当するパーティを右クリックして、インターチェンジ送信者であるパーティの [EDIFACT インターチェンジ処理のプロパティ] または [X12 インターチェンジ処理のプロパティ] ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="be550-121">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the appropriate party, and open either the EDIFACT Interchange Processing Properties or the X12 Interchange Processing Properties dialog box for the party as an interchange sender.</span></span> <span data-ttu-id="be550-122">EDIFACT インターチェンジに対する確認を無効化するには、[インターチェンジ内で重複している UNG5 (グループ制御番号) を確認する] をオフにします。</span><span class="sxs-lookup"><span data-stu-id="be550-122">To disable a check for an EDIFACT interchange, clear the Check for duplicate UNG5 (Group control number) in interchange property.</span></span> <span data-ttu-id="be550-123">X12 インターチェンジに対する確認を無効化するには、[インターチェンジ内で重複している GS6 (グループ制御番号) を確認する] をオフにします。</span><span class="sxs-lookup"><span data-stu-id="be550-123">To disable a check for an X12 interchange, clear the Check for duplicate GS6 (Group control number) in interchange property.</span></span>