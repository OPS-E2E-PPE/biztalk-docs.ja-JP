---
title: コード ページ指定フラット ファイル スキーマの |Microsoft ドキュメント
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
ms.openlocfilehash: 64d5cfbc960346e702ed0d4a39ca74bbc4b3634c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232266"
---
# <a name="code-page-specification-for-flat-file-schemas"></a><span data-ttu-id="05311-102">フラット ファイル スキーマのコード ページ仕様</span><span class="sxs-lookup"><span data-stu-id="05311-102">Code Page Specification for Flat File Schemas</span></span>

## <a name="overview"></a><span data-ttu-id="05311-103">概要</span><span class="sxs-lookup"><span data-stu-id="05311-103">Overview</span></span>
<span data-ttu-id="05311-104">値、**コード ページ**逆アセンブリおよびフラット ファイル ドキュメントのアセンブリの中で使用されるエンコード オブジェクトを作成するプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="05311-104">The value in the **Code Page** property is used to create an encoding object that is used during the disassembly and assembly of flat file documents.</span></span> <span data-ttu-id="05311-105">このエンコード オブジェクトを使用すると、フラット ファイル パーサーでは、受信フラット ファイル ドキュメントのネイティブ エンコードを、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によって内部的に使用される正規化された UTF-8 エンコードに変換できます。</span><span class="sxs-lookup"><span data-stu-id="05311-105">This encoding object allows the flat file parser to convert the native encoding of an inbound flat file document into the normalized UTF-8 encoding that is used internally by Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="05311-106">また、フラット ファイル シリアライザーでは、内部の UTF-8 エンコードをフラット ファイル ドキュメントのネイティブ エンコードに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="05311-106">The encoding object also allows the flat file serializer to convert the internal UTF-8 encoding back into the native encoding of the flat file document.</span></span>  
  
 <span data-ttu-id="05311-107">設定、**コード ページ**プロパティは、フラット ファイル ビジネス ドキュメントで使用される文字エンコード体系を決定するとき、排他的ではないが、重要な役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="05311-107">The setting of the **Code Page** property plays an important, but not exclusive, role in determining the character encoding scheme used by your flat file business documents.</span></span> <span data-ttu-id="05311-108">送信メッセージがフラット ファイル形式に変換される場合、フラット ファイル アセンブラーが文字をエンコードする方法とフラット ファイル逆アセンブラーが受信フラット ファイル メッセージを解釈する方法を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="05311-108">You must consider how inbound flat file messages are interpreted by the flat file disassembler as well as how the flat file assembler will encode characters as outbound messages are translated into flat file format.</span></span>  

## <a name="character-encoding"></a><span data-ttu-id="05311-109">文字エン コード</span><span class="sxs-lookup"><span data-stu-id="05311-109">Character encoding</span></span>  
 <span data-ttu-id="05311-110">次のように、特定のインスタンス メッセージの文字エンコードを処理する方法を決める複数の要因があります。</span><span class="sxs-lookup"><span data-stu-id="05311-110">There are multiple factors that play a role in determining how character encoding for a given instance message is handled, as follows:</span></span>  
  
-   <span data-ttu-id="05311-111">フラット ファイル インスタンス メッセージを逆アセンブルする場合、次のアルゴリズムを使用して、エンコード情報の決定および保存が行われます。</span><span class="sxs-lookup"><span data-stu-id="05311-111">When disassembling a flat file instance message, the following algorithm is used to determine and preserve encoding information:</span></span>  
  
    1.  <span data-ttu-id="05311-112">場合、 **Charset**メッセージのボディ部では設定された場合、その値を使用します。</span><span class="sxs-lookup"><span data-stu-id="05311-112">If the **Charset** in the Message body part is set, its value is used.</span></span>  
  
    2.  <span data-ttu-id="05311-113">それ以外の場合、エンベロープ (またはドキュメント) スキーマでは、コード ページを使用して、指定する場合、**コード ページ**プロパティ、その値を使用します。</span><span class="sxs-lookup"><span data-stu-id="05311-113">Otherwise, if the envelope (or document) schema specifies a code page using the **Code Page** property, its value is used.</span></span>  
  
    3.  <span data-ttu-id="05311-114">上記に該当しない場合、バイト順マークが存在すると、その値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="05311-114">Otherwise, if a byte order mark is present, its value is used.</span></span>  
  
    4.  <span data-ttu-id="05311-115">上記に該当しない場合、UTF-8 を使用します。</span><span class="sxs-lookup"><span data-stu-id="05311-115">Otherwise, assume UTF-8.</span></span>  
  
-   <span data-ttu-id="05311-116">フラット ファイル インスタンス メッセージをアセンブルする場合、次のアルゴリズムを使用して、デコードで使用する文字セットが決まります。</span><span class="sxs-lookup"><span data-stu-id="05311-116">When assembling a flat file instance message, the following algorithm is used to determine the character set to use for decoding:</span></span>  
  
-   <span data-ttu-id="05311-117">場合、 **XMLNorm.TargetCharset**メッセージ コンテキスト プロパティが設定されて、その値を使用します。</span><span class="sxs-lookup"><span data-stu-id="05311-117">If the **XMLNorm.TargetCharset** message context property is set, its value is used.</span></span>  
  
-   <span data-ttu-id="05311-118">それ以外の場合、 **TargetCharset**アセンブラー (デザイン時) プロパティが設定されて、その値を使用します。</span><span class="sxs-lookup"><span data-stu-id="05311-118">Otherwise, if the **TargetCharset** assembler (design-time) property is set, its value is used.</span></span>  
  
-   <span data-ttu-id="05311-119">それ以外の場合、エンベロープ (またはドキュメント) スキーマでは、コード ページを使用して、指定する場合、**コード ページ**プロパティ、その値を使用します。</span><span class="sxs-lookup"><span data-stu-id="05311-119">Otherwise, if the envelope (or document) schema specifies a code page using the **Code Page** property, its value is used.</span></span>  
  
    1.  <span data-ttu-id="05311-120">それ以外の場合、 **SourceCharset**メッセージ コンテキスト プロパティが設定されて、その値を使用します。</span><span class="sxs-lookup"><span data-stu-id="05311-120">Otherwise, if the **SourceCharset** message context property is set, its value is used.</span></span>  
  
    2.  <span data-ttu-id="05311-121">それ以外の場合、utf-8 を使用します。</span><span class="sxs-lookup"><span data-stu-id="05311-121">Otherwise, use UTF-8.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05311-122">参照</span><span class="sxs-lookup"><span data-stu-id="05311-122">See Also</span></span>  
 <span data-ttu-id="05311-123">**ファイル メッセージ スキーマをフラットを作成する際の考慮事項**と**コード ページ (フラット ファイル スキーマのノード プロパティ)**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="05311-123">**Considerations When Creating Flat File Message Schemas** and **Code Page (Node Property of Flat File Schemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>