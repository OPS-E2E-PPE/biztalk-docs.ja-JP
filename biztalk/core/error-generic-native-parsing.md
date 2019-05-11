---
title: エラー - ネイティブ解析の一般的な |Microsoft Docs
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
ms.openlocfilehash: eb7b46fb6b04486c8c80a286c86a4f9cb3c84dbb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348242"
---
# <a name="error---generic-native-parsing"></a><span data-ttu-id="2c2e9-102">エラー - ネイティブ解析のジェネリック</span><span class="sxs-lookup"><span data-stu-id="2c2e9-102">Error - Generic Native Parsing</span></span>
<span data-ttu-id="2c2e9-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="2c2e9-103">**Error Code**</span></span>  
  
 <span data-ttu-id="2c2e9-104">btm1042</span><span class="sxs-lookup"><span data-stu-id="2c2e9-104">btm1042</span></span>  
  
 <span data-ttu-id="2c2e9-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="2c2e9-105">**Explanation**</span></span>  
  
 <span data-ttu-id="2c2e9-106">マップのテスト操作に指定されたネイティブ入力インスタンス メッセージ ファイルは、解析できませんでしたし、汎用の致命的な解析エラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="2c2e9-106">The native input instance message file specified for the Test Map operation could not be parsed, and generated a generic fatal parsing error.</span></span>  
  
 <span data-ttu-id="2c2e9-107">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="2c2e9-107">**User Action**</span></span>  
  
 <span data-ttu-id="2c2e9-108">必要に応じて、適切な送信元スキーマは、マップまたは指定したファイルまたはその両方でネイティブの入力インスタンス メッセージに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="2c2e9-108">As appropriate, correct either the source schema associated with the map or the native input instance message in the specified file, or both.</span></span> <span data-ttu-id="2c2e9-109">BizTalk エディターで問題を特定する作業を検討してください。</span><span class="sxs-lookup"><span data-stu-id="2c2e9-109">Consider working within BizTalk Editor to isolate the problem.</span></span> <span data-ttu-id="2c2e9-110">**スキーマの検証**と**インスタンスの生成**コマンド、使用できるは、ソリューション エクスプ ローラーでスキーマを右クリックしたときにスキーマ エラーの検出に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2c2e9-110">The **Validate Schema** and **Generate Instance** commands, available when you right-click a schema in Solution Explorer, are useful for finding schema errors.</span></span>