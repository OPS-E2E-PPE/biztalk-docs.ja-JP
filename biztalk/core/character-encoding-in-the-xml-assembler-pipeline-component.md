---
title: XML アセンブラー パイプライン コンポーネントでの文字エン コード |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IBaseMessagePart.Charset property
- XMLNorm.SourceCharset property
- pipeline components, XML Assembler
- XMLNorm.TargetCharset property
- Target Charset property
- XML Assembler [pipeline component], character encoding
ms.assetid: c031fbbf-f00f-41ba-8ac9-cec7d625cef6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82709af574e3577990cf99cd430e1a5e6a7f8485
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232106"
---
# <a name="character-encoding-in-the-xml-assembler-pipeline-component"></a><span data-ttu-id="2848a-102">XML アセンブラー パイプライン コンポーネントでの文字エン コード</span><span class="sxs-lookup"><span data-stu-id="2848a-102">Character Encoding in the XML Assembler Pipeline Component</span></span>
<span data-ttu-id="2848a-103">XML アセンブラー パイプライン コンポーネントでは、ユーザー指定の文字エンコード方法に基づいてメッセージを生成します。指定できるエンコード方法は、次の表に示す 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="2848a-103">The XML Assembler pipeline component can produce messages in user-specified character encoding in two ways, as shown in the following table.</span></span>  
  
|<span data-ttu-id="2848a-104">エンコード レベル</span><span class="sxs-lookup"><span data-stu-id="2848a-104">Encoding level</span></span>|<span data-ttu-id="2848a-105">エンコード方法</span><span class="sxs-lookup"><span data-stu-id="2848a-105">Encoding method</span></span>|  
|--------------------|---------------------|  
|<span data-ttu-id="2848a-106">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2848a-106">Component</span></span>|<span data-ttu-id="2848a-107">設定、**表せない**パイプライン デザイナーでコンポーネントのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="2848a-107">Set the **Target charset** component property in Pipeline Designer.</span></span>|  
|<span data-ttu-id="2848a-108">メッセージ</span><span class="sxs-lookup"><span data-stu-id="2848a-108">Message</span></span>|<span data-ttu-id="2848a-109">設定、 **XMLNorm.TargetCharset**メッセージ コンテキストのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="2848a-109">Set the **XMLNorm.TargetCharset** property on the message context.</span></span> <span data-ttu-id="2848a-110">**注:** メッセージ コンテキスト プロパティは常にパイプライン デザイナーで設定されたコンテキスト プロパティをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="2848a-110">**Note:**  A message context property always overrides any context property set in Pipeline Designer.</span></span>|  
  
 <span data-ttu-id="2848a-111">XML アセンブラーでは、次のアルゴリズムに基づいて、出力メッセージのエンコードを決定します。</span><span class="sxs-lookup"><span data-stu-id="2848a-111">The XML Assembler uses the following algorithm to determine output message encoding:</span></span>  
  
1.  <span data-ttu-id="2848a-112">場合、 **XMLNorm.TargetCharset**コンテキスト プロパティが設定されて、その値を使用します。</span><span class="sxs-lookup"><span data-stu-id="2848a-112">If the **XMLNorm.TargetCharset** context property is set, its value is used.</span></span>  
  
2.  <span data-ttu-id="2848a-113">それ以外の場合、**表せない**プロパティが指定されてパイプライン デザイナーでその値を使用します。</span><span class="sxs-lookup"><span data-stu-id="2848a-113">Otherwise, if the **Target charset** property is specified in Pipeline Designer, its value is used.</span></span>  
  
3.  <span data-ttu-id="2848a-114">それ以外の場合、 **XMLNorm.SourceCharset**プロパティを指定すると、その値を使用します。</span><span class="sxs-lookup"><span data-stu-id="2848a-114">Otherwise, if the **XMLNorm.SourceCharset** property is specified, its value is used.</span></span>  
  
4.  <span data-ttu-id="2848a-115">上記のいずれのプロパティも設定されていなかった場合は、UTF-8 エンコードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="2848a-115">If none of the preceding properties is set, UTF-8 encoding is used.</span></span>  
  
 <span data-ttu-id="2848a-116">XML アセンブラーでは、BizTalk メッセージ オブジェクトのエンコード情報を保存する、`IBaseMessagePart.Charset`プロパティです。</span><span class="sxs-lookup"><span data-stu-id="2848a-116">The XML Assembler saves the encoding information of a BizTalk message object in the `IBaseMessagePart.Charset` property.</span></span> <span data-ttu-id="2848a-117">Unicode または UTF-8 エンコードを使用する場合、送信メッセージには常にバイト オーダー マーク (BOM) が追加されます。</span><span class="sxs-lookup"><span data-stu-id="2848a-117">When using Unicode or UTF-8 encoding, the XML Assembler always adds the byte order mark (BOM) to outgoing messages.</span></span>  
  
 <span data-ttu-id="2848a-118">XML 送信パイプラインで、XML アセンブラー コンポーネントが含まれている既定値を使用する場合、生成されるドキュメント エンコードできる、サーバーに送信されたか、ドキュメントが作成された場合は、utf-8 を使用してエンコードされるときと同じ文字セットを使用してに注意してください。サーバー内でおよび**XMLNorm.TargetCharset**が指定されていません。</span><span class="sxs-lookup"><span data-stu-id="2848a-118">Note that when using the default XML send pipeline, which contains the XML Assembler component, the produced documents may be encoded by using the same charset as when they were submitted into the server, or they may be encoded by using UTF-8 if documents were created within the server and **XMLNorm.TargetCharset** was not specified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2848a-119">参照</span><span class="sxs-lookup"><span data-stu-id="2848a-119">See Also</span></span>  
 <span data-ttu-id="2848a-120">[XML アセンブラー パイプライン コンポーネント](../core/xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="2848a-120">[XML Assembler Pipeline Component](../core/xml-assembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="2848a-121">[XML アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="2848a-121">[How to Configure the XML Assembler Pipeline Component](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="2848a-122">パイプライン AssemblerDisassembler (BizTalk Server Samples フォルダ)</span><span class="sxs-lookup"><span data-stu-id="2848a-122">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)