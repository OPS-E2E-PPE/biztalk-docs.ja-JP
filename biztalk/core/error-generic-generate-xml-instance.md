---
title: エラー - XML インスタンスの生成ジェネリック |Microsoft ドキュメント
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
ms.openlocfilehash: c859cfc775e74ab817e66dbb8b896f51458f0301
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---generic-generate-xml-instance"></a><span data-ttu-id="34ff1-102">エラー - XML インスタンスの生成ジェネリック</span><span class="sxs-lookup"><span data-stu-id="34ff1-102">Error - Generic Generate XML Instance</span></span>
<span data-ttu-id="34ff1-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="34ff1-103">**Error Code**</span></span>  
  
 <span data-ttu-id="34ff1-104">btm1038</span><span class="sxs-lookup"><span data-stu-id="34ff1-104">btm1038</span></span>  
  
 <span data-ttu-id="34ff1-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="34ff1-105">**Explanation**</span></span>  
  
 <span data-ttu-id="34ff1-106">BizTalk マッパーで、マップの送信元スキーマの XML インスタンス メッセージ ファイルを生成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="34ff1-106">BizTalk Mapper was not able to generate an XML instance message file for the source schema of the map.</span></span> <span data-ttu-id="34ff1-107">マップに関連付けられている送信元スキーマに問題があります。</span><span class="sxs-lookup"><span data-stu-id="34ff1-107">This suggests that there is a problem with the source schema associated with the map.</span></span>  
  
 <span data-ttu-id="34ff1-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="34ff1-108">**User Action**</span></span>  
  
 <span data-ttu-id="34ff1-109">BizTalk エディターを使用して、マップに関連付けられた送信元スキーマを開き、送信元スキーマに問題があるかどうかを調査します。</span><span class="sxs-lookup"><span data-stu-id="34ff1-109">Use BizTalk Editor to open the source schema associated with the map and begin investigating whether there are problems with the source schema.</span></span> <span data-ttu-id="34ff1-110">また、**スキーマの検証**と**インスタンスの生成**ソリューション エクスプ ローラーでスキーマを右クリックしたときに使用できるコマンドは、スキーマ エラーの検出に便利です。</span><span class="sxs-lookup"><span data-stu-id="34ff1-110">Also, the **Validate Schema** and **Generate Instance** commands, available when you right-click a schema in Solution Explorer, are useful for finding schema errors.</span></span>