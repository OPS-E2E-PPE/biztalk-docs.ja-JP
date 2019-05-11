---
title: 状態レポートを有効にするには実行&#39;BizTalk Server 構成&#39;および EDI AS2 状態レポート機能の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bf125919-80ab-4cb8-b1f5-0f2616cc6f5c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96b885b9fcf16929a8f6ac064fbbf56354c7e1e7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254530"
---
# <a name="to-enable-status-reporting-run-39biztalk-server-configuration39-and-configure-edi-as2-status-reporting-feature"></a><span data-ttu-id="10710-102">状態レポートを有効にするには実行&#39;BizTalk Server 構成&#39;および EDI AS2 状態レポート機能の構成</span><span class="sxs-lookup"><span data-stu-id="10710-102">To enable status reporting, run &#39;BizTalk Server Configuration&#39; and configure EDI-AS2 status reporting feature</span></span>
## <a name="details"></a><span data-ttu-id="10710-103">詳細</span><span class="sxs-lookup"><span data-stu-id="10710-103">Details</span></span>  
  
|                 |                                                                                                                |
|-----------------|----------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="10710-104">製品名</span><span class="sxs-lookup"><span data-stu-id="10710-104">Product Name</span></span>   |               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]               |
| <span data-ttu-id="10710-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="10710-105">Product Version</span></span> |                           [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                           |
|    <span data-ttu-id="10710-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="10710-106">Event ID</span></span>     |                                                       -                                                        |
|  <span data-ttu-id="10710-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="10710-107">Event Source</span></span>   |             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="10710-108">EDI</span><span class="sxs-lookup"><span data-stu-id="10710-108">EDI</span></span>             |
|    <span data-ttu-id="10710-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="10710-109">Component</span></span>    |                                                   <span data-ttu-id="10710-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="10710-110">EDI Engine</span></span>                                                   |
|  <span data-ttu-id="10710-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="10710-111">Symbolic Name</span></span>  |                                                       <span data-ttu-id="10710-112">0</span><span class="sxs-lookup"><span data-stu-id="10710-112">0</span></span>                                                        |
|  <span data-ttu-id="10710-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="10710-113">Message Text</span></span>   | <span data-ttu-id="10710-114">状態レポートを有効にするには、'BizTalk Server 構成' を実行し、EDI/AS2 状態レポート機能を構成してください。</span><span class="sxs-lookup"><span data-stu-id="10710-114">To enable status reporting, run 'BizTalk Server Configuration' and configure EDI/AS2 status reporting feature.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="10710-115">説明</span><span class="sxs-lookup"><span data-stu-id="10710-115">Explanation</span></span>  
 <span data-ttu-id="10710-116">このエラー/警告/情報イベントは、EDI/AS2 状態レポートが構成されていないため、レポートが動作していないことを示します。</span><span class="sxs-lookup"><span data-stu-id="10710-116">This Error/Warning/Information event indicates that EDI/AS2 status reporting is not working because it has not been configured.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="10710-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="10710-117">User Action</span></span>  
 <span data-ttu-id="10710-118">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="10710-118">To resolve this error, do the following:</span></span>  
  
1.  <span data-ttu-id="10710-119">BizTalk Server 構成ウィザードを実行します。</span><span class="sxs-lookup"><span data-stu-id="10710-119">Run the BizTalk Server Configuration wizard.</span></span> <span data-ttu-id="10710-120">[BizTalk EDI/AS2 ランタイム] ノードをクリックし、[この BizTalk グループの BizTalk EDI/AS2 ランタイム状態レポートを有効にする] プロパティをオンにします。</span><span class="sxs-lookup"><span data-stu-id="10710-120">Click the BizTalk EDI/AS2 Runtime node, and check the "Enable BizTalk EDI/AS2 Runtime Status Reporting for this BizTalk Group" property.</span></span> <span data-ttu-id="10710-121">EDI/AS2 状態レポートを構成するには、BAM を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10710-121">You must configure BAM in order to configure EDI/AS2 status reporting.</span></span>  
  
2.  <span data-ttu-id="10710-122">BizTalk Server 管理コンソールで、[EDI のプロパティ] ダイアログ ボックスの [全般] ページの [EDI レポートをアクティブにする] プロパティをクリックして、パーティの EDI 状態レポートを有効にします。</span><span class="sxs-lookup"><span data-stu-id="10710-122">In the BizTalk Server Administration Console, enable EDI status reporting for the party by clicking the "Activate EDI reporting" property in the General page of the EDI Properties dialog box.</span></span> <span data-ttu-id="10710-123">[AS2 のプロパティ] ダイアログ ボックスの [全般] ページの [AS レポートをアクティブにする] プロパティをクリックして、パーティの AS2 状態レポートを有効にします。</span><span class="sxs-lookup"><span data-stu-id="10710-123">Enable AS2 status reporting for the party by clicking the "Activate AS2 reporting" property in the General page of the AS2 Properties dialog box.</span></span> <span data-ttu-id="10710-124">EDI または AS2 状態レポートを有効にした後に、BizTalk サービスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10710-124">You must restart the BizTalk service after enabling EDI or AS2 status reporting.</span></span>