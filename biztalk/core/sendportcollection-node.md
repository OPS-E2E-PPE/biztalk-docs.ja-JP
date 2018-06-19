---
title: SendPortCollection ノード |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SendPortCollection node [binding file]
ms.assetid: 2084507e-ef70-4828-a15f-51d676b14333
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2cf0a968ef995bfdb5a551d16b204743d507b25
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269674"
---
# <a name="sendportcollection-node"></a><span data-ttu-id="7ee6b-102">SendPortCollection ノード</span><span class="sxs-lookup"><span data-stu-id="7ee6b-102">SendPortCollection Node</span></span>
<span data-ttu-id="7ee6b-103">バインド ファイルの SendPortCollection ノードは、そのバインド ファイルでエクスポートされる送信ポートに関する情報を含むすべての SendPort ノードの親ノードです。</span><span class="sxs-lookup"><span data-stu-id="7ee6b-103">The SendPortCollection node of a binding file is the parent node for all of the SendPort nodes which contain specific information about a send port that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-sendportcollection-node"></a><span data-ttu-id="7ee6b-104">SendPortCollection ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="7ee6b-104">Nodes in the SendPortCollection node</span></span>  
 <span data-ttu-id="7ee6b-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="7ee6b-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="7ee6b-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="7ee6b-106">**Name**</span></span>|<span data-ttu-id="7ee6b-107">**ノード型**</span><span class="sxs-lookup"><span data-stu-id="7ee6b-107">**Node Type**</span></span>|<span data-ttu-id="7ee6b-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="7ee6b-108">**Data Type**</span></span>|<span data-ttu-id="7ee6b-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="7ee6b-109">**Description**</span></span>|<span data-ttu-id="7ee6b-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="7ee6b-110">**Restrictions**</span></span>|<span data-ttu-id="7ee6b-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="7ee6b-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="7ee6b-112">送信ポート</span><span class="sxs-lookup"><span data-stu-id="7ee6b-112">SendPort</span></span>](../core/sendport-sendportcollection-node.md)|<span data-ttu-id="7ee6b-113">レコード</span><span class="sxs-lookup"><span data-stu-id="7ee6b-113">Record</span></span>|<span data-ttu-id="7ee6b-114">SendPort (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="7ee6b-114">SendPort (ComplexType)</span></span>|<span data-ttu-id="7ee6b-115">バインド ファイルと共にエクスポートされる送信ポートに関する情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="7ee6b-115">Specifies information about a send port that is exported with the binding file.</span></span>|<span data-ttu-id="7ee6b-116">任意</span><span class="sxs-lookup"><span data-stu-id="7ee6b-116">Not required</span></span>|<span data-ttu-id="7ee6b-117">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="7ee6b-117">Default value: none</span></span>|