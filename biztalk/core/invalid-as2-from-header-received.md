---
title: 無効な AS2 のヘッダーを受信しました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9d773e09-8526-4533-9066-8e743e65a688
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 935995719473c8ff7977b47ec8b6971229b1a795
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381424"
---
# <a name="invalid-as2-from-header-received"></a><span data-ttu-id="16d56-102">無効な AS2 のヘッダーを受信しました</span><span class="sxs-lookup"><span data-stu-id="16d56-102">Invalid AS2-From header received</span></span>
## <a name="details"></a><span data-ttu-id="16d56-103">詳細</span><span class="sxs-lookup"><span data-stu-id="16d56-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="16d56-104">製品名</span><span class="sxs-lookup"><span data-stu-id="16d56-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="16d56-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="16d56-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="16d56-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="16d56-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="16d56-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="16d56-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="16d56-108">EDI</span><span class="sxs-lookup"><span data-stu-id="16d56-108">EDI</span></span> |
|    <span data-ttu-id="16d56-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="16d56-109">Component</span></span>    |                                       <span data-ttu-id="16d56-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="16d56-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="16d56-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="16d56-111">Symbolic Name</span></span>  |                         <span data-ttu-id="16d56-112">InvalidAS2FromNameHeaderReceivedError</span><span class="sxs-lookup"><span data-stu-id="16d56-112">InvalidAS2FromNameHeaderReceivedError</span></span>                          |
|  <span data-ttu-id="16d56-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="16d56-113">Message Text</span></span>   |                     <span data-ttu-id="16d56-114">無効な AS2 のヘッダーを受信しました。</span><span class="sxs-lookup"><span data-stu-id="16d56-114">Invalid AS2-From header received.</span></span>  <span data-ttu-id="16d56-115">値: {0}</span><span class="sxs-lookup"><span data-stu-id="16d56-115">Value: {0}</span></span>                      |
  
## <a name="explanation"></a><span data-ttu-id="16d56-116">説明</span><span class="sxs-lookup"><span data-stu-id="16d56-116">Explanation</span></span>  
 <span data-ttu-id="16d56-117">このエラー/警告/情報イベントは、エントリのため、受信パイプラインが受信インターチェンジが処理しないことを示します、AS2 の値-メッセージのメッセージ ヘッダーから準拠していなかった AS2 RFC 4130 の仕様にします。</span><span class="sxs-lookup"><span data-stu-id="16d56-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of the AS2-From header in the message did not conform to the specifications in AS2 RFC 4130.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="16d56-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="16d56-118">User Action</span></span>  
 <span data-ttu-id="16d56-119">このエラーを解決することを確認、AS2 の値-メッセージのヘッダーから、AS2 RFC 4130 のセクション 6.2 の仕様に準拠し、メッセージを再送信します。</span><span class="sxs-lookup"><span data-stu-id="16d56-119">To resolve this error, make sure that the value in the AS2-From header of the message conforms to the specifications in section 6.2 of AS2 RFC 4130, and then have the message resent.</span></span>