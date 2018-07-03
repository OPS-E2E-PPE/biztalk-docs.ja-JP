---
title: コンパイラ ディレクティブおよびリンク |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- compilier directives
- maps, compiling
- BizTalk Mapper, compiler directives
- links [maps], compiling
ms.assetid: 1655e10c-af98-4100-849d-b8214f93cfe9
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38e00b7d20e6fd0aff4f6af72377e301a812b8fd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992003"
---
# <a name="compiler-directives-and-links"></a><span data-ttu-id="29c6e-102">コンパイラ ディレクティブおよびリンク</span><span class="sxs-lookup"><span data-stu-id="29c6e-102">Compiler Directives and Links</span></span>
<span data-ttu-id="29c6e-103">リンクごとに、次の 2 つのコンパイラ ディレクティブを構成できます。</span><span class="sxs-lookup"><span data-stu-id="29c6e-103">You can configure the following two compiler directives on a link-by-link basis:</span></span>  
  
- <span data-ttu-id="29c6e-104">出力インスタンス メッセージの該当要素または属性の値として、入力インスタンス メッセージのどのデータを取得し、コピーするか。</span><span class="sxs-lookup"><span data-stu-id="29c6e-104">What data from the input instance message is retrieved and copied as the relevant element or attribute value in the output instance message.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="29c6e-105">この場合のデータには、要素または属性に関連付けられた値ではなく、要素または属性自体の名前をコピーすることもできます。</span><span class="sxs-lookup"><span data-stu-id="29c6e-105">Data here includes the option to copy the name of the element or attribute itself, rather than any value associated with the element or attribute.</span></span> <span data-ttu-id="29c6e-106">要素または属性の名前は、通常、XML インスタンス メッセージに保持されるデータの一部とは見なされません。</span><span class="sxs-lookup"><span data-stu-id="29c6e-106">Element and attribute names are not normally thought of as part of the data carried in an XML instance message.</span></span>  
  
- <span data-ttu-id="29c6e-107">送信元と送信先スキーマ間でのノードの照合方法。</span><span class="sxs-lookup"><span data-stu-id="29c6e-107">How node-matching is performed between the source and destination schemas.</span></span>  
  
  <span data-ttu-id="29c6e-108">このセクションでは、これらのディレクティブで使用可能なオプションについて詳細に説明します。</span><span class="sxs-lookup"><span data-stu-id="29c6e-108">This section provides a detailed explanation of these options available for these directives.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="29c6e-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="29c6e-109">In This Section</span></span>  
  
-   [<span data-ttu-id="29c6e-110">データ変換の構成</span><span class="sxs-lookup"><span data-stu-id="29c6e-110">Data Transformation Configuration</span></span>](../core/data-transformation-configuration.md)  
  
-   [<span data-ttu-id="29c6e-111">ノード階層レベルの照合</span><span class="sxs-lookup"><span data-stu-id="29c6e-111">Node-Hierarchy Level Matching</span></span>](../core/node-hierarchy-level-matching.md)