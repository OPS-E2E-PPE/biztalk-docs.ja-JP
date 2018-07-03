---
title: Edifact インターチェンジの必要がありますが含まれている TransactionSetGroup または FunctionalGroup Xml タグ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 34318133-211f-422d-acdf-b841ece5d2b0
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5736a9146a88dd9c9dac6747e381fccc88f18d9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979331"
---
# <a name="edifact-interchange-should-have-contained-transactionsetgroup-or-functionalgroup-xml-tags"></a><span data-ttu-id="43111-102">EDIFACT インターチェンジには TransactionSetGroup または FunctionalGroup XML タグが含まれている必要があります</span><span class="sxs-lookup"><span data-stu-id="43111-102">Edifact interchange should have contained TransactionSetGroup or FunctionalGroup Xml tags</span></span>
## <a name="details"></a><span data-ttu-id="43111-103">詳細</span><span class="sxs-lookup"><span data-stu-id="43111-103">Details</span></span>  
  
|                 |                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------|
|  <span data-ttu-id="43111-104">製品名</span><span class="sxs-lookup"><span data-stu-id="43111-104">Product Name</span></span>   |    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]     |
| <span data-ttu-id="43111-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="43111-105">Product Version</span></span> |                [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                 |
|    <span data-ttu-id="43111-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="43111-106">Event ID</span></span>     |                                             -                                             |
|  <span data-ttu-id="43111-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="43111-107">Event Source</span></span>   |  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="43111-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="43111-108"> EDI</span></span>   |
|    <span data-ttu-id="43111-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="43111-109">Component</span></span>    |                                        <span data-ttu-id="43111-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="43111-110">EDI Engine</span></span>                                         |
|  <span data-ttu-id="43111-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="43111-111">Symbolic Name</span></span>  |                                             -                                             |
|  <span data-ttu-id="43111-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="43111-112">Message Text</span></span>   | <span data-ttu-id="43111-113">EDIFACT インターチェンジには TransactionSetGroup または FunctionalGroup XML タグが含まれている必要があります</span><span class="sxs-lookup"><span data-stu-id="43111-113">Edifact interchange should have contained TransactionSetGroup or FunctionalGroup Xml tags</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="43111-114">説明</span><span class="sxs-lookup"><span data-stu-id="43111-114">Explanation</span></span>  
 <span data-ttu-id="43111-115">このエラー/警告/情報イベントは、TransactionSetGroup または FunctionalGroup タグがインターチェンジ XML ファイルに含まれていなかったため、送信パイプラインが保存された EDIFACT バッチ インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="43111-115">This Error/Warning/Information event indicates that the send pipeline could not process an EDIFACT batched interchange that was preserved because the TransactionSetGroup or FunctionalGroup tags were not included in the interchange XML file.</span></span>  
  
 <span data-ttu-id="43111-116">BizTalk が保存されているバッチ インターチェンジを処理する場合、インターチェンジの XML ファイルで、トランザクション セットのグループまたはグループのグループに XML タグが付与されます。</span><span class="sxs-lookup"><span data-stu-id="43111-116">When BizTalk processes a batched interchange that is preserved, a group of transaction sets or a group of groups in the interchange's XML file are given an XML tag.</span></span> <span data-ttu-id="43111-117">トランザクション セットのグループには TransactionSetGroup タグが設定されます。</span><span class="sxs-lookup"><span data-stu-id="43111-117">A group of transaction sets is given the TransactionSetGroup tag.</span></span> <span data-ttu-id="43111-118">グループのグループには、FunctionalGroup タグが付与されます。</span><span class="sxs-lookup"><span data-stu-id="43111-118">A group of groups is given the FunctionalGroup tag.</span></span> <span data-ttu-id="43111-119">このエラー状態は、受信パイプラインとパススルー送信パイプラインを使用して、保存されたバッチを設定する場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="43111-119">This error condition occurs if you set up a preserved batch using a receive pipeline and a passthrough transmit send pipeline.</span></span> <span data-ttu-id="43111-120">タグは受信パイプラインによって設定され、送信パイプラインによって除去されます。</span><span class="sxs-lookup"><span data-stu-id="43111-120">The tags are set by the receive pipeline and stripped out by the send pipeline.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="43111-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="43111-121">User Action</span></span>  
 <span data-ttu-id="43111-122">このエラーを解決するには、保存されたバッチ用に生成された XML ファイルで、TransactionSetGroup タグ (複数のトランザクション セットがあるグループ用)、FunctionalGroup タグ (複数のグループ用)、またはその両方に整形式の XML 構造が使用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="43111-122">To resolve this error, ensure that the XML file generated for the preserved batch has a well-formed XML structure with the TransactionSetGroup tag (for a group with multiple transaction sets) and/or the FunctionalGroup tag (for multiple groups).</span></span>