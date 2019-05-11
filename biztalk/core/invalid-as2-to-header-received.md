---
title: 無効な AS2-To 受信ヘッダー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 56cd16b3-511b-4716-8806-817f174f0b0e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9acfbb11edabc26d1a01d36e545820892c65139
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330925"
---
# <a name="invalid-as2-to-header-received"></a><span data-ttu-id="5048e-102">無効な AS2 のヘッダーを受信しました</span><span class="sxs-lookup"><span data-stu-id="5048e-102">Invalid AS2-To header received</span></span>
## <a name="details"></a><span data-ttu-id="5048e-103">詳細</span><span class="sxs-lookup"><span data-stu-id="5048e-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="5048e-104">製品名</span><span class="sxs-lookup"><span data-stu-id="5048e-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="5048e-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="5048e-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="5048e-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="5048e-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="5048e-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="5048e-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="5048e-108">EDI</span><span class="sxs-lookup"><span data-stu-id="5048e-108">EDI</span></span> |
|    <span data-ttu-id="5048e-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5048e-109">Component</span></span>    |                                       <span data-ttu-id="5048e-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="5048e-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="5048e-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="5048e-111">Symbolic Name</span></span>  |                          <span data-ttu-id="5048e-112">InvalidAS2ToNameHeaderReceivedError</span><span class="sxs-lookup"><span data-stu-id="5048e-112">InvalidAS2ToNameHeaderReceivedError</span></span>                           |
|  <span data-ttu-id="5048e-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="5048e-113">Message Text</span></span>   |                      <span data-ttu-id="5048e-114">無効な AS2 のヘッダーを受信しました。</span><span class="sxs-lookup"><span data-stu-id="5048e-114">Invalid AS2-To header received.</span></span>  <span data-ttu-id="5048e-115">値: {0}</span><span class="sxs-lookup"><span data-stu-id="5048e-115">Value: {0}</span></span>                       |
  
## <a name="explanation"></a><span data-ttu-id="5048e-116">説明</span><span class="sxs-lookup"><span data-stu-id="5048e-116">Explanation</span></span>  
 <span data-ttu-id="5048e-117">このエラー/警告/情報イベントは、エントリのため、受信パイプラインが受信インターチェンジが処理しないことを示します、AS2 の値-メッセージのメッセージ ヘッダーに準拠していなかった AS2 RFC 4130 の仕様にします。</span><span class="sxs-lookup"><span data-stu-id="5048e-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of the AS2-To header in the message did not conform to the specifications in AS2 RFC 4130.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5048e-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="5048e-118">User Action</span></span>  
 <span data-ttu-id="5048e-119">このエラーを解決することを確認します、AS2 の値に、メッセージのヘッダーには、AS2 RFC 4130 のセクション 6.2 の仕様に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="5048e-119">To resolve this error, make sure that the value in the AS2-To header of the message conforms to the specifications in section 6.2 of AS2 RFC 4130.</span></span>