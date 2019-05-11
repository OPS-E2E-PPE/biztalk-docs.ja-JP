---
title: データ型のプロパティの変換 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, data type conversion
- MQBYTE property [MQSeries adapters]
- MQLONG property [MQSeries adapters]
- MQCHAR property [MQSeries adapters]
- configuring [MQSeries adapters], data type conversion
ms.assetid: 5b81eab0-f7a1-42f3-b212-a211b2893fd5
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3846fa8cb6fe30e1cae561f7652aba0a02944a28
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353040"
---
# <a name="data-type-conversion-of-properties"></a><span data-ttu-id="5500c-102">プロパティのデータ型変換</span><span class="sxs-lookup"><span data-stu-id="5500c-102">Data Type Conversion of Properties</span></span>
<span data-ttu-id="5500c-103">MQSeries メッセージ ヘッダー プロパティは、メッセージ自体に含まれているデータ構造です。</span><span class="sxs-lookup"><span data-stu-id="5500c-103">Header properties in an MQSeries message are data structures contained in the message itself.</span></span> <span data-ttu-id="5500c-104">MQSeries アダプターは自動的に検証し、メッセージを送受信するときに、MQSeries メッセージ ヘッダーで特定の値に変換します。</span><span class="sxs-lookup"><span data-stu-id="5500c-104">The MQSeries adapter automatically validates and converts certain values in MQSeries message headers when sending and receiving messages.</span></span>  
  
 <span data-ttu-id="5500c-105">次の表では、MQSeries データ型と、検証と変換について説明します。</span><span class="sxs-lookup"><span data-stu-id="5500c-105">The following table describes the MQSeries data types and their validation and conversion.</span></span>  
  
|<span data-ttu-id="5500c-106">MQSeries データ型</span><span class="sxs-lookup"><span data-stu-id="5500c-106">MQSeries data type</span></span>|<span data-ttu-id="5500c-107">検証と変換</span><span class="sxs-lookup"><span data-stu-id="5500c-107">Validation and conversion</span></span>|  
|------------------------|-------------------------------|  
|<span data-ttu-id="5500c-108">MQLONG</span><span class="sxs-lookup"><span data-stu-id="5500c-108">MQLONG</span></span>|<span data-ttu-id="5500c-109">MQSeries は、検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="5500c-109">MQSeries performs the validation.</span></span> <span data-ttu-id="5500c-110">長整数に変換します。</span><span class="sxs-lookup"><span data-stu-id="5500c-110">Converts to a long integer.</span></span> <span data-ttu-id="5500c-111">無効な値では、メッセージが MQSeries キューに移動できなくなります。</span><span class="sxs-lookup"><span data-stu-id="5500c-111">Values that are not valid prevent the message from going to the MQSeries queue.</span></span>|  
|<span data-ttu-id="5500c-112">MQCHAR</span><span class="sxs-lookup"><span data-stu-id="5500c-112">MQCHAR</span></span>|<span data-ttu-id="5500c-113">文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="5500c-113">Converts to a string.</span></span>|  
|<span data-ttu-id="5500c-114">MQBYTE</span><span class="sxs-lookup"><span data-stu-id="5500c-114">MQBYTE</span></span>|<span data-ttu-id="5500c-115">0 ~ 9 および a ~ f、または A ~ F、16 進数の値を表すを含む文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="5500c-115">Converts to a string that contains the characters 0-9 and a-f or A-F, representing the hexadecimal value of the number.</span></span>|  
  
 <span data-ttu-id="5500c-116">MQSeries プロパティの多くは、32 ビット (4 バイト) 符号なし整数です。</span><span class="sxs-lookup"><span data-stu-id="5500c-116">Many of the MQSeries properties are 32-bit (4-byte) unsigned integers.</span></span> <span data-ttu-id="5500c-117">**Uint**共通言語仕様 (CLS) ではありません-準拠型で、割り当てる必要がありますに**オブジェクト**型 .NET メソッドで使用する前にします。</span><span class="sxs-lookup"><span data-stu-id="5500c-117">Because **uint** is not a Common Language Specification (CLS)-compliant type, you must assign them to **object** types before using them in .NET methods.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5500c-118">参照</span><span class="sxs-lookup"><span data-stu-id="5500c-118">See Also</span></span>  
 <span data-ttu-id="5500c-119">[MQSeries アダプターのプロパティ](../core/mqseries-adapter-properties.md) </span><span class="sxs-lookup"><span data-stu-id="5500c-119">[MQSeries Adapter Properties](../core/mqseries-adapter-properties.md) </span></span>  
 <span data-ttu-id="5500c-120">[BizTalk Server に関連するプロパティ](../core/properties-related-to-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="5500c-120">[Properties Related to BizTalk Server](../core/properties-related-to-biztalk-server.md) </span></span>  
 [<span data-ttu-id="5500c-121">MQSeries コンテキスト プロパティ</span><span class="sxs-lookup"><span data-stu-id="5500c-121">MQSeries Context Properties</span></span>](../core/mqseries-context-properties.md)