---
title: エラー - マップを移行する必要が |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.mapNeedsMigrating
ms.assetid: f10af4a4-6e40-4eec-a2fd-e526821aebe6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b1b1bee4bcdedecb31dc4b648b505d8ae53b4eb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389034"
---
# <a name="error---map-needs-to-be-migrated"></a><span data-ttu-id="42b00-102">エラー - マップを移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42b00-102">Error - Map Needs to be Migrated</span></span>
<span data-ttu-id="42b00-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="42b00-103">**Error Code**</span></span>  
  
 <span data-ttu-id="42b00-104">btm1064</span><span class="sxs-lookup"><span data-stu-id="42b00-104">btm1064</span></span>  
  
 <span data-ttu-id="42b00-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="42b00-105">**Explanation**</span></span>  
  
 <span data-ttu-id="42b00-106">以前のバージョンの BizTalk マッパーを使用して作成されたために、マップをコンパイルすることはできません。</span><span class="sxs-lookup"><span data-stu-id="42b00-106">The map cannot be compiled because it was created using a previous version of BizTalk Mapper.</span></span> <span data-ttu-id="42b00-107">コンパイルする前に、このようなマップをこのバージョンの BizTalk マッパーに移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42b00-107">You must migrate such maps to this version of BizTalk Mapper before they can be compiled.</span></span>  
  
 <span data-ttu-id="42b00-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="42b00-108">**User Action**</span></span>  
  
 <span data-ttu-id="42b00-109">現在のバージョンの BizTalk マッパーをマップを移行するには、"xml"から"btm"に関連する Microsoft BizTalk Server プロジェクトに追加するファイル拡張子を変更します。</span><span class="sxs-lookup"><span data-stu-id="42b00-109">Migrate the map to the current version of BizTalk Mapper by changing its file extension from "xml" to "btm", adding it to the relevant Microsoft BizTalk Server project.</span></span> <span data-ttu-id="42b00-110">使用して、**既存項目の追加**コマンドで使用できる、**ファイル**メニューと BizTalk のショートカット メニューの ソリューション エクスプ ローラーでプロジェクトし、ソリューション エクスプ ローラーでダブルクリックしてマップを開きます。</span><span class="sxs-lookup"><span data-stu-id="42b00-110">Use the **Add Existing Item** command available on the **File** menu and on the shortcut menu for the BizTalk project in Solution Explorer, and then open the map by double-clicking it in Solution Explorer.</span></span> <span data-ttu-id="42b00-111">このトピックに達しているため、最初の 2 つの手順を既に実行しました。</span><span class="sxs-lookup"><span data-stu-id="42b00-111">Because you have reached this topic, you have probably already performed the first two steps.</span></span> <span data-ttu-id="42b00-112">現在のバージョンの BizTalk マッパーでマップを開くだけで、マップの場で移行を実行します。</span><span class="sxs-lookup"><span data-stu-id="42b00-112">Simply opening the map in the current version of BizTalk Mapper will perform an on-the-fly migration of the map.</span></span>