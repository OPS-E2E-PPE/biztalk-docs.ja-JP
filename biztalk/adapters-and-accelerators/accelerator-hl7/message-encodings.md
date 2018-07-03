---
title: メッセージのエンコーディング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, encodings
- messages, code samples
- encoding [messages]
- code samples
ms.assetid: 360638c0-4094-428f-a7c7-306a5f95a6bf
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 013df4d29604e6dd7ce6d2e486612be303cc5898
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007091"
---
# <a name="message-encodings"></a><span data-ttu-id="bf395-102">メッセージ エンコーディング</span><span class="sxs-lookup"><span data-stu-id="bf395-102">Message Encodings</span></span>
<span data-ttu-id="bf395-103">HL7 を使用するためにメッセージのセマンティクスを定義するのに十分ではありません。</span><span class="sxs-lookup"><span data-stu-id="bf395-103">It is not sufficient to define message semantics in order for HL7 to be useful.</span></span> <span data-ttu-id="bf395-104">メッセージの内容を確認すると、実際のインターフェイスでは、そのコンテンツを表す方法を説明する、標準を持ちます。</span><span class="sxs-lookup"><span data-stu-id="bf395-104">Once message content has been determined, the standard has to explain how to represent that content in an actual interface.</span></span> <span data-ttu-id="bf395-105">つまり、必要がある、指定した「メッセージをエンコードする」。</span><span class="sxs-lookup"><span data-stu-id="bf395-105">That is to say, there must be a specified "message encoding".</span></span> <span data-ttu-id="bf395-106">HL7 バージョン 2 では、2 つの形式のメッセージのエンコードと、カスタムの区切り記号ベースのエンコード、XML エンコーディングをサポートします。</span><span class="sxs-lookup"><span data-stu-id="bf395-106">HL7 Version 2 supports two forms of message encoding, a custom delimiter-based encoding, and an XML encoding.</span></span>  
  
 <span data-ttu-id="bf395-107">HL7 元区切り記号ベースのエンコード可能な限りメッセージのサイズを小さくことにしました。</span><span class="sxs-lookup"><span data-stu-id="bf395-107">HL7 chose the original delimiter-based encoding to reduce the size of messages as much as possible.</span></span> <span data-ttu-id="bf395-108">たとえばを区切り記号は位置の固定セット内の各要素を移動する構造体への要素を区切るデータ構造体を比較すると、区切り記号ベースの構造体より経済的) メッセージでは、いくつかの要素と b) 一部が含まれない場合要素は、許可されているすべての領域には入力しません。</span><span class="sxs-lookup"><span data-stu-id="bf395-108">For example, if you compare a data structure in which delimiters separate elements to a structure that positions each element in a fixed set of positions, the delimiter-based structure is far more economical if a) messages do not contain some elements, and b) some elements do not fill all the space allowed.</span></span> <span data-ttu-id="bf395-109">構造体の区切り記号ベースの唯一のオーバーヘッドは、自身の区切り記号です。</span><span class="sxs-lookup"><span data-stu-id="bf395-109">The only overhead in delimiter-based structures is the delimiters themselves.</span></span>  
  
 <span data-ttu-id="bf395-110">元の HL7 のエンコードには、各メッセージは MSH セグメント内で宣言する 5 つの区切り記号を定義します。</span><span class="sxs-lookup"><span data-stu-id="bf395-110">The original HL7 encoding defines five delimiters, which each message declares within the MSH segment.</span></span> <span data-ttu-id="bf395-111">これらを指定します。</span><span class="sxs-lookup"><span data-stu-id="bf395-111">These indicate:</span></span>  
  
- <span data-ttu-id="bf395-112">セグメント</span><span class="sxs-lookup"><span data-stu-id="bf395-112">Segments</span></span>  
  
- <span data-ttu-id="bf395-113">フィールド</span><span class="sxs-lookup"><span data-stu-id="bf395-113">Fields</span></span>  
  
- <span data-ttu-id="bf395-114">Components</span><span class="sxs-lookup"><span data-stu-id="bf395-114">Components</span></span>  
  
- <span data-ttu-id="bf395-115">サブコンポーネント</span><span class="sxs-lookup"><span data-stu-id="bf395-115">Subcomponents</span></span>  
  
- <span data-ttu-id="bf395-116">(フィールド、コンポーネントまたはサブコンポーネント) の繰り返し</span><span class="sxs-lookup"><span data-stu-id="bf395-116">Repetition (of a field, component, or subcomponent)</span></span>  
  
  <span data-ttu-id="bf395-117">区切り記号、エンコーディングの基本的な側面はする必要がありますを定義することに最初に注意してください。</span><span class="sxs-lookup"><span data-stu-id="bf395-117">Note that since delimiters are a fundamental aspect of the encoding, you must define them first.</span></span> <span data-ttu-id="bf395-118">この結果は、あることにないサブ サブの区切り記号です。</span><span class="sxs-lookup"><span data-stu-id="bf395-118">One result of this is that there can be no sub-sub-delimiter.</span></span> <span data-ttu-id="bf395-119">この制限には、新しいデータ型のデザイン時に残念な効果があります。</span><span class="sxs-lookup"><span data-stu-id="bf395-119">At times, this limitation has unfortunate effects upon the design of new data types.</span></span>  
  
  <span data-ttu-id="bf395-120">2003 年 6 月、HL7 は HL7 バージョン 2、XML エンコードの構文、リリース 1 を公開します。</span><span class="sxs-lookup"><span data-stu-id="bf395-120">In June 2003, HL7 published HL7 Version 2, XML Encoding Syntax, Release 1.</span></span> <span data-ttu-id="bf395-121">この標準が HL7 バージョン 2.3.1 および 2.4 メッセージの場合、代替のエンコーディング規則を定義し、後続の HL7 の代替のエンコーディング規則を決定するためのメカニズムを提供します 2.X バージョン。</span><span class="sxs-lookup"><span data-stu-id="bf395-121">This standard defines alternate encoding rules for HL7 Version 2.3.1 and 2.4 messages, and provides a mechanism for determining alternate encoding rules for subsequent HL7 2.X versions.</span></span> <span data-ttu-id="bf395-122">基本的には、この新しい標準は、Version 2.3.1 および V2.4 抽象メッセージ、セグメント、フィールド、およびデータ型の XML 要素タグを定義し、標準バージョン 2 の今後のバージョンの作成、新しい構造に必要なタグを定義するための規則を作成します。</span><span class="sxs-lookup"><span data-stu-id="bf395-122">In essence, this new standard defines XML element tags for the Version 2.3.1 and V2.4 abstract messages, segments, fields, and data types, and creates rules for defining the tags needed for any new structures created for subsequent versions of the Version 2 standard.</span></span> <span data-ttu-id="bf395-123">この標準を定義するプロセスは、一連のバージョン 2.4、2.5 での機能強化につながっています。</span><span class="sxs-lookup"><span data-stu-id="bf395-123">The process of defining this standard led to a series of improvements in versions 2.4 and 2.5.</span></span> <span data-ttu-id="bf395-124">XML タグの作成により、基になる標準の長期あいまいさに対処する必要があるのため、これが発生しました。</span><span class="sxs-lookup"><span data-stu-id="bf395-124">This happened because creation of XML tags led to the need to address some longstanding ambiguities in the underlying standard.</span></span> <span data-ttu-id="bf395-125">B) 抽象メッセージ セグメントのグループが正式に特定され、という名前の繰り返しのトリガー イベントに関連付けられている抽象メッセージ内のバリエーションを示すコードの構造) 適切に定義されたメッセージが作成されたその、c)、およびローカル定義済みのデータ型、CM は、特定の種類に置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="bf395-125">As a result, a) well-defined message structure codes were created to indicate variations in the abstract messages associated with trigger events, b) repeating groups of segments with an abstract message were formally identified and named, and c) the locally defined data type, CM was replaced with more specific types.</span></span>  
  
  <span data-ttu-id="bf395-126">たとえば、従来のパイプ区切り形式を使用して単純な受信確認メッセージは、次のように。</span><span class="sxs-lookup"><span data-stu-id="bf395-126">For example, the following is a simple acknowledgment message using the traditional pipe delimited format:</span></span>  
  
```  
MSH|^~\&|LAB|767543|ADT|767543|199003141304-0500||ACK^^ACK|XX3657|P|2.4  
MSA|AR|ZZ9380  
ERR|PID^1^16^103&Table value not found&HL70357  
```  
  
 <span data-ttu-id="bf395-127">これに対し、次は、同じメッセージを XML ドキュメントとして表されます。</span><span class="sxs-lookup"><span data-stu-id="bf395-127">By contrast, the following is the same message represented as an XML document:</span></span>  
  
```  
<ACK  
xmlns="urn:hl7-org:v2xml"  
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
xsi:schemaLocation="urn:hl7-org:v2xml ACK.xsd">  
   <MSH>  
      <MSH.1>|</MSH.1>  
      <MSH.2>^~\&</MSH.2>  
      <MSH.3>  
         <HD.1>LAB</HD.1>  
      </MSH.3>  
      <MSH.4>  
         <HD.1>767543</HD.1>  
      </MSH.4>  
      <MSH.5>  
         <HD.1>ADT</HD.1>  
      </MSH.5>  
      <MSH.6>  
         <HD.1>767543</HD.1>  
      </MSH.6>  
      <MSH.7>  
         <TS.1>199003141304-0500</TS.1>  
      </MSH.7>  
      <MSH.9>  
         <MSG.1>ACK</MSG.1>  
         <MSG.3>ACK</MSG.3>  
      </MSH.9>  
      <MSH.10>XX3657</MSH.10>  
      <MSH.11>  
         <PT.1>P</PT.1>  
      </MSH.11>  
      <MSH.12>  
         <VID.1>2.4</VID.1>  
      </MSH.12>  
   </MSH>  
   <MSA>  
      <MSA.1>AR</MSA.1>  
      <MSA.2>ZZ9380</MSA.2>  
   </MSA>  
   <ERR>  
      <ERR.1>  
         <ELD.1>PID</ELD.1>  
         <ELD.2>1</ELD.2>  
         <ELD.3>16</ELD.3>  
         <ELD.4>  
            <CE.1>103</CE.1>  
            <CE.2>Table value not found</CE.2>  
            <CE.3>HL70357</CE.3>  
         </ELD.4>  
      </ERR.1>  
   </ERR>  
</ACK>  
```  
  
 <span data-ttu-id="bf395-128">Microsoft BizTalk Accelerator for HL7 の次の関数 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) これらの要件をサポートします。</span><span class="sxs-lookup"><span data-stu-id="bf395-128">The following functions of Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) support these requirements:</span></span>  
  
-   <span data-ttu-id="bf395-129">パイプ区切り、および XML エンコーディングをサポートします。</span><span class="sxs-lookup"><span data-stu-id="bf395-129">Support of pipe delimited and XML encoding.</span></span>  
  
-   <span data-ttu-id="bf395-130">XML とパイプ間の変換のサポートには、エンコーディングが区切られます。</span><span class="sxs-lookup"><span data-stu-id="bf395-130">Support of translation between XML and pipe delimited encodings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf395-131">参照</span><span class="sxs-lookup"><span data-stu-id="bf395-131">See Also</span></span>  
 <span data-ttu-id="bf395-132">[HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="bf395-132">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="bf395-133">[メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="bf395-133">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="bf395-134">HL7 2.X スキーマの使用</span><span class="sxs-lookup"><span data-stu-id="bf395-134">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)