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
ms.openlocfilehash: a0bc9fd8043205920f69aec2ca7efbfcc9478724
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010355"
---
# <a name="invalid-as2-to-header-received"></a><span data-ttu-id="36fdd-102">無効な AS2-To ヘッダーを受信しました</span><span class="sxs-lookup"><span data-stu-id="36fdd-102">Invalid AS2-To header received</span></span>
## <a name="details"></a><span data-ttu-id="36fdd-103">詳細</span><span class="sxs-lookup"><span data-stu-id="36fdd-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="36fdd-104">製品名</span><span class="sxs-lookup"><span data-stu-id="36fdd-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="36fdd-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="36fdd-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="36fdd-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="36fdd-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="36fdd-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="36fdd-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="36fdd-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="36fdd-108"> EDI</span></span> |
|    <span data-ttu-id="36fdd-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="36fdd-109">Component</span></span>    |                                       <span data-ttu-id="36fdd-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="36fdd-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="36fdd-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="36fdd-111">Symbolic Name</span></span>  |                          <span data-ttu-id="36fdd-112">InvalidAS2ToNameHeaderReceivedError</span><span class="sxs-lookup"><span data-stu-id="36fdd-112">InvalidAS2ToNameHeaderReceivedError</span></span>                           |
|  <span data-ttu-id="36fdd-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="36fdd-113">Message Text</span></span>   |                      <span data-ttu-id="36fdd-114">無効な AS2-To ヘッダーを受信しました。</span><span class="sxs-lookup"><span data-stu-id="36fdd-114">Invalid AS2-To header received.</span></span>  <span data-ttu-id="36fdd-115">値: {0}</span><span class="sxs-lookup"><span data-stu-id="36fdd-115">Value: {0}</span></span>                       |
  
## <a name="explanation"></a><span data-ttu-id="36fdd-116">説明</span><span class="sxs-lookup"><span data-stu-id="36fdd-116">Explanation</span></span>  
 <span data-ttu-id="36fdd-117">このエラー/警告/情報イベントは、メッセージの AS2-To ヘッダーの値が AS2 RFC 4130 の仕様に準拠していなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="36fdd-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of the AS2-To header in the message did not conform to the specifications in AS2 RFC 4130.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="36fdd-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="36fdd-118">User Action</span></span>  
 <span data-ttu-id="36fdd-119">このエラーを解決するには、メッセージの AS2-To ヘッダーの値が AS2 RFC 4130 のセクション 6.2 の仕様に準拠していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="36fdd-119">To resolve this error, make sure that the value in the AS2-To header of the message conforms to the specifications in section 6.2 of AS2 RFC 4130.</span></span>