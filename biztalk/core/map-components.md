---
title: コンポーネントのマップ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- file types, maps
- BizTalk Mapper, output
- maps, file type
- maps, file contents
- BizTalk Mapper, file type
- maps, components
ms.assetid: be438d21-80a8-49d8-bd08-d85618ab23de
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58a7555ff45d25c4e131b05b078c713f7a169687
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262378"
---
# <a name="map-components"></a><span data-ttu-id="96088-102">マップの構成要素</span><span class="sxs-lookup"><span data-stu-id="96088-102">Map Components</span></span>
<span data-ttu-id="96088-103">マップの構成要素のほとんどは、.btm 拡張子を持つマップ ファイルに保存されます。</span><span class="sxs-lookup"><span data-stu-id="96088-103">Map files (having a .btm extension) store most of the components of a map.</span></span> <span data-ttu-id="96088-104">このファイルに格納される項目を次に示します。</span><span class="sxs-lookup"><span data-stu-id="96088-104">Items stored in the file include:</span></span>  
  
-   <span data-ttu-id="96088-105">送信元スキーマおよび送信先スキーマへの参照</span><span class="sxs-lookup"><span data-stu-id="96088-105">References to source and destination schemas</span></span>  
  
-   <span data-ttu-id="96088-106">リンク (リンクのプロパティを含む)</span><span class="sxs-lookup"><span data-stu-id="96088-106">Links, including the link properties</span></span>  
  
-   <span data-ttu-id="96088-107">Functoid とそのプロパティ (入力パラメーターなど)</span><span class="sxs-lookup"><span data-stu-id="96088-107">Functoids with their properties such as input parameters</span></span>  
  
-   <span data-ttu-id="96088-108">その他さまざまなプロパティ (グリッドやマップそのものに関連付けられたプロパティなど)</span><span class="sxs-lookup"><span data-stu-id="96088-108">Other miscellaneous properties such as those associated with the grid and the map itself.</span></span>  
  
 <span data-ttu-id="96088-109">BizTalk マッパーは、.btm ファイル内のマップを XSLT (Extensible Stylesheet Language Transformations) ファイルとしてコンパイルしますが、XSLT がこのファイルの一部になることはありません。</span><span class="sxs-lookup"><span data-stu-id="96088-109">Although BizTalk Mapper compiles the map in the .btm file into an Extensible Stylesheet Transformations (XSLT) file, the XSLT is not part of the file.</span></span> <span data-ttu-id="96088-110">BizTalk マッパーがマップの XSLT を生成するのは、プロジェクトのコンパイル時とマップの検証時だけです。</span><span class="sxs-lookup"><span data-stu-id="96088-110">BizTalk Mapper produces the XSLT for the map only when you compile the project or when you validate the map.</span></span> <span data-ttu-id="96088-111">BizTalk マッパーは、XSLT をプロジェクト アセンブリの一部としてパッケージします。</span><span class="sxs-lookup"><span data-stu-id="96088-111">BizTalk Mapper packages the XSLT as part of the project assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96088-112">参照</span><span class="sxs-lookup"><span data-stu-id="96088-112">See Also</span></span>  
 <span data-ttu-id="96088-113">[マップ](../core/maps.md) </span><span class="sxs-lookup"><span data-stu-id="96088-113">[Maps](../core/maps.md) </span></span>  
 [<span data-ttu-id="96088-114">BizTalk マッパーを使用してマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="96088-114">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)