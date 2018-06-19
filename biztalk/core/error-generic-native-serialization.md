---
title: エラー - ネイティブ シリアライズの一般的な |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.genericNativeSerialize
ms.assetid: 3728727d-7d99-432d-844e-c956cc4635e4
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d2eacfae17d72dbb17786a1d924cfdf14be20ee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241002"
---
# <a name="error---generic-native-serialization"></a><span data-ttu-id="3b80b-102">エラー - ネイティブ シリアライズの一般的です</span><span class="sxs-lookup"><span data-stu-id="3b80b-102">Error - Generic Native Serialization</span></span>
<span data-ttu-id="3b80b-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="3b80b-103">**Error Code**</span></span>  
  
 <span data-ttu-id="3b80b-104">btm1049</span><span class="sxs-lookup"><span data-stu-id="3b80b-104">btm1049</span></span>  
  
 <span data-ttu-id="3b80b-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="3b80b-105">**Explanation**</span></span>  
  
 <span data-ttu-id="3b80b-106">マップで指定された変換によって生成された XML 出力インスタンス メッセージは、特定できないエラーが原因で、送信先スキーマで指定されたネイティブ形式に変換できませんでした。</span><span class="sxs-lookup"><span data-stu-id="3b80b-106">The XML output instance message produced by the transformation specified by the map could not be converted to the native format specified by the destination schema due to an unspecified error.</span></span>  
  
 <span data-ttu-id="3b80b-107">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="3b80b-107">**User Action**</span></span>  
  
 <span data-ttu-id="3b80b-108">BizTalk エディターで、送信先スキーマを開いて使用して、**スキーマの検証**、**インスタンスの検証**と**インスタンスの生成** コマンドを右クリックしたときに使用します。ソリューション エクスプ ローラーで、問題を特定するスキーマです。</span><span class="sxs-lookup"><span data-stu-id="3b80b-108">Open the destination schema in BizTalk Editor and use the **Validate Schema**, **Validate Instance**, and **Generate Instance** commands, available when you right-click a schema in Solution Explorer, to isolate the problem.</span></span>