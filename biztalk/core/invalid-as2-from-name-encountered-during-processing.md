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
ms.openlocfilehash: c9d007b4c20a21606b83395ef1a4d2226cca8508
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381378"
---
# <a name="invalid-as2-from-name-encountered-during-processing"></a><span data-ttu-id="a7df5-102">無効な AS2 の処理中に検出名から</span><span class="sxs-lookup"><span data-stu-id="a7df5-102">Invalid AS2-From name encountered during processing</span></span>
## <a name="details"></a><span data-ttu-id="a7df5-103">詳細</span><span class="sxs-lookup"><span data-stu-id="a7df5-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="a7df5-104">製品名</span><span class="sxs-lookup"><span data-stu-id="a7df5-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="a7df5-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="a7df5-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="a7df5-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="a7df5-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="a7df5-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="a7df5-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="a7df5-108">EDI</span><span class="sxs-lookup"><span data-stu-id="a7df5-108">EDI</span></span> |
|    <span data-ttu-id="a7df5-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a7df5-109">Component</span></span>    |                                       <span data-ttu-id="a7df5-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="a7df5-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="a7df5-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="a7df5-111">Symbolic Name</span></span>  |                           <span data-ttu-id="a7df5-112">InvalidAS2FromNameEncounteredError</span><span class="sxs-lookup"><span data-stu-id="a7df5-112">InvalidAS2FromNameEncounteredError</span></span>                           |
|  <span data-ttu-id="a7df5-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="a7df5-113">Message Text</span></span>   |            <span data-ttu-id="a7df5-114">無効な AS2 の処理中に検出名から。</span><span class="sxs-lookup"><span data-stu-id="a7df5-114">Invalid AS2-From name encountered during processing.</span></span>  <span data-ttu-id="a7df5-115">値: {0}</span><span class="sxs-lookup"><span data-stu-id="a7df5-115">Value: {0}</span></span>            |
  
## <a name="explanation"></a><span data-ttu-id="a7df5-116">説明</span><span class="sxs-lookup"><span data-stu-id="a7df5-116">Explanation</span></span>  
 <span data-ttu-id="a7df5-117">このエラー/警告/情報イベントまたはを示します、受信パイプラインで受信インターチェンジを処理できなかったために、送信パイプラインは、送信インターチェンジを処理できませんでした、AS2 の値のヘッダーに準拠しないと、AS2 RFC 4130 の仕様。</span><span class="sxs-lookup"><span data-stu-id="a7df5-117">This Error/Warning/Information event indicates that either the receive pipeline could not process the incoming interchange or the send pipeline could not process the outgoing interchange because the value of the AS2-From header did not conform to the specifications in AS2 RFC 4130.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a7df5-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="a7df5-118">User Action</span></span>  
 <span data-ttu-id="a7df5-119">このエラーを解決することを確認、AS2 の受信または送信メッセージのメッセージ ヘッダーから、AS2 RFC 4130 のセクション 6.2 の仕様に準拠し、メッセージを再送信します。</span><span class="sxs-lookup"><span data-stu-id="a7df5-119">To resolve this error, make sure that the AS2-From header in the incoming or outgoing message conforms to the specifications in section 6.2 of AS2 RFC 4130, and then have the message resent.</span></span>