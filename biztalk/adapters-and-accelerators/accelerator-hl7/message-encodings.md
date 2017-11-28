---
title: "メッセージのエンコーディング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, encodings
- messages, code samples
- encoding [messages]
- code samples
ms.assetid: 360638c0-4094-428f-a7c7-306a5f95a6bf
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36063416e1c5d1f30c9cb9c26056299f0b926a50
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-encodings"></a><span data-ttu-id="dcceb-102">メッセージ エンコーディング</span><span class="sxs-lookup"><span data-stu-id="dcceb-102">Message Encodings</span></span>
<span data-ttu-id="dcceb-103">役に立つに HL7 の順序でメッセージのセマンティクスを定義するのに十分ではありません。</span><span class="sxs-lookup"><span data-stu-id="dcceb-103">It is not sufficient to define message semantics in order for HL7 to be useful.</span></span> <span data-ttu-id="dcceb-104">メッセージの内容が特定されると、標準は、実際のインターフェイスでは、そのコンテンツを表現する方法を説明するがします。</span><span class="sxs-lookup"><span data-stu-id="dcceb-104">Once message content has been determined, the standard has to explain how to represent that content in an actual interface.</span></span> <span data-ttu-id="dcceb-105">つまり、ある必要があります指定された「メッセージ エンコード」です。</span><span class="sxs-lookup"><span data-stu-id="dcceb-105">That is to say, there must be a specified "message encoding".</span></span> <span data-ttu-id="dcceb-106">HL7 バージョン 2 には、メッセージ エンコーディング、カスタム区切り記号ベース エンコーディング、および XML エンコーディングの 2 つの形式がサポートしています。</span><span class="sxs-lookup"><span data-stu-id="dcceb-106">HL7 Version 2 supports two forms of message encoding, a custom delimiter-based encoding, and an XML encoding.</span></span>  
  
 <span data-ttu-id="dcceb-107">HL7 では、元の区切り記号ベースのエンコードをできるだけ多くのメッセージのサイズを減らすために選択されました。</span><span class="sxs-lookup"><span data-stu-id="dcceb-107">HL7 chose the original delimiter-based encoding to reduce the size of messages as much as possible.</span></span> <span data-ttu-id="dcceb-108">たとえば、区切り文字が位置の固定セット内の各要素を移動する構造体への要素を別々 のデータ構造体を比較する場合の区切り記号ベースの構造体は、はるかに高経済的) メッセージでは、いくつかの要素、および b) が含まれない場合要素では、許可されているすべての領域は入力しません。</span><span class="sxs-lookup"><span data-stu-id="dcceb-108">For example, if you compare a data structure in which delimiters separate elements to a structure that positions each element in a fixed set of positions, the delimiter-based structure is far more economical if a) messages do not contain some elements, and b) some elements do not fill all the space allowed.</span></span> <span data-ttu-id="dcceb-109">区切り記号ベースの構造でのみ、オーバーヘッドは、自身の区切り記号です。</span><span class="sxs-lookup"><span data-stu-id="dcceb-109">The only overhead in delimiter-based structures is the delimiters themselves.</span></span>  
  
 <span data-ttu-id="dcceb-110">元の HL7 のエンコードには、各メッセージが MSH セグメント内で宣言する 5 つの区切り記号を定義します。</span><span class="sxs-lookup"><span data-stu-id="dcceb-110">The original HL7 encoding defines five delimiters, which each message declares within the MSH segment.</span></span> <span data-ttu-id="dcceb-111">これは、情報を示します。</span><span class="sxs-lookup"><span data-stu-id="dcceb-111">These indicate:</span></span>  
  
-   <span data-ttu-id="dcceb-112">セグメント</span><span class="sxs-lookup"><span data-stu-id="dcceb-112">Segments</span></span>  
  
-   <span data-ttu-id="dcceb-113">フィールド</span><span class="sxs-lookup"><span data-stu-id="dcceb-113">Fields</span></span>  
  
-   <span data-ttu-id="dcceb-114">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="dcceb-114">Components</span></span>  
  
-   <span data-ttu-id="dcceb-115">これらのサブコンポーネント</span><span class="sxs-lookup"><span data-stu-id="dcceb-115">Subcomponents</span></span>  
  
-   <span data-ttu-id="dcceb-116">繰り返し (フィールド、コンポーネントまたはサブコンポーネント)</span><span class="sxs-lookup"><span data-stu-id="dcceb-116">Repetition (of a field, component, or subcomponent)</span></span>  
  
 <span data-ttu-id="dcceb-117">区切り記号は、エンコーディングの基本的な側面にあるために必要がありますを定義することに最初に注意してください。</span><span class="sxs-lookup"><span data-stu-id="dcceb-117">Note that since delimiters are a fundamental aspect of the encoding, you must define them first.</span></span> <span data-ttu-id="dcceb-118">この結果は、ことはありませんサブ サブの区切り記号です。</span><span class="sxs-lookup"><span data-stu-id="dcceb-118">One result of this is that there can be no sub-sub-delimiter.</span></span> <span data-ttu-id="dcceb-119">ときに、この制限には、新しいデータ型のデザイン時に残念ながら効果があります。</span><span class="sxs-lookup"><span data-stu-id="dcceb-119">At times, this limitation has unfortunate effects upon the design of new data types.</span></span>  
  
 <span data-ttu-id="dcceb-120">年 6 月の 2003 では、HL7 は、HL7 バージョン 2、XML エンコードの構文、Release 1 を公開します。</span><span class="sxs-lookup"><span data-stu-id="dcceb-120">In June 2003, HL7 published HL7 Version 2, XML Encoding Syntax, Release 1.</span></span> <span data-ttu-id="dcceb-121">この標準 HL7 バージョン 2.3.1 と 2.4 メッセージの場合の代替のエンコード規則を定義し、後続の HL7 の代替のエンコード規則を決定するためのメカニズムを提供 2.X バージョン。</span><span class="sxs-lookup"><span data-stu-id="dcceb-121">This standard defines alternate encoding rules for HL7 Version 2.3.1 and 2.4 messages, and provides a mechanism for determining alternate encoding rules for subsequent HL7 2.X versions.</span></span> <span data-ttu-id="dcceb-122">基本的には、この新しい標準は、Version 2.3.1 と V2.4 抽象メッセージ、セグメント、フィールド、およびデータ型の XML 要素タグを定義し、標準バージョン 2 の後続バージョンで作成された新しい構造体に必要なタグを定義するための規則を作成します。</span><span class="sxs-lookup"><span data-stu-id="dcceb-122">In essence, this new standard defines XML element tags for the Version 2.3.1 and V2.4 abstract messages, segments, fields, and data types, and creates rules for defining the tags needed for any new structures created for subsequent versions of the Version 2 standard.</span></span> <span data-ttu-id="dcceb-123">この標準を定義するプロセスは、バージョン 2.4 および 2.5 での機能強化の系列につながっています。</span><span class="sxs-lookup"><span data-stu-id="dcceb-123">The process of defining this standard led to a series of improvements in versions 2.4 and 2.5.</span></span> <span data-ttu-id="dcceb-124">これには、XML タグの作成の原因で、基になる標準従来からのあいまいさを解決する必要があるためにが発生しました。</span><span class="sxs-lookup"><span data-stu-id="dcceb-124">This happened because creation of XML tags led to the need to address some longstanding ambiguities in the underlying standard.</span></span> <span data-ttu-id="dcceb-125">) 適切に定義されたメッセージの構造体のコードを抽象にイベントを発生させる、b) 繰り返し抽象メッセージを含むセグメントのグループが正式に特定され、という名前に関連付けられているメッセージ内のバリエーションを示すために作成された as a result、c)、およびローカル定義済みのデータ型、CM は、特定の種類に置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="dcceb-125">As a result, a) well-defined message structure codes were created to indicate variations in the abstract messages associated with trigger events, b) repeating groups of segments with an abstract message were formally identified and named, and c) the locally defined data type, CM was replaced with more specific types.</span></span>  
  
 <span data-ttu-id="dcceb-126">たとえば、従来のパイプ区切り形式を使用して、単純な受信確認メッセージは、次のように。</span><span class="sxs-lookup"><span data-stu-id="dcceb-126">For example, the following is a simple acknowledgment message using the traditional pipe delimited format:</span></span>  
  
```  
MSH|^~\&|LAB|767543|ADT|767543|199003141304-0500||ACK^^ACK|XX3657|P|2.4  
MSA|AR|ZZ9380  
ERR|PID^1^16^103&Table value not found&HL70357  
```  
  
 <span data-ttu-id="dcceb-127">これに対し、次は、同じメッセージを XML ドキュメントとして表されます。</span><span class="sxs-lookup"><span data-stu-id="dcceb-127">By contrast, the following is the same message represented as an XML document:</span></span>  
  
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
  
 <span data-ttu-id="dcceb-128">次の関数の[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) これらの要件をサポートします。</span><span class="sxs-lookup"><span data-stu-id="dcceb-128">The following functions of [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) support these requirements:</span></span>  
  
-   <span data-ttu-id="dcceb-129">パイプ区切りおよび XML エンコーディングのサポート。</span><span class="sxs-lookup"><span data-stu-id="dcceb-129">Support of pipe delimited and XML encoding.</span></span>  
  
-   <span data-ttu-id="dcceb-130">XML ストレージとパイプの翻訳のサポートには、エンコーディングが区切られます。</span><span class="sxs-lookup"><span data-stu-id="dcceb-130">Support of translation between XML and pipe delimited encodings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcceb-131">参照</span><span class="sxs-lookup"><span data-stu-id="dcceb-131">See Also</span></span>  
 <span data-ttu-id="dcceb-132">[HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="dcceb-132">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="dcceb-133">[メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="dcceb-133">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="dcceb-134">HL7 2.X スキーマの使用</span><span class="sxs-lookup"><span data-stu-id="dcceb-134">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)