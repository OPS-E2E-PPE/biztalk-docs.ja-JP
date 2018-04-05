---
title: エラー - ネイティブ解析の一般的な |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.genericNativeParsing
ms.assetid: a28a4c0f-b69b-448b-b305-3b06b4f061e4
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 383c3198af290552715d51812f22c82760cb445f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---generic-native-parsing"></a><span data-ttu-id="97c8e-102">エラー - ネイティブ解析のジェネリック</span><span class="sxs-lookup"><span data-stu-id="97c8e-102">Error - Generic Native Parsing</span></span>
<span data-ttu-id="97c8e-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="97c8e-103">**Error Code**</span></span>  
  
 <span data-ttu-id="97c8e-104">btm1042</span><span class="sxs-lookup"><span data-stu-id="97c8e-104">btm1042</span></span>  
  
 <span data-ttu-id="97c8e-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="97c8e-105">**Explanation**</span></span>  
  
 <span data-ttu-id="97c8e-106">マップのテスト用に指定されたネイティブの入力インスタンス メッセージ ファイルを解析できませんでした。その結果、一般的で致命的な解析エラーが生成されました。</span><span class="sxs-lookup"><span data-stu-id="97c8e-106">The native input instance message file specified for the Test Map operation could not be parsed, and generated a generic fatal parsing error.</span></span>  
  
 <span data-ttu-id="97c8e-107">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="97c8e-107">**User Action**</span></span>  
  
 <span data-ttu-id="97c8e-108">適宜、マップに関連付けられている送信元スキーマか、指定されているファイルのネイティブな入力インスタンス メッセージ、またはその両方を修正してください。</span><span class="sxs-lookup"><span data-stu-id="97c8e-108">As appropriate, correct either the source schema associated with the map or the native input instance message in the specified file, or both.</span></span> <span data-ttu-id="97c8e-109">問題の箇所を特定するために BizTalk エディターで作業することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="97c8e-109">Consider working within BizTalk Editor to isolate the problem.</span></span> <span data-ttu-id="97c8e-110">**スキーマの検証**と**インスタンスの生成**ソリューション エクスプ ローラーでスキーマを右クリックしたときに使用できるコマンドは、スキーマ エラーの検出に便利です。</span><span class="sxs-lookup"><span data-stu-id="97c8e-110">The **Validate Schema** and **Generate Instance** commands, available when you right-click a schema in Solution Explorer, are useful for finding schema errors.</span></span>