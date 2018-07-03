---
title: 無効な AS2 の処理中に検出名から |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ba658119-9171-4851-835c-72c188275b73
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30277473c0b5bdae8eeb3228b9f53275498842a4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975811"
---
# <a name="invalid-as2-from-name-encountered-during-processing"></a><span data-ttu-id="12794-102">処理中に無効な AS2-From 名を検出しました</span><span class="sxs-lookup"><span data-stu-id="12794-102">Invalid AS2-From name encountered during processing</span></span>
## <a name="details"></a><span data-ttu-id="12794-103">詳細</span><span class="sxs-lookup"><span data-stu-id="12794-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="12794-104">製品名</span><span class="sxs-lookup"><span data-stu-id="12794-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="12794-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="12794-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="12794-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="12794-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="12794-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="12794-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="12794-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="12794-108"> EDI</span></span> |
|    <span data-ttu-id="12794-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="12794-109">Component</span></span>    |                                       <span data-ttu-id="12794-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="12794-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="12794-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="12794-111">Symbolic Name</span></span>  |                           <span data-ttu-id="12794-112">InvalidAS2FromNameEncounteredError</span><span class="sxs-lookup"><span data-stu-id="12794-112">InvalidAS2FromNameEncounteredError</span></span>                           |
|  <span data-ttu-id="12794-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="12794-113">Message Text</span></span>   |            <span data-ttu-id="12794-114">処理中に無効な AS2-From 名を検出しました。</span><span class="sxs-lookup"><span data-stu-id="12794-114">Invalid AS2-From name encountered during processing.</span></span>  <span data-ttu-id="12794-115">値: {0}</span><span class="sxs-lookup"><span data-stu-id="12794-115">Value: {0}</span></span>            |
  
## <a name="explanation"></a><span data-ttu-id="12794-116">説明</span><span class="sxs-lookup"><span data-stu-id="12794-116">Explanation</span></span>  
 <span data-ttu-id="12794-117">このエラー/警告/情報イベントは、AS2-From ヘッダーの値が、AS2 RFC 4130 の仕様に準拠していなかったため、受信パイプラインで受信インターチェンジを処理できなかったか、または送信パイプラインで送信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="12794-117">This Error/Warning/Information event indicates that either the receive pipeline could not process the incoming interchange or the send pipeline could not process the outgoing interchange because the value of the AS2-From header did not conform to the specifications in AS2 RFC 4130.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="12794-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="12794-118">User Action</span></span>  
 <span data-ttu-id="12794-119">このエラーを解決するには、受信メッセージまたは送信メッセージの AS2-From ヘッダーが AS2 RFC 4130 のセクション 6.2 の仕様に準拠していることを確認し、メッセージを再送信してもらいます。</span><span class="sxs-lookup"><span data-stu-id="12794-119">To resolve this error, make sure that the AS2-From header in the incoming or outgoing message conforms to the specifications in section 6.2 of AS2 RFC 4130, and then have the message resent.</span></span>