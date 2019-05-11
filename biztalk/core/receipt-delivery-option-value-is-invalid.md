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
ms.openlocfilehash: f69a1f396b6b788f3aee446b5feb501eb2f59e4f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398232"
---
# <a name="receipt-delivery-option-value-is-invalid"></a><span data-ttu-id="0a7bf-102">Receipt-delivery-option の値が無効です。</span><span class="sxs-lookup"><span data-stu-id="0a7bf-102">Receipt-Delivery-Option value is invalid</span></span>
## <a name="details"></a><span data-ttu-id="0a7bf-103">詳細</span><span class="sxs-lookup"><span data-stu-id="0a7bf-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="0a7bf-104">製品名</span><span class="sxs-lookup"><span data-stu-id="0a7bf-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="0a7bf-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="0a7bf-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="0a7bf-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0a7bf-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="0a7bf-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="0a7bf-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="0a7bf-108">EDI</span><span class="sxs-lookup"><span data-stu-id="0a7bf-108">EDI</span></span> |
|    <span data-ttu-id="0a7bf-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0a7bf-109">Component</span></span>    |                                       <span data-ttu-id="0a7bf-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="0a7bf-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="0a7bf-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="0a7bf-111">Symbolic Name</span></span>  |                           <span data-ttu-id="0a7bf-112">InvalidReceiptDeliveryOptionError</span><span class="sxs-lookup"><span data-stu-id="0a7bf-112">InvalidReceiptDeliveryOptionError</span></span>                            |
|  <span data-ttu-id="0a7bf-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="0a7bf-113">Message Text</span></span>   |                 <span data-ttu-id="0a7bf-114">Receipt-delivery-option の値:"{0}"が無効です。</span><span class="sxs-lookup"><span data-stu-id="0a7bf-114">Receipt-Delivery-Option value: "{0}" is invalid.</span></span>  <span data-ttu-id="0a7bf-115">{1}</span><span class="sxs-lookup"><span data-stu-id="0a7bf-115">{1}</span></span>                  |
  
## <a name="explanation"></a><span data-ttu-id="0a7bf-116">説明</span><span class="sxs-lookup"><span data-stu-id="0a7bf-116">Explanation</span></span>  
 <span data-ttu-id="0a7bf-117">このエラー/警告/情報イベントはの Receipt-delivery-option で受信した AS2 メッセージが有効な URL ではありませんが、AS2 RFC 4130 の仕様に準拠していないことを示します。</span><span class="sxs-lookup"><span data-stu-id="0a7bf-117">This Error/Warning/Information event indicates that the Receipt-Delivery-Option in the received AS2 message is not a valid URL and does not conform to the specifications in the AS2 RFC 4130.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0a7bf-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="0a7bf-118">User Action</span></span>  
 <span data-ttu-id="0a7bf-119">このエラーを解決するのには、AS2 メッセージの有効な URL を含めると、AS2 RFC 4130 のセクション 7.3 の仕様に準拠しているし、AS2 メッセージ再送信する変更に確認メッセージの配信オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="0a7bf-119">To resolve this error, have the Receipt-Delivery-Option in the AS2 message changed to include a valid URL and conform to the specifications in section 7.3 of the AS2 RFC 4130, and then resend the AS2 message.</span></span>