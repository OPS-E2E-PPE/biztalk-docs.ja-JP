---
title: 制御番号が重複しています |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 331ad173-29b3-427c-8104-60d80c580a5a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3f4e58a6a26390b10d5cc3b4956c1b2fd0864c1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350760"
---
# <a name="duplicate-control-number"></a><span data-ttu-id="5e46a-102">制御番号が重複しています</span><span class="sxs-lookup"><span data-stu-id="5e46a-102">Duplicate Control Number</span></span>
## <a name="details"></a><span data-ttu-id="5e46a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="5e46a-103">Details</span></span>  

|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="5e46a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="5e46a-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="5e46a-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="5e46a-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="5e46a-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="5e46a-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="5e46a-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="5e46a-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="5e46a-108">EDI</span><span class="sxs-lookup"><span data-stu-id="5e46a-108">EDI</span></span> |
|    <span data-ttu-id="5e46a-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5e46a-109">Component</span></span>    |                                       <span data-ttu-id="5e46a-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="5e46a-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="5e46a-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="5e46a-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="5e46a-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="5e46a-112">Message Text</span></span>   |                                <span data-ttu-id="5e46a-113">制御番号が重複しています</span><span class="sxs-lookup"><span data-stu-id="5e46a-113">Duplicate Control Number</span></span>                                |

## <a name="explanation"></a><span data-ttu-id="5e46a-114">説明</span><span class="sxs-lookup"><span data-stu-id="5e46a-114">Explanation</span></span>  
 <span data-ttu-id="5e46a-115">このエラー/警告/情報イベントは、EDI 受信パイプラインの中に、以前受信したインターチェンジと同じインターチェンジ制御番号、グループ制御番号、またはトランザクション セット制御番号が含まれていたため、EDI 受信パイプラインが受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="5e46a-115">This Error/Warning/Information event indicates that the EDI receive pipeline could not process an incoming interchange because it had the same interchange, group, or transaction set control number as a previously received interchange.</span></span> <span data-ttu-id="5e46a-116">重複している制御番号のチェックが有効になっている限り、この重複はエラーになります。</span><span class="sxs-lookup"><span data-stu-id="5e46a-116">This will result in a failure as long as the appropriate duplicate control number checks are enabled.</span></span>  

## <a name="user-action"></a><span data-ttu-id="5e46a-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="5e46a-117">User Action</span></span>  
 <span data-ttu-id="5e46a-118">このエラーを解決するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5e46a-118">To resolve this error, do one of the following:</span></span>  

- <span data-ttu-id="5e46a-119">対応する重複した制御番号の確認が有効になっている場合は、BizTalk Server に送信したインターチェンジで前のインターチェンジと同じインターチェンジ制御番号、グループ制御番号、またはトランザクション セット制御番号が使用されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="5e46a-119">Ensure that the interchange sent to BizTalk Server does not have the same interchange, group, or transaction set control number as a previous interchange, if the corresponding duplicate control number check is enabled.</span></span>  

- <span data-ttu-id="5e46a-120">重複する制御番号の確認を無効化します。</span><span class="sxs-lookup"><span data-stu-id="5e46a-120">Disable the duplicate control number check.</span></span> <span data-ttu-id="5e46a-121">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、該当するパーティを右クリックして、インターチェンジ送信者であるパーティの [EDIFACT インターチェンジ処理のプロパティ] または [X12 インターチェンジ処理のプロパティ] ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="5e46a-121">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the appropriate party, and open either the EDIFACT Interchange Processing Properties or the X12 Interchange Processing Properties dialog box for the party as an interchange sender.</span></span> <span data-ttu-id="5e46a-122">EDIFACT インターチェンジに対する確認を無効化するには、[重複している UNB5 (インターチェンジ制御番号) を確認する]、[インターチェンジ内で重複している UNG5 (グループ制御番号) を確認する]、[グループ内で重複している UNH1 (トランザクション セット参照番号) を確認する] のいずれかのプロパティをオフにします。</span><span class="sxs-lookup"><span data-stu-id="5e46a-122">To disable a check for an EDIFACT interchange, clear the Check for duplicate UNB5 (Interchange control number), Check for duplicate UNG5 (Group control number) in interchange, or Check for duplicate UNH1 (Transaction set reference number) in group property.</span></span> <span data-ttu-id="5e46a-123">X12 インターチェンジに対する確認を無効化するには、[重複している ISA13 (インターチェンジ制御番号) を確認する]、[インターチェンジ内で重複している GS6 (グループ制御番号) を確認する]、[グループ内で重複している ST2 (トランザクション セット制御番号] のいずれかのプロパティをオフにします。</span><span class="sxs-lookup"><span data-stu-id="5e46a-123">To disable a check for an X12 interchange, clear the Check for duplicate ISA13 (Interchange control number), Check for duplicate GS6 (Group control number) in interchange, or Check for duplicate ST2 (Transaction set control number) in group property.</span></span>
