---
title: インターチェンジ構造エラーが、最初の機能グループの前に |Microsoft ドキュメント
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
ms.openlocfilehash: 5d5ab490de214f53e85ea32c1b243456f837c72e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278658"
---
# <a name="the-interchange-had-a-structural-error-in-before-the-first-functional-group"></a><span data-ttu-id="973e3-102">インターチェンジ構造エラーが、最初の機能グループの前に</span><span class="sxs-lookup"><span data-stu-id="973e3-102">The interchange had a structural error in-before the first functional group</span></span>
## <a name="details"></a><span data-ttu-id="973e3-103">詳細</span><span class="sxs-lookup"><span data-stu-id="973e3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="973e3-104">製品名</span><span class="sxs-lookup"><span data-stu-id="973e3-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="973e3-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="973e3-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="973e3-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="973e3-106">Event ID</span></span>|-|  
|<span data-ttu-id="973e3-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="973e3-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="973e3-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="973e3-108"> EDI</span></span>|  
|<span data-ttu-id="973e3-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="973e3-109">Component</span></span>|<span data-ttu-id="973e3-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="973e3-110">EDI Engine</span></span>|  
|<span data-ttu-id="973e3-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="973e3-111">Symbolic Name</span></span>|<span data-ttu-id="973e3-112">X12InterchangeStructuralErrorBefore1stGroup</span><span class="sxs-lookup"><span data-stu-id="973e3-112">X12InterchangeStructuralErrorBefore1stGroup</span></span>|  
|<span data-ttu-id="973e3-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="973e3-113">Message Text</span></span>|<span data-ttu-id="973e3-114">Id '{0}'、送信者 id '{1}' で、インターチェンジ受信者 id '{2}' が最初の機能グループ内/前に、の構造のエラー</span><span class="sxs-lookup"><span data-stu-id="973e3-114">The interchange with id '{0}', with sender id '{1}', receiver id '{2}' had structural error in/before the first functional group</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="973e3-115">説明</span><span class="sxs-lookup"><span data-stu-id="973e3-115">Explanation</span></span>  
 <span data-ttu-id="973e3-116">このエラー/警告/情報イベントは、次のいずれかの理由により、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="973e3-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange, for one of the following reasons:</span></span>  
  
-   <span data-ttu-id="973e3-117">インターチェンジの ISA セグメントと IEA セグメントまたは最初の機能グループで構造エラーが発生しました。インターチェンジが該当するスキーマに準拠していません。</span><span class="sxs-lookup"><span data-stu-id="973e3-117">A structural error occurred in either the ISA and IEA segments or the first functional group of the interchange, so the interchange did not conform to the applicable schema.</span></span>  
  
-   <span data-ttu-id="973e3-118">(BaseArtifacts.dll 内の) X12ServiceSchema が展開されていません。</span><span class="sxs-lookup"><span data-stu-id="973e3-118">The X12ServiceSchema (in BaseArtifacts.dll) was not deployed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="973e3-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="973e3-119">User Action</span></span>  
 <span data-ttu-id="973e3-120">このエラーを解決するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="973e3-120">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="973e3-121">ISA セグメント、IEA セグメント、またはその両方のセグメントか最初の機能グループを、該当するスキーマに準拠するようにインターチェンジの送信者に変更してもらい、インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="973e3-121">Have the sender of the interchange change the ISA and/or IEA segments or the first functional group so that it conforms to the applicable schema, and then resend the interchange.</span></span>  
  
-   <span data-ttu-id="973e3-122">BaseArtifacts.dll に X12ServiceSchema が含まれていることと、X12ServiceSchema が展開されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="973e3-122">Ensure that BaseArtifacts.dll includes the X12ServiceSchema and is deployed.</span></span> <span data-ttu-id="973e3-123">これを行うには、BizTalk Server 管理コンソールを開き、[BizTalk EDI アプリケーション] ノードの [スキーマ] ノードを開いて、X12ServiceSchema が表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="973e3-123">You can do so by opening the BizTalk Server Administration Console, opening the BizTalk EDI Application node and the Schemas node, and verifying that X12ServiceSchema is listed.</span></span>