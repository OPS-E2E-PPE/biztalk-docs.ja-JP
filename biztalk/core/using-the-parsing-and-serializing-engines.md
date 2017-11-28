---
title: "文字列の解析を使用して、エンジンをシリアル化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parsing engine
- pipeline components [custom], engines
- serialization engine
- pipeline components [custom], assembling
- pipeline components [custom], parsing
ms.assetid: a9d19703-b074-402a-971a-b2a6cd5d0724
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e820b2dce1257ec948aa214c9fdf1d43a6a7152
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-parsing-and-serializing-engines"></a><span data-ttu-id="8899b-102">解析およびシリアル化エンジンを使用します。</span><span class="sxs-lookup"><span data-stu-id="8899b-102">Using the Parsing and Serializing Engines</span></span>
<span data-ttu-id="8899b-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には、フラット ファイル ドキュメントの解析とシリアル化の処理を容易にする解析エンジンとシリアル化エンジンが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="8899b-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] includes a parsing and serializing engine to simplify the process of parsing and serializing flat file documents.</span></span>  
  
 <span data-ttu-id="8899b-104">解析エンジンは、スキーマ主導のフレームワークで、さまざまな種類のドキュメント形式を XML として解析できます。</span><span class="sxs-lookup"><span data-stu-id="8899b-104">The parsing engine is a schema-driven framework that can parse many different document formats into XML.</span></span> <span data-ttu-id="8899b-105">また、カスタム形式の解析を容易にするための厳密に定義された機能拡張モデルも備えています。</span><span class="sxs-lookup"><span data-stu-id="8899b-105">In addition, the engine has a well-defined extensibility model to make parsing custom formats even easier.</span></span>  
  
 <span data-ttu-id="8899b-106">複雑な解析の場合は、逆アセンブラーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8899b-106">For complex parsing, disassemblers are used.</span></span> <span data-ttu-id="8899b-107">逆アセンブラーは、ネイティブ形式を XML に変換するだけでなく、単一ドキュメントから複数ドキュメントへの分割も行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8899b-107">In addition to converting the native format to XML, the disassembler can also separate a single document into multiple documents.</span></span>  
  
 <span data-ttu-id="8899b-108">シリアル化エンジンは解析エンジンと似ていますが、処理の方向が逆です。</span><span class="sxs-lookup"><span data-stu-id="8899b-108">The serializing engine is similar to the parsing engine, except that it works in the opposite direction.</span></span> <span data-ttu-id="8899b-109">解析エンジンがネイティブ形式を XML に変換するのに対し、シリアル化エンジンは XML をネイティブ形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="8899b-109">Where the parsing engine converts native formats to XML, the serializing engine converts XML to native formats.</span></span> <span data-ttu-id="8899b-110">また、解析エンジンが逆アセンブラーを使用するのと同様に、シリアル化エンジンはアセンブラーを使用します。</span><span class="sxs-lookup"><span data-stu-id="8899b-110">And just as the parsing engine uses disassemblers, the serializing engine uses assemblers.</span></span>  
  
 <span data-ttu-id="8899b-111">このセクションでは、文字エンコードの実行方法、XSD (XML スキーマ定義) 言語スキーマに基づく解析とシリアル化の方法、および解析エンジンとシリアル化エンジンの API を使用するその他一般的なタスクの実行方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8899b-111">This section discusses how to perform character encoding, parse and serialize based on XML Schema definition language (XSD) schemas, and perform other common tasks using the parsing engine and serializing engine APIs.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8899b-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8899b-112">In This Section</span></span>  
  
-   [<span data-ttu-id="8899b-113">パイプライン コンポーネントの文字エンコーディングを実装します。</span><span class="sxs-lookup"><span data-stu-id="8899b-113">Implementing Character Encoding in a Pipeline Component</span></span>](../core/implementing-character-encoding-in-a-pipeline-component.md)  
  
-   [<span data-ttu-id="8899b-114">スキーマの使用</span><span class="sxs-lookup"><span data-stu-id="8899b-114">Using Schemas</span></span>](../core/using-schemas.md)  
  
-   [<span data-ttu-id="8899b-115">フラット ファイル解析エンジンの使用</span><span class="sxs-lookup"><span data-stu-id="8899b-115">Using the Flat File Parsing Engine</span></span>](../core/using-the-flat-file-parsing-engine.md)  
  
-   [<span data-ttu-id="8899b-116">フラット ファイルのシリアル化エンジンを使用します。</span><span class="sxs-lookup"><span data-stu-id="8899b-116">Using the Flat File Serializing Engine</span></span>](../core/using-the-flat-file-serializing-engine.md)