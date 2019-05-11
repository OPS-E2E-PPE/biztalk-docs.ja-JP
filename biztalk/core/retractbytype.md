---
title: RetractByType |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RetractByType function [Business Rules Engine], TypedXMLDocument
- RetractByType function [Business Rules Engine]
- RetractByType function [Business Rules Engine], .NET objects
- RetractByType function [Business Rules Engine], TypedData table
- RetractByType function [Business Rules Engine], DataConnection
- .NET objects
ms.assetid: e8867553-ee3c-46be-84cd-d5373eaf3337
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 460684c52f00df531eb73f397fdc187829522be2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65309507"
---
# <a name="retractbytype"></a><span data-ttu-id="14ff7-102">RetractByType</span><span class="sxs-lookup"><span data-stu-id="14ff7-102">RetractByType</span></span>
<span data-ttu-id="14ff7-103">**RetractByType**関数には、作業メモリ内の指定した型のすべてのインスタンスが取り消されますが、 **Retract**関数は、特定の種類の特定の項目だけを取り消します。</span><span class="sxs-lookup"><span data-stu-id="14ff7-103">The **RetractByType** function retracts all instances of a specified type in the working memory, whereas the **Retract**function retracts only specific items of a certain type.</span></span> <span data-ttu-id="14ff7-104">次の段落を記述する方法、 **RetractByType**関数は、さまざまな種類のエンティティを操作します。</span><span class="sxs-lookup"><span data-stu-id="14ff7-104">The following paragraphs describe how the **RetractByType** function works with entities of different types.</span></span>  
  
## <a name="net-objects"></a><span data-ttu-id="14ff7-105">.NET オブジェクト</span><span class="sxs-lookup"><span data-stu-id="14ff7-105">.NET Objects</span></span>  
 <span data-ttu-id="14ff7-106">指定されたクラス型のすべてのオブジェクトが作業メモリから取り消されます。</span><span class="sxs-lookup"><span data-stu-id="14ff7-106">All objects for a given class type are retracted from working memory.</span></span> <span data-ttu-id="14ff7-107">クラスに .NET クラス ファクト ペインからドラッグする、 **RetractByType**関数。</span><span class="sxs-lookup"><span data-stu-id="14ff7-107">You simply drag the class from the .NET Classes fact pane into the **RetractByType** function.</span></span>  
  
## <a name="typedxmldocument"></a><span data-ttu-id="14ff7-108">TypedXmlDocument</span><span class="sxs-lookup"><span data-stu-id="14ff7-108">TypedXmlDocument</span></span>  
 <span data-ttu-id="14ff7-109">すべてのインスタンスが取り消されます。</span><span class="sxs-lookup"><span data-stu-id="14ff7-109">All instances are retracted.</span></span> <span data-ttu-id="14ff7-110">つまり、すべて**TypedXmlDocument**を同じ**DocumentType.Selector**が取り消されます。</span><span class="sxs-lookup"><span data-stu-id="14ff7-110">This means that all **TypedXmlDocument**s with the same **DocumentType.Selector** are retracted.</span></span> <span data-ttu-id="14ff7-111">XML スキーマ ファクト ペインから、適切なノードをドラッグする必要があります、 **RetractByType**関数。</span><span class="sxs-lookup"><span data-stu-id="14ff7-111">You should drag the appropriate node from the XML Schemas fact pane into the **RetractByType** function.</span></span> <span data-ttu-id="14ff7-112">一貫性のある、 **Retract**関数を実行する場合、 **RetractByType**ドキュメントのルート ノードにするだけでなくすべて**TypedXmlDocuments**そのアサート**DocumentType**すべての子ですが、取り消す**TypedXmlDocuments** (**XmlNode**ツリー階層内の) その親に関連付けられている**TypedXmlDocuments**も取り消されます。</span><span class="sxs-lookup"><span data-stu-id="14ff7-112">Consistent with the **Retract** function, if you perform a **RetractByType** on the document root node, not only will all **TypedXmlDocuments** asserted with that **DocumentType** be retracted, but all child **TypedXmlDocuments** (**XmlNode**s in the tree hierarchy) associated with those parent **TypedXmlDocuments** will also be retracted.</span></span>  
  
## <a name="typeddatatable-and-dataconnection"></a><span data-ttu-id="14ff7-113">TypedDataTable と DataConnection</span><span class="sxs-lookup"><span data-stu-id="14ff7-113">TypedDataTable and DataConnection</span></span>  
 <span data-ttu-id="14ff7-114">**取り消し**と**RetractByType**の両方に対応が**TypedDataTable**と**DataConnection**します。</span><span class="sxs-lookup"><span data-stu-id="14ff7-114">**Retract** and **RetractByType** are equivalent for both **TypedDataTable** and **DataConnection**.</span></span> <span data-ttu-id="14ff7-115">**DataSetName.DataTableName**一意の識別子は、両方の種類はインスタンス 1 つだけ、エンジンで任意の時点にある時間。</span><span class="sxs-lookup"><span data-stu-id="14ff7-115">Because **DataSetName.DataTableName** is a unique identifier for both types, there is only one instance in the engine at any point in time.</span></span> <span data-ttu-id="14ff7-116">同様**Retract**、テーブルをドラッグする、 **RetractByType**関数。</span><span class="sxs-lookup"><span data-stu-id="14ff7-116">As with **Retract**, you drag the table into the **RetractByType** function.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14ff7-117">参照</span><span class="sxs-lookup"><span data-stu-id="14ff7-117">See Also</span></span>  
 [<span data-ttu-id="14ff7-118">エンジン制御関数</span><span class="sxs-lookup"><span data-stu-id="14ff7-118">Engine Control Functions</span></span>](../core/engine-control-functions.md)