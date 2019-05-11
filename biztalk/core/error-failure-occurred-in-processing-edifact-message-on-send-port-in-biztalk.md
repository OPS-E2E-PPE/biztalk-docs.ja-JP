---
title: 送信ポートで Edifact メッセージの処理中にエラーが発生しました。アグリーメント受信者および送信者 id 修飾子の組み合わせが存在しません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cffc4705-164f-4779-8f04-c6a2a7f1bbda
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c2937dc29be315ef5298b43a50ab95f52c4573a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348298"
---
# <a name="a-failure-occurred-in-processing-edifact-message-on-send-port-no-agreement-for-receiver-and-sender-identifier-qualifier-pairs"></a><span data-ttu-id="56341-102">送信ポートで Edifact メッセージの処理中にエラーが発生しました。アグリーメント受信者および送信者 id 修飾子の組み合わせが存在しません</span><span class="sxs-lookup"><span data-stu-id="56341-102">A failure occurred in processing Edifact message on send port: No agreement for receiver and sender identifier-qualifier pairs</span></span>
## <a name="details"></a><span data-ttu-id="56341-103">詳細</span><span class="sxs-lookup"><span data-stu-id="56341-103">Details</span></span>  
  
|                 |                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="56341-104">製品名</span><span class="sxs-lookup"><span data-stu-id="56341-104">Product Name</span></span>   |                                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                         |
| <span data-ttu-id="56341-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="56341-105">Product Version</span></span> |                                                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                     |
|    <span data-ttu-id="56341-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="56341-106">Event ID</span></span>     |                                                                                 -                                                                                 |
|  <span data-ttu-id="56341-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="56341-107">Event Source</span></span>   |                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="56341-108">EDI</span><span class="sxs-lookup"><span data-stu-id="56341-108">EDI</span></span>                                       |
|    <span data-ttu-id="56341-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="56341-109">Component</span></span>    |                                                                            <span data-ttu-id="56341-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="56341-110">EDI Engine</span></span>                                                                             |
|  <span data-ttu-id="56341-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="56341-111">Symbolic Name</span></span>  |                                                                                 -                                                                                 |
|  <span data-ttu-id="56341-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="56341-112">Message Text</span></span>   | <span data-ttu-id="56341-113">送信ポートで Edifact メッセージの処理中にエラーが発生しました{0}します。</span><span class="sxs-lookup"><span data-stu-id="56341-113">A failure occurred in processing Edifact message on send port {0}.</span></span> <span data-ttu-id="56341-114">受信者および送信者の識別子と修飾子の組み合わせのアグリーメントが存在しない{1}、 {2}、 {3}、{4}します。</span><span class="sxs-lookup"><span data-stu-id="56341-114">No agreement exists for receiver and sender identifier/qualifier pairs for {1}, {2}, {3}, {4}.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="56341-115">説明</span><span class="sxs-lookup"><span data-stu-id="56341-115">Explanation</span></span>  
 <span data-ttu-id="56341-116">このエラー/警告/情報イベントは、BizTalk Server が EDIFACT インターチェンジのパーティを照合できなかったため、昇格の送信者の修飾子と識別子のプロパティを解決することができませんでしたと受信者の修飾子と識別子を昇格することを示します。プロパティでは、パーティの対応する値。</span><span class="sxs-lookup"><span data-stu-id="56341-116">This Error/Warning/Information event indicates BizTalk Server was unable to resolve the party for the EDIFACT interchange because it was unable to match promoted sender qualifier and identifier properties, and promoted receiver qualifier and identifier properties, with the corresponding values for a party.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="56341-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="56341-117">User Action</span></span>  
 <span data-ttu-id="56341-118">このエラーを解決するには、一致するよう送信者の修飾子と識別子 (UNB2.1 と UNB2.2) および受信者の修飾子と識別子 (UNB3.1 と UNB3.2) が、EDI のプロパティ ダイアログ ボックスのパーティの UNB セグメントの定義 ページで定義されている、対応します。インターチェンジのコンテキストで昇格させたプロパティです。</span><span class="sxs-lookup"><span data-stu-id="56341-118">To resolve this error, ensure that the sender qualifier and identifier (UNB2.1 and UNB2.2) and receiver qualifier and identifier (UNB3.1 and UNB3.2) defined in the party's UNB Segment Definition page of the EDI Properties dialog box match the corresponding promoted properties in the context of the interchange.</span></span>