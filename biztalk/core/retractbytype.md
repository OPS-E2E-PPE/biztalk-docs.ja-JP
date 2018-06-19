---
title: RetractByType |Microsoft ドキュメント
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
ms.openlocfilehash: da8cd4581007ad2bd93ed66ebce4f5de6378280c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268738"
---
# <a name="retractbytype"></a><span data-ttu-id="17116-102">[種類別の取り消し]</span><span class="sxs-lookup"><span data-stu-id="17116-102">RetractByType</span></span>
<span data-ttu-id="17116-103">**RetractByType**関数によって、作業メモリに指定した型のすべてのインスタンスが取り消された、 **Retract**関数には、特定の種類の特定の項目だけが取り消されます。</span><span class="sxs-lookup"><span data-stu-id="17116-103">The **RetractByType** function retracts all instances of a specified type in the working memory, whereas the **Retract**function retracts only specific items of a certain type.</span></span> <span data-ttu-id="17116-104">以下に述べる方法、 **RetractByType**関数は、さまざまな種類のエンティティで機能します。</span><span class="sxs-lookup"><span data-stu-id="17116-104">The following paragraphs describe how the **RetractByType** function works with entities of different types.</span></span>  
  
## <a name="net-objects"></a><span data-ttu-id="17116-105">.NET オブジェクト</span><span class="sxs-lookup"><span data-stu-id="17116-105">.NET Objects</span></span>  
 <span data-ttu-id="17116-106">特定のクラスの種類のすべてのオブジェクトが作業メモリから取り消されます。</span><span class="sxs-lookup"><span data-stu-id="17116-106">All objects for a given class type are retracted from working memory.</span></span> <span data-ttu-id="17116-107">クラスを .NET クラス ファクト ペインからドラッグするだけ、 **RetractByType**関数。</span><span class="sxs-lookup"><span data-stu-id="17116-107">You simply drag the class from the .NET Classes fact pane into the **RetractByType** function.</span></span>  
  
## <a name="typedxmldocument"></a><span data-ttu-id="17116-108">TypedXmlDocument</span><span class="sxs-lookup"><span data-stu-id="17116-108">TypedXmlDocument</span></span>  
 <span data-ttu-id="17116-109">すべてのインスタンスが取り消されます。</span><span class="sxs-lookup"><span data-stu-id="17116-109">All instances are retracted.</span></span> <span data-ttu-id="17116-110">つまり、すべて**TypedXmlDocument**同じ s **DocumentType.Selector**が取り消されます。</span><span class="sxs-lookup"><span data-stu-id="17116-110">This means that all **TypedXmlDocument**s with the same **DocumentType.Selector** are retracted.</span></span> <span data-ttu-id="17116-111">XML スキーマ ファクト ペインから、適切なノードをドラッグする必要があります、 **RetractByType**関数。</span><span class="sxs-lookup"><span data-stu-id="17116-111">You should drag the appropriate node from the XML Schemas fact pane into the **RetractByType** function.</span></span> <span data-ttu-id="17116-112">一貫性のある、 **Retract**関数を実行する場合、 **RetractByType**ドキュメント ルート ノード上だけでなく、すべて**TypedXmlDocuments**そのアサート**DocumentType**で取り消される場合、すべての子が**TypedXmlDocuments** (**XmlNode**ツリー階層内の s) その親に関連付けられている**TypedXmlDocuments**も取り消されます。</span><span class="sxs-lookup"><span data-stu-id="17116-112">Consistent with the **Retract** function, if you perform a **RetractByType** on the document root node, not only will all **TypedXmlDocuments** asserted with that **DocumentType** be retracted, but all child **TypedXmlDocuments** (**XmlNode**s in the tree hierarchy) associated with those parent **TypedXmlDocuments** will also be retracted.</span></span>  
  
## <a name="typeddatatable-and-dataconnection"></a><span data-ttu-id="17116-113">TypedDataTable と DataConnection</span><span class="sxs-lookup"><span data-stu-id="17116-113">TypedDataTable and DataConnection</span></span>  
 <span data-ttu-id="17116-114">**取り消し**と**RetractByType**は両方の同等**TypedDataTable**と**DataConnection**です。</span><span class="sxs-lookup"><span data-stu-id="17116-114">**Retract** and **RetractByType** are equivalent for both **TypedDataTable** and **DataConnection**.</span></span> <span data-ttu-id="17116-115">**DataSetName.DataTableName**一意の識別子は、両方の種類の 1 つだけインスタンスが、エンジンで任意の時点にします。</span><span class="sxs-lookup"><span data-stu-id="17116-115">Because **DataSetName.DataTableName** is a unique identifier for both types, there is only one instance in the engine at any point in time.</span></span> <span data-ttu-id="17116-116">同様に**Retract**、テーブルをドラッグする、 **RetractByType**関数。</span><span class="sxs-lookup"><span data-stu-id="17116-116">As with **Retract**, you drag the table into the **RetractByType** function.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17116-117">参照</span><span class="sxs-lookup"><span data-stu-id="17116-117">See Also</span></span>  
 [<span data-ttu-id="17116-118">エンジン制御関数</span><span class="sxs-lookup"><span data-stu-id="17116-118">Engine Control Functions</span></span>](../core/engine-control-functions.md)