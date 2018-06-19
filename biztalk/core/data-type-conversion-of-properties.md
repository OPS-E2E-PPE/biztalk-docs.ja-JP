---
title: データ型のプロパティの変換 |Microsoft ドキュメント
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
ms.openlocfilehash: 3705f1d0a20a48f0683a15588891ef3fe60889cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238666"
---
# <a name="data-type-conversion-of-properties"></a><span data-ttu-id="b7e5e-102">プロパティのデータ型の変換</span><span class="sxs-lookup"><span data-stu-id="b7e5e-102">Data Type Conversion of Properties</span></span>
<span data-ttu-id="b7e5e-103">MQSeries メッセージのヘッダー プロパティは、そのメッセージ自体に含まれているデータ構造です。</span><span class="sxs-lookup"><span data-stu-id="b7e5e-103">Header properties in an MQSeries message are data structures contained in the message itself.</span></span> <span data-ttu-id="b7e5e-104">MQSeries アダプタでは、メッセージの送受信時に MQSeries メッセージ ヘッダーの特定の値を自動的に検証および変換します。</span><span class="sxs-lookup"><span data-stu-id="b7e5e-104">The MQSeries adapter automatically validates and converts certain values in MQSeries message headers when sending and receiving messages.</span></span>  
  
 <span data-ttu-id="b7e5e-105">次の表では、MQSeries データ型と、それらの検証および変換について説明します。</span><span class="sxs-lookup"><span data-stu-id="b7e5e-105">The following table describes the MQSeries data types and their validation and conversion.</span></span>  
  
|<span data-ttu-id="b7e5e-106">MQSeries データ型</span><span class="sxs-lookup"><span data-stu-id="b7e5e-106">MQSeries data type</span></span>|<span data-ttu-id="b7e5e-107">検証と変換</span><span class="sxs-lookup"><span data-stu-id="b7e5e-107">Validation and conversion</span></span>|  
|------------------------|-------------------------------|  
|<span data-ttu-id="b7e5e-108">MQLONG</span><span class="sxs-lookup"><span data-stu-id="b7e5e-108">MQLONG</span></span>|<span data-ttu-id="b7e5e-109">MQSeries によって検証が行われます。</span><span class="sxs-lookup"><span data-stu-id="b7e5e-109">MQSeries performs the validation.</span></span> <span data-ttu-id="b7e5e-110">長整数に変換されます。</span><span class="sxs-lookup"><span data-stu-id="b7e5e-110">Converts to a long integer.</span></span> <span data-ttu-id="b7e5e-111">値が無効である場合、メッセージは MQSeries キューに送信されません。</span><span class="sxs-lookup"><span data-stu-id="b7e5e-111">Values that are not valid prevent the message from going to the MQSeries queue.</span></span>|  
|<span data-ttu-id="b7e5e-112">MQCHAR</span><span class="sxs-lookup"><span data-stu-id="b7e5e-112">MQCHAR</span></span>|<span data-ttu-id="b7e5e-113">文字列に変換されます。</span><span class="sxs-lookup"><span data-stu-id="b7e5e-113">Converts to a string.</span></span>|  
|<span data-ttu-id="b7e5e-114">MQBYTE</span><span class="sxs-lookup"><span data-stu-id="b7e5e-114">MQBYTE</span></span>|<span data-ttu-id="b7e5e-115">数字の 16 進値を表す、文字 0 ～ 9、a ～ f、または A ～ F が含まれた文字列に変換されます。</span><span class="sxs-lookup"><span data-stu-id="b7e5e-115">Converts to a string that contains the characters 0-9 and a-f or A-F, representing the hexadecimal value of the number.</span></span>|  
  
 <span data-ttu-id="b7e5e-116">ほとんどの MQSeries プロパティは、32 ビット (4 バイト) の符号なし整数です。</span><span class="sxs-lookup"><span data-stu-id="b7e5e-116">Many of the MQSeries properties are 32-bit (4-byte) unsigned integers.</span></span> <span data-ttu-id="b7e5e-117">**Uint**共通言語仕様 (CLS) ではありません-準拠型で、割り当てる必要がありますに**オブジェクト**.NET メソッドで使用する前に型です。</span><span class="sxs-lookup"><span data-stu-id="b7e5e-117">Because **uint** is not a Common Language Specification (CLS)-compliant type, you must assign them to **object** types before using them in .NET methods.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7e5e-118">参照</span><span class="sxs-lookup"><span data-stu-id="b7e5e-118">See Also</span></span>  
 <span data-ttu-id="b7e5e-119">[MQSeries アダプターのプロパティ](../core/mqseries-adapter-properties.md) </span><span class="sxs-lookup"><span data-stu-id="b7e5e-119">[MQSeries Adapter Properties](../core/mqseries-adapter-properties.md) </span></span>  
 <span data-ttu-id="b7e5e-120">[BizTalk Server に関連するプロパティ](../core/properties-related-to-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="b7e5e-120">[Properties Related to BizTalk Server](../core/properties-related-to-biztalk-server.md) </span></span>  
 [<span data-ttu-id="b7e5e-121">MQSeries コンテキスト プロパティ</span><span class="sxs-lookup"><span data-stu-id="b7e5e-121">MQSeries Context Properties</span></span>](../core/mqseries-context-properties.md)