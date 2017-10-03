---
title: "フラット ファイル アセンブラー パイプライン コンポーネントでの文字エン コード |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Flat File Assembler [pipeline component], character encoding
- IBaseMessagePart.Charset property
- pipeline components, Flat File Assembler
- Codepage property
- XMLNorm.SourceCharset property
- XMLNorm.TargetCharset property
- Target Charset property
ms.assetid: 0cf3c0fd-f036-4190-83ce-9064ef4e823c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af38855c81129cd4bafff50544f2aee15e6f3fab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="character-encoding-in-the-flat-file-assembler-pipeline-component"></a><span data-ttu-id="8f541-102">フラット ファイル アセンブラー パイプライン コンポーネントでの文字エン コード</span><span class="sxs-lookup"><span data-stu-id="8f541-102">Character Encoding in the Flat File Assembler Pipeline Component</span></span>
<span data-ttu-id="8f541-103">フラット ファイル アセンブラーを使用すると、ユーザーが指定する文字エンコードでメッセージを生成できます。</span><span class="sxs-lookup"><span data-stu-id="8f541-103">The Flat File Assembler can produce messages in user-specified character encoding.</span></span> <span data-ttu-id="8f541-104">文字エンコードは複数のレベルで指定できます。</span><span class="sxs-lookup"><span data-stu-id="8f541-104">You can specify the character encoding at several levels:</span></span>  
  
-   <span data-ttu-id="8f541-105">**スキーマです。**</span><span class="sxs-lookup"><span data-stu-id="8f541-105">**Schema.**</span></span> <span data-ttu-id="8f541-106">設定、**コードページ**ドキュメントのフラット ファイル スキーマのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="8f541-106">Set the **codepage** property in the flat file schema for the document.</span></span>  
  
-   <span data-ttu-id="8f541-107">**コンポーネント。**</span><span class="sxs-lookup"><span data-stu-id="8f541-107">**Component.**</span></span> <span data-ttu-id="8f541-108">設定、**表せない**パイプライン デザイナーでコンポーネントのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="8f541-108">Set the **Target Charset** component property in Pipeline Designer.</span></span>  
  
-   <span data-ttu-id="8f541-109">**メッセージ。**</span><span class="sxs-lookup"><span data-stu-id="8f541-109">**Message.**</span></span> <span data-ttu-id="8f541-110">設定、 **XMLNorm.TargetCharset**メッセージ コンテキストのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="8f541-110">Set the **XMLNorm.TargetCharset** property on the message context.</span></span>  
  
 <span data-ttu-id="8f541-111">メッセージ コンテキストに設定されたプロパティ値は、パイプライン デザイナーで設定されたプロパティ値よりも常に優先されます。</span><span class="sxs-lookup"><span data-stu-id="8f541-111">The value of the property set on a message context always overrides the one set in Pipeline Designer.</span></span> <span data-ttu-id="8f541-112">また、常にパイプライン デザイナーで設定された値として設定された値を上書き、**コードページ**フラット ファイル ドキュメント スキーマ内のプロパティです。</span><span class="sxs-lookup"><span data-stu-id="8f541-112">Also, the value set in Pipeline Designer always overwrites the value set as a **codepage** property in a flat file document schema.</span></span>  
  
 <span data-ttu-id="8f541-113">フラット ファイル アセンブラーでは、次のアルゴリズムに基づいて、出力メッセージのエンコードに使用する文字セットを決定します。</span><span class="sxs-lookup"><span data-stu-id="8f541-113">The Flat File Assembler uses the following algorithm to determine which encoding to use for an output message:</span></span>  
  
-   <span data-ttu-id="8f541-114">場合、 **XMLNorm.TargetCharset**コンテキスト プロパティが設定されて、その値はエンコードするために使用します。</span><span class="sxs-lookup"><span data-stu-id="8f541-114">If the **XMLNorm.TargetCharset** context property is set, its value is used for encoding.</span></span>  
  
-   <span data-ttu-id="8f541-115">それ以外の場合、**表せない**パイプライン デザイナーでプロパティを指定すると、その値を使用します。</span><span class="sxs-lookup"><span data-stu-id="8f541-115">Otherwise, if the **Target charset** property in Pipeline Designer is specified, its value is used.</span></span>  
  
-   <span data-ttu-id="8f541-116">それ以外の場合、**コードページ**フラット ファイル スキーマのプロパティを指定すると、その値を使用します。</span><span class="sxs-lookup"><span data-stu-id="8f541-116">Otherwise, if the **codepage** property in the flat file schema is specified, its value is used.</span></span>  
  
-   <span data-ttu-id="8f541-117">それ以外の場合、 **XMLNorm.SourceCharset**プロパティを指定すると、その値を使用します。</span><span class="sxs-lookup"><span data-stu-id="8f541-117">Otherwise, if the **XMLNorm.SourceCharset** property is specified, its value is used.</span></span>  
  
-   <span data-ttu-id="8f541-118">上記のいずれにも該当しない場合は、"UTF-8" が使用されます。</span><span class="sxs-lookup"><span data-stu-id="8f541-118">Otherwise, "UTF-8" is used.</span></span> <span data-ttu-id="8f541-119">UTF-8 エンコードを使用する場合、フラット ファイル アセンブラー パイプライン コンポーネントでは、送信メッセージにバイト順マークが付加されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8f541-119">Note that the Flat File Assembler pipeline component does not put byte order mark on outgoing messages when UTF-8 encoding is used.</span></span>  
  
 <span data-ttu-id="8f541-120">フラット ファイル アセンブラーでは、BizTalk メッセージ オブジェクトのボディ部のエンコード情報を保存、 **IBaseMessagePart.Charset**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="8f541-120">The Flat File Assembler saves encoding information on the body part of the BizTalk message object in the **IBaseMessagePart.Charset** property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f541-121">参照</span><span class="sxs-lookup"><span data-stu-id="8f541-121">See Also</span></span>  
 <span data-ttu-id="8f541-122">[フラット ファイル アセンブラー パイプライン コンポーネント](../core/flat-file-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="8f541-122">[Flat File Assembler Pipeline Component](../core/flat-file-assembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="8f541-123">[フラット ファイル アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="8f541-123">[How to Configure the Flat File Assembler Pipeline Component](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="8f541-124">パイプライン AssemblerDisassembler (BizTalk Server Samples フォルダ)</span><span class="sxs-lookup"><span data-stu-id="8f541-124">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)