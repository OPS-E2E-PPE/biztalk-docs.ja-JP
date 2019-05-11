---
title: 解析を使用して、エンジンをシリアル化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- parsing engine
- pipeline components [custom], engines
- serialization engine
- pipeline components [custom], assembling
- pipeline components [custom], parsing
ms.assetid: a9d19703-b074-402a-971a-b2a6cd5d0724
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c78e0dcffd680136cd2a140f18787793b43a4913
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302983"
---
# <a name="using-the-parsing-and-serializing-engines"></a><span data-ttu-id="57978-102">解析およびシリアル化エンジンを使用します。</span><span class="sxs-lookup"><span data-stu-id="57978-102">Using the Parsing and Serializing Engines</span></span>
<span data-ttu-id="57978-103">Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解析とシリアル化の解析とフラット ファイル ドキュメントをシリアル化プロセスを簡易化エンジンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="57978-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] includes a parsing and serializing engine to simplify the process of parsing and serializing flat file documents.</span></span>  
  
 <span data-ttu-id="57978-104">解析エンジンは、スキーマ主導のフレームワークで、多くのさまざまなドキュメント形式を XML に解析できます。</span><span class="sxs-lookup"><span data-stu-id="57978-104">The parsing engine is a schema-driven framework that can parse many different document formats into XML.</span></span> <span data-ttu-id="57978-105">また、エンジンより簡単にカスタム形式の解析を明確に定義された機能拡張モデル。</span><span class="sxs-lookup"><span data-stu-id="57978-105">In addition, the engine has a well-defined extensibility model to make parsing custom formats even easier.</span></span>  
  
 <span data-ttu-id="57978-106">複雑な解析、逆アセンブラーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="57978-106">For complex parsing, disassemblers are used.</span></span> <span data-ttu-id="57978-107">ネイティブ形式を XML に変換するだけでなく、逆アセンブラーは 1 つのドキュメントを複数のドキュメントに分割することができますも。</span><span class="sxs-lookup"><span data-stu-id="57978-107">In addition to converting the native format to XML, the disassembler can also separate a single document into multiple documents.</span></span>  
  
 <span data-ttu-id="57978-108">シリアル化エンジンは、反対方向に正常に機能する点を除いて、解析エンジンと似ています。</span><span class="sxs-lookup"><span data-stu-id="57978-108">The serializing engine is similar to the parsing engine, except that it works in the opposite direction.</span></span> <span data-ttu-id="57978-109">解析エンジンでは、ネイティブ形式を XML に変換して、場所、シリアル化エンジンは、XML をネイティブ形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="57978-109">Where the parsing engine converts native formats to XML, the serializing engine converts XML to native formats.</span></span> <span data-ttu-id="57978-110">解析エンジンは、逆アセンブラーを使用すると同様、シリアル化エンジンはアセンブラーを使用します。</span><span class="sxs-lookup"><span data-stu-id="57978-110">And just as the parsing engine uses disassemblers, the serializing engine uses assemblers.</span></span>  
  
 <span data-ttu-id="57978-111">文字エン コードの実行、解析し、シリアル化する方法を説明する XML スキーマ定義言語 (XSD) スキーマに基づいており、解析エンジンおよびシリアル化エンジン Api を使用して他の一般的なタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="57978-111">This section discusses how to perform character encoding, parse and serialize based on XML Schema definition language (XSD) schemas, and perform other common tasks using the parsing engine and serializing engine APIs.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="57978-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="57978-112">In This Section</span></span>  
  
-   [<span data-ttu-id="57978-113">パイプライン コンポーネントでの文字エンコードの実装</span><span class="sxs-lookup"><span data-stu-id="57978-113">Implementing Character Encoding in a Pipeline Component</span></span>](../core/implementing-character-encoding-in-a-pipeline-component.md)  
  
-   [<span data-ttu-id="57978-114">スキーマの使用</span><span class="sxs-lookup"><span data-stu-id="57978-114">Using Schemas</span></span>](../core/using-schemas.md)  
  
-   [<span data-ttu-id="57978-115">フラット ファイル解析エンジンの使用</span><span class="sxs-lookup"><span data-stu-id="57978-115">Using the Flat File Parsing Engine</span></span>](../core/using-the-flat-file-parsing-engine.md)  
  
-   [<span data-ttu-id="57978-116">フラット ファイル シリアル化エンジンの使用</span><span class="sxs-lookup"><span data-stu-id="57978-116">Using the Flat File Serializing Engine</span></span>](../core/using-the-flat-file-serializing-engine.md)