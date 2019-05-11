---
title: インターチェンジ構造エラーが、最初の機能グループの前に |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 12202148-0a32-464e-8dbd-d01b9ba530eb
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 051323ef4c1ff6456595e34d6989e0183f050766
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254372"
---
# <a name="the-interchange-had-a-structural-error-in-before-the-first-functional-group"></a><span data-ttu-id="b2557-102">インターチェンジ構造エラーが、最初の機能グループの前に</span><span class="sxs-lookup"><span data-stu-id="b2557-102">The interchange had a structural error in-before the first functional group</span></span>
## <a name="details"></a><span data-ttu-id="b2557-103">詳細</span><span class="sxs-lookup"><span data-stu-id="b2557-103">Details</span></span>  
  
|                 |                                                                                                                                  |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="b2557-104">製品名</span><span class="sxs-lookup"><span data-stu-id="b2557-104">Product Name</span></span>   |                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                        |
| <span data-ttu-id="b2557-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="b2557-105">Product Version</span></span> |                                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                    |
|    <span data-ttu-id="b2557-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="b2557-106">Event ID</span></span>     |                                                                -                                                                 |
|  <span data-ttu-id="b2557-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="b2557-107">Event Source</span></span>   |                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="b2557-108">EDI</span><span class="sxs-lookup"><span data-stu-id="b2557-108">EDI</span></span>                      |
|    <span data-ttu-id="b2557-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b2557-109">Component</span></span>    |                                                            <span data-ttu-id="b2557-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="b2557-110">EDI Engine</span></span>                                                            |
|  <span data-ttu-id="b2557-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="b2557-111">Symbolic Name</span></span>  |                                           <span data-ttu-id="b2557-112">X12InterchangeStructuralErrorBefore1stGroup</span><span class="sxs-lookup"><span data-stu-id="b2557-112">X12InterchangeStructuralErrorBefore1stGroup</span></span>                                            |
|  <span data-ttu-id="b2557-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="b2557-113">Message Text</span></span>   | <span data-ttu-id="b2557-114">Id を持つインターチェンジ '{0}'、送信者 id'{1}'、受信者 id '{2}' で/最初の機能グループの前に構造エラーが</span><span class="sxs-lookup"><span data-stu-id="b2557-114">The interchange with id '{0}', with sender id '{1}', receiver id '{2}' had structural error in/before the first functional group</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="b2557-115">説明</span><span class="sxs-lookup"><span data-stu-id="b2557-115">Explanation</span></span>  
 <span data-ttu-id="b2557-116">このエラー/警告/情報イベントは、次の理由の 1 つの受信のインターチェンジを受信パイプラインが処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="b2557-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange, for one of the following reasons:</span></span>  
  
-   <span data-ttu-id="b2557-117">インターチェンジ、該当するスキーマに準拠していなかったために、ISA および IEA セグメントまたはインターチェンジの最初の機能グループのいずれかで構造エラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="b2557-117">A structural error occurred in either the ISA and IEA segments or the first functional group of the interchange, so the interchange did not conform to the applicable schema.</span></span>  
  
-   <span data-ttu-id="b2557-118">(Baseartifacts.dll 内の) 内の X12ServiceSchema が展開されていません。</span><span class="sxs-lookup"><span data-stu-id="b2557-118">The X12ServiceSchema (in BaseArtifacts.dll) was not deployed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b2557-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="b2557-119">User Action</span></span>  
 <span data-ttu-id="b2557-120">このエラーを解決するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b2557-120">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="b2557-121">ISA インターチェンジ変更の送信元および IEA セグメントまたは最初の機能グループがある、該当するスキーマに準拠するようにし、インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="b2557-121">Have the sender of the interchange change the ISA and/or IEA segments or the first functional group so that it conforms to the applicable schema, and then resend the interchange.</span></span>  
  
-   <span data-ttu-id="b2557-122">BaseArtifacts.dll に X12ServiceSchema が含まれていることと、X12ServiceSchema が展開されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b2557-122">Ensure that BaseArtifacts.dll includes the X12ServiceSchema and is deployed.</span></span> <span data-ttu-id="b2557-123">これを行うには、BizTalk Server 管理コンソールを開き、開き、BizTalk EDI アプリケーション ノード、[スキーマ] ノード、X12ServiceSchema が表示されていることを確認しています。</span><span class="sxs-lookup"><span data-stu-id="b2557-123">You can do so by opening the BizTalk Server Administration Console, opening the BizTalk EDI Application node and the Schemas node, and verifying that X12ServiceSchema is listed.</span></span>