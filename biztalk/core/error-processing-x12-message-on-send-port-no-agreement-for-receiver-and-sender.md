---
title: 'X12 の処理中にエラーが発生した送信ポートでメッセージ: 受信者および送信者 id 修飾子の組み合わせと名前のないパーティのアグリーメントがありません |。Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fdf445e8-51a3-44fb-aa71-e0b0ab9c428f
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: acb05b7795c48c161ab50ab5e79d18a225306fd2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241450"
---
# <a name="a-failure-occurred-in-processing-x12-message-on-send-port-no-agreement-for-receiver-and-sender-identifier-qualifier-pairs-and-no-party-with-name"></a><span data-ttu-id="57b4a-102">X12 の処理中にエラーが発生した送信ポートでメッセージ: 受信者および送信者 id 修飾子の組み合わせと名前のないパーティのアグリーメントがありません。</span><span class="sxs-lookup"><span data-stu-id="57b4a-102">A failure occurred in processing X12 message on send port: No agreement for receiver and sender identifier-qualifier pairs and no party with name</span></span>
## <a name="details"></a><span data-ttu-id="57b4a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="57b4a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="57b4a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="57b4a-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="57b4a-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="57b4a-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="57b4a-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="57b4a-106">Event ID</span></span>|-|  
|<span data-ttu-id="57b4a-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="57b4a-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="57b4a-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="57b4a-108"> EDI</span></span>|  
|<span data-ttu-id="57b4a-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="57b4a-109">Component</span></span>|<span data-ttu-id="57b4a-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="57b4a-110">EDI Engine</span></span>|  
|<span data-ttu-id="57b4a-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="57b4a-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="57b4a-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="57b4a-112">Message Text</span></span>|<span data-ttu-id="57b4a-113">送信ポート {0} で X12 メッセージの処理中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="57b4a-113">A failure occurred in processing X12 message on send port {0}.</span></span> <span data-ttu-id="57b4a-114">{1}、{2}、{3}、{4} 受信者および送信者の id と修飾子の組み合わせのアグリーメントが存在しません。</span><span class="sxs-lookup"><span data-stu-id="57b4a-114">No agreement exists for receiver and sender identifier/qualifier pairs for {1}, {2}, {3}, {4}.</span></span> <span data-ttu-id="57b4a-115">名 \\ 5 \\ のパーティが存在しません。</span><span class="sxs-lookup"><span data-stu-id="57b4a-115">No Party exists with name {5}.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="57b4a-116">説明</span><span class="sxs-lookup"><span data-stu-id="57b4a-116">Explanation</span></span>  
 <span data-ttu-id="57b4a-117">このエラー/警告/情報イベントは、BizTalk Server で、昇格した送信者の修飾子と識別子のプロパティ、および昇格した受信者の修飾子と識別子のプロパティが、パーティの対応する値と一致しなかったために、BizTalk Server で EDIFACT インターチェンジのパーティを解決できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="57b4a-117">This Error/Warning/Information event indicates BizTalk Server was unable to resolve the party for the EDIFACT interchange because BizTalk Server was unable to match promoted sender qualifier and identifier properties, and promoted receiver qualifier and identifier properties, with the corresponding values for a party.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="57b4a-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="57b4a-118">User Action</span></span>  
 <span data-ttu-id="57b4a-119">このエラーを解決するには、[EDI のプロパティ] ダイアログ ボックスのパーティの [ISA セグメントの定義] ページで定義されている、送信者の修飾子と識別子 (ISA5 と ISA6) および受信者の修飾子と識別子 (ISA7 と ISA8) が、インターチェンジのコンテキストで昇格させた対応するプロパティに一致することを確認します。</span><span class="sxs-lookup"><span data-stu-id="57b4a-119">To resolve this error, ensure that the sender qualifier and identifier (ISA5 and ISA6) and receiver qualifier and identifier (ISA7 and ISA8) defined in the party's ISA Segment Definition page of the EDI Properties dialog box match the corresponding promoted properties in the context of the interchange.</span></span>