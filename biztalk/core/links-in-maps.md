---
title: マップ内のリンク |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- functoid types, Looping
- Looping functoids
- maps, links
- BizTalk Mapper, links
ms.assetid: 3db77b8d-7b86-4c00-99a0-0513aff9b56b
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a32d2a9ef07cf2d79037d7983e49b26c6cfe5e81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262090"
---
# <a name="links-in-maps"></a><span data-ttu-id="e5c07-102">マップのリンク</span><span class="sxs-lookup"><span data-stu-id="e5c07-102">Links in Maps</span></span>
<span data-ttu-id="e5c07-103">リンクを使用して、入力インスタンス メッセージの要素や属性のデータを、出力インスタンスの要素や属性にコピーするときの基本的な機能を指定します。</span><span class="sxs-lookup"><span data-stu-id="e5c07-103">Links specify the basic function of copying data from an element or attribute in an input instance message to an element or attribute in an output instance.</span></span> <span data-ttu-id="e5c07-104">送信元スキーマと送信先スキーマのレコード間およびフィールド間のリンクをデザイン時に作成しておくと、</span><span class="sxs-lookup"><span data-stu-id="e5c07-104">You create links between records and fields in the source and destination schemas at design time.</span></span> <span data-ttu-id="e5c07-105">実行時には、送信元スキーマに準拠した入力インスタンス メッセージから、送信先スキーマに準拠した出力インスタンス メッセージが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e5c07-105">This drives the creation, at run time, of an output instance message conforming to the destination schema from an input instance message conforming to the source schema.</span></span>  
  
 <span data-ttu-id="e5c07-106">BizTalk マッパーは、1 対 1 および 1 対多のリンクをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e5c07-106">BizTalk Mapper supports one-to-one links and one-to-many links.</span></span> <span data-ttu-id="e5c07-107">たとえば、送信元スキーマの単一のレコードまたはフィールドを、送信先スキーマの単一のレコードまたはフィールドに接続するようなリンクを作成する以外に、</span><span class="sxs-lookup"><span data-stu-id="e5c07-107">For example, a link can connect a single record or field from the source schema to a single record or field in the destination schema.</span></span> <span data-ttu-id="e5c07-108">送信元スキーマの単一のレコードまたはフィールドを、送信先スキーマの複数のレコードまたはフィールドに接続するようなリンクを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="e5c07-108">A link can also connect a single record or field from the source schema to multiple records or fields in the destination schema.</span></span>  
  
 <span data-ttu-id="e5c07-109">送信元スキーマの複数のレコードまたはフィールドを Functoid に接続し、そこから、さらに、送信先スキーマの単一 (または複数) のレコードまたはフィールドに接続するようなリンクを作成することも可能です。</span><span class="sxs-lookup"><span data-stu-id="e5c07-109">Links can also connect multiple records or fields from the source schema to a functoid, which then connects to a single (or multiple) record(s) and/or field(s) in the destination schema.</span></span> <span data-ttu-id="e5c07-110">通常は、複数の送信元レコードまたはフィールドを、単一の送信先レコードまたはフィールドに直接接続することはできません。このような多対 1 のリンクでは警告が発生します。</span><span class="sxs-lookup"><span data-stu-id="e5c07-110">In general, direct links from multiple source records or fields to a single destination record or field are not valid and produce a warning.</span></span> <span data-ttu-id="e5c07-111">1 つの例外は、**ループ**functoid です。</span><span class="sxs-lookup"><span data-stu-id="e5c07-111">One exception to this is the **Looping** functoid.</span></span> <span data-ttu-id="e5c07-112">詳細については、**ループ**functoid を参照してください[ループ Functoid の](../core/looping-functoid.md)します。</span><span class="sxs-lookup"><span data-stu-id="e5c07-112">For more information about the **Looping** functoid, see [Looping Functoid](../core/looping-functoid.md).</span></span>  
  
 <span data-ttu-id="e5c07-113">このセクションの各トピックでは、BizTalk マッパーにおけるリンクの作成と使用に関連した概要が説明されています。</span><span class="sxs-lookup"><span data-stu-id="e5c07-113">The topics in this section describe concepts related to creating and working with links in BizTalk Mapper.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e5c07-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e5c07-114">In This Section</span></span>  
  
-   [<span data-ttu-id="e5c07-115">リンクの種類</span><span class="sxs-lookup"><span data-stu-id="e5c07-115">Types of Links</span></span>](../core/types-of-links.md)  
  
-   [<span data-ttu-id="e5c07-116">リンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="e5c07-116">Creating Links</span></span>](../core/creating-links.md)  
  
-   [<span data-ttu-id="e5c07-117">リンクを構成します。</span><span class="sxs-lookup"><span data-stu-id="e5c07-117">Configuring Links</span></span>](../core/configuring-links.md)  
  
-   [<span data-ttu-id="e5c07-118">レコードへのリンク</span><span class="sxs-lookup"><span data-stu-id="e5c07-118">Record-to-Record Linking</span></span>](../core/record-to-record-linking.md)  
  
-   [<span data-ttu-id="e5c07-119">リンクから、すべての要素および anyAttribute ノード</span><span class="sxs-lookup"><span data-stu-id="e5c07-119">Links To and From the Any Element and anyAttribute Nodes</span></span>](../core/links-to-and-from-the-any-element-and-anyattribute-nodes.md)  
  
-   [<span data-ttu-id="e5c07-120">コンパイラ ディレクティブおよびリンク</span><span class="sxs-lookup"><span data-stu-id="e5c07-120">Compiler Directives and Links</span></span>](../core/compiler-directives-and-links.md)