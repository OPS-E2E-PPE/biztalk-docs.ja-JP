---
title: Receipt-delivery-option の値が無効です |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0eed306b-0912-4694-a55c-976128117c02
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8966e3d95e89aff023300a9834ab1bca2915421f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994851"
---
# <a name="receipt-delivery-option-value-is-invalid"></a><span data-ttu-id="1cf56-102">Receipt-Delivery-Option の値が無効です</span><span class="sxs-lookup"><span data-stu-id="1cf56-102">Receipt-Delivery-Option value is invalid</span></span>
## <a name="details"></a><span data-ttu-id="1cf56-103">詳細</span><span class="sxs-lookup"><span data-stu-id="1cf56-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="1cf56-104">製品名</span><span class="sxs-lookup"><span data-stu-id="1cf56-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="1cf56-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="1cf56-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="1cf56-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="1cf56-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="1cf56-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="1cf56-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="1cf56-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="1cf56-108"> EDI</span></span> |
|    <span data-ttu-id="1cf56-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1cf56-109">Component</span></span>    |                                       <span data-ttu-id="1cf56-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="1cf56-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="1cf56-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="1cf56-111">Symbolic Name</span></span>  |                           <span data-ttu-id="1cf56-112">InvalidReceiptDeliveryOptionError</span><span class="sxs-lookup"><span data-stu-id="1cf56-112">InvalidReceiptDeliveryOptionError</span></span>                            |
|  <span data-ttu-id="1cf56-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="1cf56-113">Message Text</span></span>   |                 <span data-ttu-id="1cf56-114">Receipt-delivery-option の値:"{0}"が無効です。</span><span class="sxs-lookup"><span data-stu-id="1cf56-114">Receipt-Delivery-Option value: "{0}" is invalid.</span></span>  <span data-ttu-id="1cf56-115">{1}</span><span class="sxs-lookup"><span data-stu-id="1cf56-115">{1}</span></span>                  |
  
## <a name="explanation"></a><span data-ttu-id="1cf56-116">説明</span><span class="sxs-lookup"><span data-stu-id="1cf56-116">Explanation</span></span>  
 <span data-ttu-id="1cf56-117">このエラー/警告/情報イベントは、受信した AS2 メッセージの Receipt-Delivery-Option が有効な URL ではなく、AS2 RFC 4130 の仕様に準拠していないことを示します。</span><span class="sxs-lookup"><span data-stu-id="1cf56-117">This Error/Warning/Information event indicates that the Receipt-Delivery-Option in the received AS2 message is not a valid URL and does not conform to the specifications in the AS2 RFC 4130.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1cf56-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="1cf56-118">User Action</span></span>  
 <span data-ttu-id="1cf56-119">このエラーを解決するには、AS2 メッセージの Receipt-Delivery-Option を有効な URL を含むように変更し、AS2 RFC 4130 のセクション 7.3 の仕様に準拠するようにしてから、AS2 メッセージを再送信します。</span><span class="sxs-lookup"><span data-stu-id="1cf56-119">To resolve this error, have the Receipt-Delivery-Option in the AS2 message changed to include a valid URL and conform to the specifications in section 7.3 of the AS2 RFC 4130, and then resend the AS2 message.</span></span>