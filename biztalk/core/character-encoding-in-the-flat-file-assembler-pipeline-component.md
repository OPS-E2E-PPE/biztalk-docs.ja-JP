---
title: フラット ファイル アセンブラー パイプライン コンポーネントにおける文字エンコーディング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b97a92ed1dd842f6b65b49d1c312ffd84eb8dac
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357487"
---
# <a name="character-encoding-in-the-flat-file-assembler-pipeline-component"></a><span data-ttu-id="4f3c3-102">フラット ファイル アセンブラー パイプライン コンポーネントでの文字エン コード</span><span class="sxs-lookup"><span data-stu-id="4f3c3-102">Character Encoding in the Flat File Assembler Pipeline Component</span></span>
<span data-ttu-id="4f3c3-103">フラット ファイル アセンブラーでは、ユーザー指定の文字のエンコードでのメッセージを生成できます。</span><span class="sxs-lookup"><span data-stu-id="4f3c3-103">The Flat File Assembler can produce messages in user-specified character encoding.</span></span> <span data-ttu-id="4f3c3-104">さまざまなレベルで文字エン コードを指定できます。</span><span class="sxs-lookup"><span data-stu-id="4f3c3-104">You can specify the character encoding at several levels:</span></span>  
  
- <span data-ttu-id="4f3c3-105">**スキーマです。**</span><span class="sxs-lookup"><span data-stu-id="4f3c3-105">**Schema.**</span></span> <span data-ttu-id="4f3c3-106">設定、**コードページ**ドキュメントのフラット ファイル スキーマのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="4f3c3-106">Set the **codepage** property in the flat file schema for the document.</span></span>  
  
- <span data-ttu-id="4f3c3-107">**コンポーネント。**</span><span class="sxs-lookup"><span data-stu-id="4f3c3-107">**Component.**</span></span> <span data-ttu-id="4f3c3-108">設定、**ターゲット文字セット**パイプライン デザイナーでコンポーネントのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="4f3c3-108">Set the **Target Charset** component property in Pipeline Designer.</span></span>  
  
- <span data-ttu-id="4f3c3-109">**メッセージ。**</span><span class="sxs-lookup"><span data-stu-id="4f3c3-109">**Message.**</span></span> <span data-ttu-id="4f3c3-110">設定、 **XMLNorm.TargetCharset**メッセージ コンテキストのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="4f3c3-110">Set the **XMLNorm.TargetCharset** property on the message context.</span></span>  
  
  <span data-ttu-id="4f3c3-111">常にメッセージ コンテキストに設定するプロパティの値は、パイプライン デザイナーで 1 つのセットを上書きします。</span><span class="sxs-lookup"><span data-stu-id="4f3c3-111">The value of the property set on a message context always overrides the one set in Pipeline Designer.</span></span> <span data-ttu-id="4f3c3-112">また、常にパイプライン デザイナーで設定された値として設定された値を上書き、**コードページ**フラット ファイル ドキュメント スキーマ内のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="4f3c3-112">Also, the value set in Pipeline Designer always overwrites the value set as a **codepage** property in a flat file document schema.</span></span>  
  
  <span data-ttu-id="4f3c3-113">フラット ファイル アセンブラーでは、次のアルゴリズムを使って、出力メッセージに使用するエンコードを決定します。</span><span class="sxs-lookup"><span data-stu-id="4f3c3-113">The Flat File Assembler uses the following algorithm to determine which encoding to use for an output message:</span></span>  
  
- <span data-ttu-id="4f3c3-114">場合、 **XMLNorm.TargetCharset**コンテキスト プロパティが設定されて、その値がエンコードに使用します。</span><span class="sxs-lookup"><span data-stu-id="4f3c3-114">If the **XMLNorm.TargetCharset** context property is set, its value is used for encoding.</span></span>  
  
- <span data-ttu-id="4f3c3-115">の場合、**ターゲット文字セット**パイプライン デザイナーでプロパティを指定すると、その値を使用します。</span><span class="sxs-lookup"><span data-stu-id="4f3c3-115">Otherwise, if the **Target charset** property in Pipeline Designer is specified, its value is used.</span></span>  
  
- <span data-ttu-id="4f3c3-116">の場合、**コードページ**フラット ファイル スキーマのプロパティを指定すると、その値を使用します。</span><span class="sxs-lookup"><span data-stu-id="4f3c3-116">Otherwise, if the **codepage** property in the flat file schema is specified, its value is used.</span></span>  
  
- <span data-ttu-id="4f3c3-117">の場合、 **XMLNorm.SourceCharset**プロパティを指定すると、その値を使用します。</span><span class="sxs-lookup"><span data-stu-id="4f3c3-117">Otherwise, if the **XMLNorm.SourceCharset** property is specified, its value is used.</span></span>  
  
- <span data-ttu-id="4f3c3-118">それ以外の場合、"utf-8"が使用されます。</span><span class="sxs-lookup"><span data-stu-id="4f3c3-118">Otherwise, "UTF-8" is used.</span></span> <span data-ttu-id="4f3c3-119">Utf-8 エンコードを使用する場合、フラット ファイル アセンブラー パイプライン コンポーネントであることに注意してくださいは送信メッセージにバイト オーダー マークを配置できません。</span><span class="sxs-lookup"><span data-stu-id="4f3c3-119">Note that the Flat File Assembler pipeline component does not put byte order mark on outgoing messages when UTF-8 encoding is used.</span></span>  
  
  <span data-ttu-id="4f3c3-120">フラット ファイル アセンブラーでは、BizTalk メッセージ オブジェクトのボディ部のエンコード情報を保存、 **IBaseMessagePart.Charset**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="4f3c3-120">The Flat File Assembler saves encoding information on the body part of the BizTalk message object in the **IBaseMessagePart.Charset** property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f3c3-121">参照</span><span class="sxs-lookup"><span data-stu-id="4f3c3-121">See Also</span></span>  
 <span data-ttu-id="4f3c3-122">[フラット ファイル アセンブラー パイプライン コンポーネント](../core/flat-file-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="4f3c3-122">[Flat File Assembler Pipeline Component](../core/flat-file-assembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="4f3c3-123">[フラット ファイル アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="4f3c3-123">[How to Configure the Flat File Assembler Pipeline Component](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="4f3c3-124">Pipelines-AssemblerDisassembler (BizTalk Server サンプル フォルダー)</span><span class="sxs-lookup"><span data-stu-id="4f3c3-124">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)