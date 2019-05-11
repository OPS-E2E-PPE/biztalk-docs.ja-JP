---
title: マップのリンク |Microsoft Docs
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
ms.openlocfilehash: ba3da2b4bebcb559616aa583fd24fd183fd085c6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329653"
---
# <a name="links-in-maps"></a><span data-ttu-id="13680-102">マップのリンク</span><span class="sxs-lookup"><span data-stu-id="13680-102">Links in Maps</span></span>
<span data-ttu-id="13680-103">リンクは、要素または属性は、入力インスタンス メッセージ内のデータ要素または属性の出力インスタンスにコピーの基本的な機能を指定します。</span><span class="sxs-lookup"><span data-stu-id="13680-103">Links specify the basic function of copying data from an element or attribute in an input instance message to an element or attribute in an output instance.</span></span> <span data-ttu-id="13680-104">デザイン時に、元と送信先スキーマのレコードとフィールド間のリンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="13680-104">You create links between records and fields in the source and destination schemas at design time.</span></span> <span data-ttu-id="13680-105">これは、ドライブの作成、送信元スキーマに準拠している入力インスタンス メッセージから送信先スキーマに準拠した出力インスタンス メッセージの実行時にします。</span><span class="sxs-lookup"><span data-stu-id="13680-105">This drives the creation, at run time, of an output instance message conforming to the destination schema from an input instance message conforming to the source schema.</span></span>  
  
 <span data-ttu-id="13680-106">BizTalk マッパーでは、1 対 1 のリンクと一対多のリンクをサポートします。</span><span class="sxs-lookup"><span data-stu-id="13680-106">BizTalk Mapper supports one-to-one links and one-to-many links.</span></span> <span data-ttu-id="13680-107">たとえば、リンクに接続できます 1 つのレコードまたはフィールド、送信元スキーマから 1 つのレコードまたはフィールドを送信先スキーマの。</span><span class="sxs-lookup"><span data-stu-id="13680-107">For example, a link can connect a single record or field from the source schema to a single record or field in the destination schema.</span></span> <span data-ttu-id="13680-108">リンク接続もできます、1 つのレコードまたはフィールド、送信元スキーマから複数のレコードまたはフィールドを送信先スキーマに。</span><span class="sxs-lookup"><span data-stu-id="13680-108">A link can also connect a single record or field from the source schema to multiple records or fields in the destination schema.</span></span>  
  
 <span data-ttu-id="13680-109">リンクにも接続できます複数のレコードまたはフィールド、送信元スキーマから functoid、単一 (または複数) のレコードまたは送信先スキーマのフィールドに接続します。</span><span class="sxs-lookup"><span data-stu-id="13680-109">Links can also connect multiple records or fields from the source schema to a functoid, which then connects to a single (or multiple) record(s) and/or field(s) in the destination schema.</span></span> <span data-ttu-id="13680-110">一般に、複数のソース レコードからリンクを直接または 1 つの宛先のレコードまたはフィールドにフィールドが有効でないし、警告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="13680-110">In general, direct links from multiple source records or fields to a single destination record or field are not valid and produce a warning.</span></span> <span data-ttu-id="13680-111">1 つの例外は、**ループ**functoid。</span><span class="sxs-lookup"><span data-stu-id="13680-111">One exception to this is the **Looping** functoid.</span></span> <span data-ttu-id="13680-112">詳細については、**ループ**functoid を参照してください[ループ Functoid](../core/looping-functoid.md)します。</span><span class="sxs-lookup"><span data-stu-id="13680-112">For more information about the **Looping** functoid, see [Looping Functoid](../core/looping-functoid.md).</span></span>  
  
 <span data-ttu-id="13680-113">このセクションのトピックでは、BizTalk マッパーにおけるリンクの作成と操作に関連する概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="13680-113">The topics in this section describe concepts related to creating and working with links in BizTalk Mapper.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="13680-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="13680-114">In This Section</span></span>  
  
-   [<span data-ttu-id="13680-115">リンクの種類</span><span class="sxs-lookup"><span data-stu-id="13680-115">Types of Links</span></span>](../core/types-of-links.md)  
  
-   [<span data-ttu-id="13680-116">リンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="13680-116">Creating Links</span></span>](../core/creating-links.md)  
  
-   [<span data-ttu-id="13680-117">リンクを構成します。</span><span class="sxs-lookup"><span data-stu-id="13680-117">Configuring Links</span></span>](../core/configuring-links.md)  
  
-   [<span data-ttu-id="13680-118">レコード間のリンク</span><span class="sxs-lookup"><span data-stu-id="13680-118">Record-to-Record Linking</span></span>](../core/record-to-record-linking.md)  
  
-   [<span data-ttu-id="13680-119">anyElement ノードおよび anyAttribute ノード間のリンク</span><span class="sxs-lookup"><span data-stu-id="13680-119">Links To and From the Any Element and anyAttribute Nodes</span></span>](../core/links-to-and-from-the-any-element-and-anyattribute-nodes.md)  
  
-   [<span data-ttu-id="13680-120">コンパイラ ディレクティブおよびリンク</span><span class="sxs-lookup"><span data-stu-id="13680-120">Compiler Directives and Links</span></span>](../core/compiler-directives-and-links.md)