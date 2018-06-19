---
title: 'X12 の処理中にエラーが発生した送信ポートでメッセージ: 受信者および送信者 id 修飾子の組み合わせのアグリーメントがありません |。Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 72ae7926-f5c1-42f4-8c29-11f34c138dd4
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 637cd174b2c9723f4391417392700e3a4f079b79
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240858"
---
# <a name="a-failure-occurred-in-processing-x12-message-on-send-port-no-agreement-for-receiver-and-sender-identifier-qualifier-pairs"></a><span data-ttu-id="1fdb4-102">X12 の処理中にエラーが発生した送信ポートでメッセージ: 受信者および送信者 id 修飾子の組み合わせのアグリーメントがありません。</span><span class="sxs-lookup"><span data-stu-id="1fdb4-102">A failure occurred in processing X12 message on send port: No agreement for receiver and sender identifier-qualifier pairs</span></span>
## <a name="details"></a><span data-ttu-id="1fdb4-103">詳細</span><span class="sxs-lookup"><span data-stu-id="1fdb4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1fdb4-104">製品名</span><span class="sxs-lookup"><span data-stu-id="1fdb4-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="1fdb4-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="1fdb4-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="1fdb4-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="1fdb4-106">Event ID</span></span>|-|  
|<span data-ttu-id="1fdb4-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="1fdb4-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="1fdb4-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="1fdb4-108"> EDI</span></span>|  
|<span data-ttu-id="1fdb4-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1fdb4-109">Component</span></span>|<span data-ttu-id="1fdb4-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="1fdb4-110">EDI Engine</span></span>|  
|<span data-ttu-id="1fdb4-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="1fdb4-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="1fdb4-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="1fdb4-112">Message Text</span></span>|<span data-ttu-id="1fdb4-113">送信ポート {0} で X12 メッセージの処理中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="1fdb4-113">A failure occurred in processing X12 message on send port {0}.</span></span> <span data-ttu-id="1fdb4-114">{1}、{2}、{3}、{4} 受信者および送信者の id と修飾子の組み合わせのアグリーメントが存在しません。</span><span class="sxs-lookup"><span data-stu-id="1fdb4-114">No agreement exists for receiver and sender identifier/qualifier pairs for {1}, {2}, {3}, {4}.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1fdb4-115">説明</span><span class="sxs-lookup"><span data-stu-id="1fdb4-115">Explanation</span></span>  
 <span data-ttu-id="1fdb4-116">このエラー/警告/情報イベントは、BizTalk Server で、昇格した送信者の修飾子と識別子のプロパティ、および昇格した受信者の修飾子と識別子のプロパティが、パーティの対応する値と一致しなかったために、BizTalk Server で EDIFACT インターチェンジのパーティを解決できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="1fdb4-116">This Error/Warning/Information event indicates BizTalk Server was unable to resolve the party for the EDIFACT interchange because BizTalk Server was unable to match promoted sender qualifier and identifier properties, and promoted receiver qualifier and identifier properties, with the corresponding values for a party.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1fdb4-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="1fdb4-117">User Action</span></span>  
 <span data-ttu-id="1fdb4-118">このエラーを解決するには、[EDI のプロパティ] ダイアログ ボックスのパーティの [ISA セグメントの定義] ページで定義されている、送信者の修飾子と識別子 (ISA5 と ISA6) および受信者の修飾子と識別子 (ISA7 と ISA8) が、インターチェンジのコンテキストで昇格させた対応するプロパティに一致することを確認します。</span><span class="sxs-lookup"><span data-stu-id="1fdb4-118">To resolve this error, ensure that the sender qualifier and identifier (ISA5 and ISA6) and receiver qualifier and identifier (ISA7 and ISA8) defined in the party's ISA Segment Definition page of the EDI Properties dialog box match the corresponding promoted properties in the context of the interchange.</span></span>