---
title: コード ページ指定フラット ファイル スキーマの |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 825e75f1-893c-4c61-b566-f893d732a907
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b0ba2c19c3fc02ff0a72fcd8e93ec9f4b112996
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357174"
---
# <a name="code-page-specification-for-flat-file-schemas"></a><span data-ttu-id="5cae8-102">フラット ファイル スキーマのコード ページの仕様</span><span class="sxs-lookup"><span data-stu-id="5cae8-102">Code Page Specification for Flat File Schemas</span></span>

## <a name="overview"></a><span data-ttu-id="5cae8-103">概要</span><span class="sxs-lookup"><span data-stu-id="5cae8-103">Overview</span></span>
<span data-ttu-id="5cae8-104">値、**コード ページ**逆アセンブリおよびフラット ファイル ドキュメントのアセンブリの中で使用されるエンコード オブジェクトを作成するプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="5cae8-104">The value in the **Code Page** property is used to create an encoding object that is used during the disassembly and assembly of flat file documents.</span></span> <span data-ttu-id="5cae8-105">このエンコーディング オブジェクトにより、Microsoft によって内部的に使用される正規化された utf-8 エンコードに、受信フラット ファイル ドキュメントのネイティブ エンコードに変換するフラット ファイル パーサー[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="5cae8-105">This encoding object allows the flat file parser to convert the native encoding of an inbound flat file document into the normalized UTF-8 encoding that is used internally by Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="5cae8-106">エンコーディング オブジェクトでは、内部の utf-8 エンコードでは、フラット ファイル ドキュメントのネイティブ エンコードに変換するフラット ファイル シリアライザーもできます。</span><span class="sxs-lookup"><span data-stu-id="5cae8-106">The encoding object also allows the flat file serializer to convert the internal UTF-8 encoding back into the native encoding of the flat file document.</span></span>  
  
 <span data-ttu-id="5cae8-107">設定、**コード ページ**プロパティが、フラット ファイル ビジネス ドキュメントで使用される文字エンコード体系を決定する際、排他的ではないが、重要な役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="5cae8-107">The setting of the **Code Page** property plays an important, but not exclusive, role in determining the character encoding scheme used by your flat file business documents.</span></span> <span data-ttu-id="5cae8-108">メッセージは、送信メッセージがフラット ファイル形式に変換された、フラット ファイル アセンブラーの文字はエンコードする方法とフラット ファイル逆アセンブラーによって解釈されます。 フラット ファイルを受信する方法を検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5cae8-108">You must consider how inbound flat file messages are interpreted by the flat file disassembler as well as how the flat file assembler will encode characters as outbound messages are translated into flat file format.</span></span>  

## <a name="character-encoding"></a><span data-ttu-id="5cae8-109">文字エン コード</span><span class="sxs-lookup"><span data-stu-id="5cae8-109">Character encoding</span></span>  
 <span data-ttu-id="5cae8-110">指定されたインスタンス メッセージの文字エン コードの処理方法を次のように決定する役割を果たす複数の要因があります。</span><span class="sxs-lookup"><span data-stu-id="5cae8-110">There are multiple factors that play a role in determining how character encoding for a given instance message is handled, as follows:</span></span>  
  
-   <span data-ttu-id="5cae8-111">フラット ファイル インスタンス メッセージを逆アセンブルするとき、次のアルゴリズムを使用して確認し、エンコード情報を保持を。</span><span class="sxs-lookup"><span data-stu-id="5cae8-111">When disassembling a flat file instance message, the following algorithm is used to determine and preserve encoding information:</span></span>  
  
    1.  <span data-ttu-id="5cae8-112">場合、 **Charset**メッセージのボディ部では、設定された場合、その値を使用します。</span><span class="sxs-lookup"><span data-stu-id="5cae8-112">If the **Charset** in the Message body part is set, its value is used.</span></span>  
  
    2.  <span data-ttu-id="5cae8-113">それ以外の場合、エンベロープ (またはドキュメント) スキーマを使用してコード ページを指定する場合、**コード ページ**プロパティ、その値を使用します。</span><span class="sxs-lookup"><span data-stu-id="5cae8-113">Otherwise, if the envelope (or document) schema specifies a code page using the **Code Page** property, its value is used.</span></span>  
  
    3.  <span data-ttu-id="5cae8-114">それ以外の場合、バイト順マークが存在する場合は、その値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="5cae8-114">Otherwise, if a byte order mark is present, its value is used.</span></span>  
  
    4.  <span data-ttu-id="5cae8-115">それ以外の場合、utf-8 を想定しています。</span><span class="sxs-lookup"><span data-stu-id="5cae8-115">Otherwise, assume UTF-8.</span></span>  
  
-   <span data-ttu-id="5cae8-116">フラット ファイル インスタンス メッセージをアセンブルするときに、次のアルゴリズムを使用してデコードで使用する文字セットの決定を。</span><span class="sxs-lookup"><span data-stu-id="5cae8-116">When assembling a flat file instance message, the following algorithm is used to determine the character set to use for decoding:</span></span>  
  
-   <span data-ttu-id="5cae8-117">場合、 **XMLNorm.TargetCharset**メッセージ コンテキスト プロパティの設定、その値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="5cae8-117">If the **XMLNorm.TargetCharset** message context property is set, its value is used.</span></span>  
  
-   <span data-ttu-id="5cae8-118">の場合、 **TargetCharset**アセンブラー (デザイン時) プロパティが設定されて、その値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="5cae8-118">Otherwise, if the **TargetCharset** assembler (design-time) property is set, its value is used.</span></span>  
  
-   <span data-ttu-id="5cae8-119">それ以外の場合、エンベロープ (またはドキュメント) スキーマを使用してコード ページを指定する場合、**コード ページ**プロパティ、その値を使用します。</span><span class="sxs-lookup"><span data-stu-id="5cae8-119">Otherwise, if the envelope (or document) schema specifies a code page using the **Code Page** property, its value is used.</span></span>  
  
    1.  <span data-ttu-id="5cae8-120">の場合、 **SourceCharset**メッセージ コンテキスト プロパティの設定、その値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="5cae8-120">Otherwise, if the **SourceCharset** message context property is set, its value is used.</span></span>  
  
    2.  <span data-ttu-id="5cae8-121">それ以外の場合、utf-8 を使用します。</span><span class="sxs-lookup"><span data-stu-id="5cae8-121">Otherwise, use UTF-8.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cae8-122">参照</span><span class="sxs-lookup"><span data-stu-id="5cae8-122">See Also</span></span>  
 <span data-ttu-id="5cae8-123">**ファイル メッセージ スキーマをフラットを作成する際の考慮事項**と**コード ページ (フラット ファイル スキーマのノード プロパティ)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="5cae8-123">**Considerations When Creating Flat File Message Schemas** and **Code Page (Node Property of Flat File Schemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>