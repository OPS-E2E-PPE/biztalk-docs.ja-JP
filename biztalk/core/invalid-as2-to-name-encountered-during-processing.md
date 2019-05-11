---
title: 無効な AS2 の処理中に検出名 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 84d848b5-b2a3-460d-85d4-c3576e4e3aaf
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf17c8221686562ec6cc74578d646bb832d4ea22
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330916"
---
# <a name="invalid-as2-to-name-encountered-during-processing"></a><span data-ttu-id="43d00-102">無効な AS2 の処理中に検出名</span><span class="sxs-lookup"><span data-stu-id="43d00-102">Invalid AS2-To name encountered during processing</span></span>
## <a name="details"></a><span data-ttu-id="43d00-103">詳細</span><span class="sxs-lookup"><span data-stu-id="43d00-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="43d00-104">製品名</span><span class="sxs-lookup"><span data-stu-id="43d00-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="43d00-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="43d00-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="43d00-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="43d00-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="43d00-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="43d00-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="43d00-108">EDI</span><span class="sxs-lookup"><span data-stu-id="43d00-108">EDI</span></span> |
|    <span data-ttu-id="43d00-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="43d00-109">Component</span></span>    |                                       <span data-ttu-id="43d00-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="43d00-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="43d00-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="43d00-111">Symbolic Name</span></span>  |                            <span data-ttu-id="43d00-112">InvalidAS2ToNameEncounteredError</span><span class="sxs-lookup"><span data-stu-id="43d00-112">InvalidAS2ToNameEncounteredError</span></span>                            |
|  <span data-ttu-id="43d00-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="43d00-113">Message Text</span></span>   |             <span data-ttu-id="43d00-114">無効な AS2 の処理中に発生する名前にします。</span><span class="sxs-lookup"><span data-stu-id="43d00-114">Invalid AS2-To name encountered during processing.</span></span>  <span data-ttu-id="43d00-115">値: {0}</span><span class="sxs-lookup"><span data-stu-id="43d00-115">Value: {0}</span></span>             |
  
## <a name="explanation"></a><span data-ttu-id="43d00-116">説明</span><span class="sxs-lookup"><span data-stu-id="43d00-116">Explanation</span></span>  
 <span data-ttu-id="43d00-117">このエラー/警告/情報イベントまたはを示します、受信パイプラインで受信インターチェンジを処理できなかったために、送信パイプラインは、送信インターチェンジを処理できませんでした、AS2 の値のヘッダーに準拠しないと、AS2 RFC 4130 の仕様。</span><span class="sxs-lookup"><span data-stu-id="43d00-117">This Error/Warning/Information event indicates that either the receive pipeline could not process the incoming interchange or the send pipeline could not process the outgoing interchange because the value of the AS2-To header did not conform to the specifications in AS2 RFC 4130.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="43d00-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="43d00-118">User Action</span></span>  
 <span data-ttu-id="43d00-119">このエラーを解決することを確認、AS2 の受信または送信メッセージのメッセージ ヘッダーには、AS2 RFC 4130 のセクション 6.2 の仕様に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="43d00-119">To resolve this error, make sure that the AS2-To header in the incoming or outgoing message conforms to the specifications in section 6.2 of AS2 RFC 4130.</span></span>