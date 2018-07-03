---
title: マップについての詳細 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- file types, maps
- BizTalk Mapper
- maps, file type
- maps, about maps
- BizTalk Mapper, about BizTalk Mapper
- maps
ms.assetid: 512ef2b7-3d01-4fcf-bb38-de68ec608b07
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd27793be4f1b1d9fd2b404f9a2a3a678b7622b2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966283"
---
# <a name="about-maps"></a><span data-ttu-id="af7e5-102">マップについて</span><span class="sxs-lookup"><span data-stu-id="af7e5-102">About Maps</span></span>
<span data-ttu-id="af7e5-103">BizTalk マッパーでは、リンクと Functoid を使って入力スキーマと出力スキーマの関係を定義できます。</span><span class="sxs-lookup"><span data-stu-id="af7e5-103">Using BizTalk Mapper, you define the relationship between an input and an output schema by using links and functoids.</span></span> <span data-ttu-id="af7e5-104">リンクは、レコードまたはフィールドのデータを直接コピーするような関係を定義するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="af7e5-104">A link defines a direct data copy of a record or field.</span></span> <span data-ttu-id="af7e5-105">スキーマに含まれる項目どうしを直接接続したり、Functoid との接続を定義する場合にリンクが使用されます。</span><span class="sxs-lookup"><span data-stu-id="af7e5-105">Links may directly connect to items in the other schema, or they may form connections to functoids.</span></span> <span data-ttu-id="af7e5-106">Functoid は、次のように複雑なデータ操作を実行するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="af7e5-106">Functoids perform more complex data manipulations, such as:</span></span>  
  
- <span data-ttu-id="af7e5-107">送信元スキーマに含まれる 2 つのフィールドの値を加算し、その結果を送信先スキーマにコピーする。</span><span class="sxs-lookup"><span data-stu-id="af7e5-107">Adding the value of two fields in the source schema and copying the result to the destination schema.</span></span>  
  
- <span data-ttu-id="af7e5-108">文字を ASCII 形式に変換する。</span><span class="sxs-lookup"><span data-stu-id="af7e5-108">Converting a character to its ASCII format.</span></span>  
  
- <span data-ttu-id="af7e5-109">繰り返しレコードのフィールドの平均を取得し、その結果を送信先スキーマのフィールドにコピーする。</span><span class="sxs-lookup"><span data-stu-id="af7e5-109">Returning the average of a field in a repeating record and copying the result to a field in the destination schema.</span></span>  
  
  <span data-ttu-id="af7e5-110">BizTalk マッパーでは、.btm という拡張子のファイルにマップが保存されます。</span><span class="sxs-lookup"><span data-stu-id="af7e5-110">BizTalk Mapper stores maps in a file with a .btm extension.</span></span> <span data-ttu-id="af7e5-111">ファイルは、マップに関するデザイン情報を保存します: functoid、スキーマ項目と functoid 間のリンクを表すアイコンの場所と、マップに関するその他の情報。</span><span class="sxs-lookup"><span data-stu-id="af7e5-111">The file saves design information about the map—the locations of icons representing functoids, the links between schema items and functoids, and other information about the map.</span></span> <span data-ttu-id="af7e5-112">マップをビルドまたはコンパイルすると、こうしたマップに関する情報が、BizTalk マッパーによって対応する XSLT (Extensible Language Stylesheet Transformations) スタイルシートに変換されます。</span><span class="sxs-lookup"><span data-stu-id="af7e5-112">When you build or compile the map, BizTalk Mapper converts the information about the map into the corresponding Extensible Language Stylesheet Transformations (XSLT) stylesheet.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="af7e5-113">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] コンパイラには、単一のプロジェクトにおけるすべての文字列の合計サイズについて 16 MB の制限があります。</span><span class="sxs-lookup"><span data-stu-id="af7e5-113">The [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] compiler has a 16-megabyte limitation on the total size of all strings in a single project.</span></span> <span data-ttu-id="af7e5-114">BizTalk プロジェクトをコンパイルしている間、コンパイラはアセンブリ作成のスキーマ、マップ、およびオーケストレーションをシリアル化し、これによってすべての文字列の合計サイズが増加し、制限を超える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="af7e5-114">While compiling BizTalk projects, the compiler serializes schemas, maps, and orchestrations for creating the assemblies, and this increases the total size of all strings, which may exceed the limitation.</span></span> <span data-ttu-id="af7e5-115">この問題を解決するには、各プロジェクト内のすべての文字列の合計サイズが 16 MB より小さくなるようにスキームまたはマップを別の BizTalk プロジェクト (通常は、同じソリューションの下) に入れることで、プロジェクトを再編成します。</span><span class="sxs-lookup"><span data-stu-id="af7e5-115">To resolve this issue, you can reorganize your project by putting schemas and/or maps into different Biztalk projects (Typically, under the same solution), such that  the total size of all strings in each project is less than 16 MB.</span></span>  
  
 <span data-ttu-id="af7e5-116">作成したマップを使用することで、データをさまざまな形式に変換できます。たとえば、単一の取引先固有の形式に変換したり、複数の取引先とやり取りするための形式に変換することもできます。</span><span class="sxs-lookup"><span data-stu-id="af7e5-116">The maps that you create can transform or translate data, and they can be specific to a single trading partner or be used with many trading partners.</span></span> <span data-ttu-id="af7e5-117">このセクションの各トピックでは、スキーマのマッピングに関する概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="af7e5-117">The topics in this section provide an introduction to the concepts involved in mapping schemas.</span></span> <span data-ttu-id="af7e5-118">マップの背景については、次を参照してください。[マップ](../core/maps.md)します。</span><span class="sxs-lookup"><span data-stu-id="af7e5-118">For background information about maps, see [Maps](../core/maps.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="af7e5-119">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="af7e5-119">In This Section</span></span>  
  
-   [<span data-ttu-id="af7e5-120">マップのリンク</span><span class="sxs-lookup"><span data-stu-id="af7e5-120">Links in Maps</span></span>](../core/links-in-maps.md)  
  
-   [<span data-ttu-id="af7e5-121">マップの Functoid</span><span class="sxs-lookup"><span data-stu-id="af7e5-121">Functoids in Maps</span></span>](../core/functoids-in-maps.md)  
  
-   [<span data-ttu-id="af7e5-122">マップのコンパイルとテスト</span><span class="sxs-lookup"><span data-stu-id="af7e5-122">Map Compilation and Testing</span></span>](../core/map-compilation-and-testing.md)