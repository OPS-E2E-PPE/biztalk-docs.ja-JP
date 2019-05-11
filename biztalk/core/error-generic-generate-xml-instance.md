---
title: エラー - XML インスタンスを生成するジェネリック |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.genericGenerateXmlInstance
ms.assetid: f2b42589-fd44-45d6-86e6-c2502820beee
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79a24f4143e2619809071d3b414c9a122c8121b2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348252"
---
# <a name="error---generic-generate-xml-instance"></a><span data-ttu-id="76594-102">エラー - XML インスタンスを生成するジェネリック</span><span class="sxs-lookup"><span data-stu-id="76594-102">Error - Generic Generate XML Instance</span></span>
<span data-ttu-id="76594-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="76594-103">**Error Code**</span></span>  
  
 <span data-ttu-id="76594-104">btm1038</span><span class="sxs-lookup"><span data-stu-id="76594-104">btm1038</span></span>  
  
 <span data-ttu-id="76594-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="76594-105">**Explanation**</span></span>  
  
 <span data-ttu-id="76594-106">BizTalk マッパーは、マップの送信元スキーマの XML インスタンス メッセージ ファイルを生成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="76594-106">BizTalk Mapper was not able to generate an XML instance message file for the source schema of the map.</span></span> <span data-ttu-id="76594-107">これは、マップに関連付けられている送信元スキーマに問題があることを示しています。</span><span class="sxs-lookup"><span data-stu-id="76594-107">This suggests that there is a problem with the source schema associated with the map.</span></span>  
  
 <span data-ttu-id="76594-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="76594-108">**User Action**</span></span>  
  
 <span data-ttu-id="76594-109">BizTalk エディターを使用して、マップに関連付けられている送信元スキーマを開き、送信元スキーマの問題があるかどうかの調査を開始します。</span><span class="sxs-lookup"><span data-stu-id="76594-109">Use BizTalk Editor to open the source schema associated with the map and begin investigating whether there are problems with the source schema.</span></span> <span data-ttu-id="76594-110">また、**スキーマの検証**と**インスタンスの生成**コマンド、使用できるは、ソリューション エクスプ ローラーでスキーマを右クリックしたときにスキーマ エラーの検出に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="76594-110">Also, the **Validate Schema** and **Generate Instance** commands, available when you right-click a schema in Solution Explorer, are useful for finding schema errors.</span></span>