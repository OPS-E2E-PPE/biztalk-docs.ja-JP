---
title: "エラー - マップを移行する必要があります |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.mapNeedsMigrating
ms.assetid: f10af4a4-6e40-4eec-a2fd-e526821aebe6
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f49ef4aae0db47216f6117f1053185df6fae0a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---map-needs-to-be-migrated"></a><span data-ttu-id="45660-102">エラー - マップを移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45660-102">Error - Map Needs to be Migrated</span></span>
<span data-ttu-id="45660-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="45660-103">**Error Code**</span></span>  
  
 <span data-ttu-id="45660-104">btm1064</span><span class="sxs-lookup"><span data-stu-id="45660-104">btm1064</span></span>  
  
 <span data-ttu-id="45660-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="45660-105">**Explanation**</span></span>  
  
 <span data-ttu-id="45660-106">マップは、以前のバージョンの BizTalk マッパーを使用して作成されているため、コンパイルできません。</span><span class="sxs-lookup"><span data-stu-id="45660-106">The map cannot be compiled because it was created using a previous version of BizTalk Mapper.</span></span> <span data-ttu-id="45660-107">このようなマップをコンパイルするには、現在のバージョンの BizTalk マッパーに移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45660-107">You must migrate such maps to this version of BizTalk Mapper before they can be compiled.</span></span>  
  
 <span data-ttu-id="45660-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="45660-108">**User Action**</span></span>  
  
 <span data-ttu-id="45660-109">このマップを現在のバージョンの BizTalk マッパーに移行します。これには、マップのファイル拡張子を "xml" から "btm" に変更し、ファイルを適切な Microsoft BizTalk Server プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="45660-109">Migrate the map to the current version of BizTalk Mapper by changing its file extension from "xml" to "btm", adding it to the relevant Microsoft BizTalk Server project.</span></span> <span data-ttu-id="45660-110">使用して、**既存項目の追加**コマンドで使用できる、**ファイル**メニューと BizTalk のショートカット メニューの ソリューション エクスプローラで、プロジェクトおよびソリューション エクスプ ローラーでダブルクリックして、マップを開きます。</span><span class="sxs-lookup"><span data-stu-id="45660-110">Use the **Add Existing Item** command available on the **File** menu and on the shortcut menu for the BizTalk project in Solution Explorer, and then open the map by double-clicking it in Solution Explorer.</span></span> <span data-ttu-id="45660-111">ヘルプの各トピックを順番に参照している場合は、最初の 2 つの手順は既に完了しています。</span><span class="sxs-lookup"><span data-stu-id="45660-111">Because you have reached this topic, you have probably already performed the first two steps.</span></span> <span data-ttu-id="45660-112">現在のバージョンの BizTalk マッパーでマップを開くだけで、非常に簡単にマップを移行できます。</span><span class="sxs-lookup"><span data-stu-id="45660-112">Simply opening the map in the current version of BizTalk Mapper will perform an on-the-fly migration of the map.</span></span>