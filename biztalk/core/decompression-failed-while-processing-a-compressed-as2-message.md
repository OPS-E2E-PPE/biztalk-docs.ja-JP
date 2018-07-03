---
title: 圧縮された AS2 メッセージの処理中に圧縮解除が失敗しました。 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5246ee97-cc60-4878-9447-de870c0f4c34
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c77bead00b97bf6fa072223485f2d1cc422053b7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001891"
---
# <a name="decompression-failed-while-processing-a-compressed-as2-message"></a><span data-ttu-id="caf8b-103">圧縮された AS2 メッセージの処理中に圧縮解除が失敗しました。</span><span class="sxs-lookup"><span data-stu-id="caf8b-103">Decompression failed while processing a compressed AS2 message.</span></span>
## <a name="details"></a><span data-ttu-id="caf8b-104">詳細</span><span class="sxs-lookup"><span data-stu-id="caf8b-104">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="caf8b-105">製品名</span><span class="sxs-lookup"><span data-stu-id="caf8b-105">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="caf8b-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="caf8b-106">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="caf8b-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="caf8b-107">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="caf8b-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="caf8b-108">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="caf8b-109"> EDI</span><span class="sxs-lookup"><span data-stu-id="caf8b-109"> EDI</span></span> |
|    <span data-ttu-id="caf8b-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="caf8b-110">Component</span></span>    |                                       <span data-ttu-id="caf8b-111">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="caf8b-111">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="caf8b-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="caf8b-112">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="caf8b-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="caf8b-113">Message Text</span></span>   |       <span data-ttu-id="caf8b-114">圧縮された AS2 メッセージの処理中に圧縮解除が失敗しました。</span><span class="sxs-lookup"><span data-stu-id="caf8b-114">Decompression failed while processing a compressed AS2 message.</span></span> <span data-ttu-id="caf8b-115">エラー: {0}</span><span class="sxs-lookup"><span data-stu-id="caf8b-115">Error: {0}</span></span>       |
  
## <a name="explanation"></a><span data-ttu-id="caf8b-116">説明</span><span class="sxs-lookup"><span data-stu-id="caf8b-116">Explanation</span></span>  
 <span data-ttu-id="caf8b-117">このエラー/警告/情報イベントは、受信パイプラインの AS2 デコーダー コンポーネントが AS2 メッセージの圧縮を解除できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="caf8b-117">This Error/Warning/Information event indicates that the AS2 Decoder component of the receive pipeline could not decompress the AS2 message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="caf8b-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="caf8b-118">User Action</span></span>  
 <span data-ttu-id="caf8b-119">このエラーを解決するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="caf8b-119">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="caf8b-120">AS2 メッセージの圧縮ラッパーが有効であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="caf8b-120">Verify that the compression wrapper in the AS2 message is valid.</span></span>  
  
-   <span data-ttu-id="caf8b-121">”メッセージの圧縮が必要" プロパティがパーティで AS2 プロパティ ダイアログ ボックスの AS2 メッセージ送信ページとしてチェックされていることを確認することにより、BizTalk Server に対して圧縮解除が有効になっていることを確認します (オーバーライドの受信メッセージ プロパティがチェックされていることを確認します)。</span><span class="sxs-lookup"><span data-stu-id="caf8b-121">Verify that decompression is enabled for BizTalk Server by verifying that the "Message should be compressed" property is checked on the Party as AS2 Message Sender page of the AS2 Properties dialog box (if the Override inbound message properties property is checked).</span></span>  
  
-   <span data-ttu-id="caf8b-122">エラー メッセージ テキストに示されるエラーの説明を参照して、具体的な問題を特定してください。</span><span class="sxs-lookup"><span data-stu-id="caf8b-122">Use the error description provided in the error message text to identify the specific issue.</span></span>