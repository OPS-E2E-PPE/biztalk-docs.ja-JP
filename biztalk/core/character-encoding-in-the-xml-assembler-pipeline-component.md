---
title: XML アセンブラー パイプライン コンポーネントにおける文字エンコーディング |Microsoft Docs
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
ms.openlocfilehash: 1e01bbf7224da9abda8700721c1de3dd7efefb8f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357477"
---
# <a name="character-encoding-in-the-xml-assembler-pipeline-component"></a><span data-ttu-id="c7824-102">XML アセンブラー パイプライン コンポーネントでの文字エン コード</span><span class="sxs-lookup"><span data-stu-id="c7824-102">Character Encoding in the XML Assembler Pipeline Component</span></span>
<span data-ttu-id="c7824-103">XML アセンブラー パイプライン コンポーネントは、次の表に示すように、ユーザー指定の文字の 2 つの方法でのエンコードでメッセージを生成できます。</span><span class="sxs-lookup"><span data-stu-id="c7824-103">The XML Assembler pipeline component can produce messages in user-specified character encoding in two ways, as shown in the following table.</span></span>  
  
|<span data-ttu-id="c7824-104">エンコード レベル</span><span class="sxs-lookup"><span data-stu-id="c7824-104">Encoding level</span></span>|<span data-ttu-id="c7824-105">エンコード方式</span><span class="sxs-lookup"><span data-stu-id="c7824-105">Encoding method</span></span>|  
|--------------------|---------------------|  
|<span data-ttu-id="c7824-106">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c7824-106">Component</span></span>|<span data-ttu-id="c7824-107">設定、**ターゲット文字セット**パイプライン デザイナーでコンポーネントのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="c7824-107">Set the **Target charset** component property in Pipeline Designer.</span></span>|  
|<span data-ttu-id="c7824-108">メッセージ</span><span class="sxs-lookup"><span data-stu-id="c7824-108">Message</span></span>|<span data-ttu-id="c7824-109">設定、 **XMLNorm.TargetCharset**メッセージ コンテキストのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="c7824-109">Set the **XMLNorm.TargetCharset** property on the message context.</span></span> <span data-ttu-id="c7824-110">**注:** メッセージ コンテキスト プロパティは、常にパイプライン デザイナーで設定されたコンテキスト プロパティをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="c7824-110">**Note:**  A message context property always overrides any context property set in Pipeline Designer.</span></span>|  
  
 <span data-ttu-id="c7824-111">XML アセンブラーでは、次のアルゴリズムを使って、出力メッセージのエンコードを決定します。</span><span class="sxs-lookup"><span data-stu-id="c7824-111">The XML Assembler uses the following algorithm to determine output message encoding:</span></span>  
  
1. <span data-ttu-id="c7824-112">場合、 **XMLNorm.TargetCharset**コンテキスト プロパティが設定されて、その値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c7824-112">If the **XMLNorm.TargetCharset** context property is set, its value is used.</span></span>  
  
2. <span data-ttu-id="c7824-113">の場合、**ターゲット文字セット**その値が使用されるパイプライン デザイナーでプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="c7824-113">Otherwise, if the **Target charset** property is specified in Pipeline Designer, its value is used.</span></span>  
  
3. <span data-ttu-id="c7824-114">の場合、 **XMLNorm.SourceCharset**プロパティを指定すると、その値を使用します。</span><span class="sxs-lookup"><span data-stu-id="c7824-114">Otherwise, if the **XMLNorm.SourceCharset** property is specified, its value is used.</span></span>  
  
4. <span data-ttu-id="c7824-115">前のプロパティを設定すると、utf-8 エンコードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="c7824-115">If none of the preceding properties is set, UTF-8 encoding is used.</span></span>  
  
   <span data-ttu-id="c7824-116">XML アセンブラーでは、BizTalk メッセージ オブジェクトのエンコード情報を保存する、`IBaseMessagePart.Charset`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="c7824-116">The XML Assembler saves the encoding information of a BizTalk message object in the `IBaseMessagePart.Charset` property.</span></span> <span data-ttu-id="c7824-117">Unicode または utf-8 エンコードを使用する場合、XML アセンブラーは常に、バイト順マーク (BOM) を送信メッセージに追加します。</span><span class="sxs-lookup"><span data-stu-id="c7824-117">When using Unicode or UTF-8 encoding, the XML Assembler always adds the byte order mark (BOM) to outgoing messages.</span></span>  
  
   <span data-ttu-id="c7824-118">される XML 送信パイプラインで、XML アセンブラー コンポーネントが含まれている既定値を使用する場合、生成されるドキュメント可能性がありますエンコードされるとき、サーバーへの送信またはドキュメントが作成された場合は、utf-8 を使用してエンコードされますとして同じ文字セットを使用して、サーバー内で、 **XMLNorm.TargetCharset**が指定されていません。</span><span class="sxs-lookup"><span data-stu-id="c7824-118">Note that when using the default XML send pipeline, which contains the XML Assembler component, the produced documents may be encoded by using the same charset as when they were submitted into the server, or they may be encoded by using UTF-8 if documents were created within the server and **XMLNorm.TargetCharset** was not specified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7824-119">参照</span><span class="sxs-lookup"><span data-stu-id="c7824-119">See Also</span></span>  
 <span data-ttu-id="c7824-120">[XML アセンブラー パイプライン コンポーネント](../core/xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="c7824-120">[XML Assembler Pipeline Component](../core/xml-assembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="c7824-121">[XML アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="c7824-121">[How to Configure the XML Assembler Pipeline Component](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="c7824-122">Pipelines-AssemblerDisassembler (BizTalk Server サンプル フォルダー)</span><span class="sxs-lookup"><span data-stu-id="c7824-122">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)