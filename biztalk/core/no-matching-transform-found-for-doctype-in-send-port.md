---
title: 一致する変換見つかりません DocType 送信ポートで |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 23f62ac7-3849-49fe-a765-2be72880a4c9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9668694f5cde2e99775d1392c8722bad0645b251
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966211"
---
# <a name="no-matching-transform-found-for-doctype-in-send-port"></a><span data-ttu-id="e9f84-102">送信ポートに DocType と一致する変換が見つかりません</span><span class="sxs-lookup"><span data-stu-id="e9f84-102">No matching transform found for DocType in Send Port</span></span>
## <a name="details"></a><span data-ttu-id="e9f84-103">詳細</span><span class="sxs-lookup"><span data-stu-id="e9f84-103">Details</span></span>  
  
|                 |                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="e9f84-104">製品名</span><span class="sxs-lookup"><span data-stu-id="e9f84-104">Product Name</span></span>   |           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]           |
| <span data-ttu-id="e9f84-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="e9f84-105">Product Version</span></span> |                       [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                       |
|    <span data-ttu-id="e9f84-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e9f84-106">Event ID</span></span>     |                                                   -                                                    |
|  <span data-ttu-id="e9f84-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="e9f84-107">Event Source</span></span>   |         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e9f84-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="e9f84-108"> EDI</span></span>         |
|    <span data-ttu-id="e9f84-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e9f84-109">Component</span></span>    |                                               <span data-ttu-id="e9f84-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="e9f84-110">EDI Engine</span></span>                                               |
|  <span data-ttu-id="e9f84-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="e9f84-111">Symbolic Name</span></span>  |                             <span data-ttu-id="e9f84-112">NoMatchingTransformFoundForSendPortAndDocType</span><span class="sxs-lookup"><span data-stu-id="e9f84-112">NoMatchingTransformFoundForSendPortAndDocType</span></span>                              |
|  <span data-ttu-id="e9f84-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="e9f84-113">Message Text</span></span>   | <span data-ttu-id="e9f84-114">Doctype と一致する変換が見つかりません{0}送信ポートで{1}します。</span><span class="sxs-lookup"><span data-stu-id="e9f84-114">No matching transform found for DocType {0} in Send Port {1}.</span></span> <span data-ttu-id="e9f84-115">ExplorerOM の情報と一貫性がありません。</span><span class="sxs-lookup"><span data-stu-id="e9f84-115">Inconsistent with ExplorerOM information</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="e9f84-116">説明</span><span class="sxs-lookup"><span data-stu-id="e9f84-116">Explanation</span></span>  
 <span data-ttu-id="e9f84-117">このエラーは、指定された DocType および SendPort に一致する変換が見つからなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="e9f84-117">This error indicates that a matching transform was not found for a given DocType and SendPort.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e9f84-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="e9f84-118">User Action</span></span>  
 <span data-ttu-id="e9f84-119">このエラーを解決するには、ように進めます。</span><span class="sxs-lookup"><span data-stu-id="e9f84-119">To resolve this error, proceed as follows:</span></span>  
  
1.  <span data-ttu-id="e9f84-120">BizTalk 管理コンソールを開き、変換を探してトランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="e9f84-120">Open the BizTalk Administration console, locate the transport, and right-click the transport name.</span></span>  
  
2.  <span data-ttu-id="e9f84-121">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e9f84-121">Click **Properties**.</span></span>  
  
3.  <span data-ttu-id="e9f84-122">ポートの [種類] の一覧で、正しいポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="e9f84-122">In the port Type list, select the correct port.</span></span> <span data-ttu-id="e9f84-123">クリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="e9f84-123">Click **Configure**.</span></span>  
  
4.  <span data-ttu-id="e9f84-124">[ポート名] 送信ポートのプロパティ ダイアログ ボックスでをクリックして**送信マップ**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="e9f84-124">In the [port name] Send Port Properties dialog box, click **Outbound Maps** in the left pane.</span></span>  
  
5.  <span data-ttu-id="e9f84-125">マップがここに表示されており、正しいドキュメントの種類に対応していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e9f84-125">Verify that the map is listed here and that it corresponds to the correct document type.</span></span>