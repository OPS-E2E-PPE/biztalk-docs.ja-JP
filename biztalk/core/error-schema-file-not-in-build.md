---
title: エラー - スキーマ ファイルがビルド内にありません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.schemaFileNotInBuild
ms.assetid: 9190868d-a1ae-48bf-ac85-510086805887
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48edbf86714ec100ba69833a57786205139247f2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388423"
---
# <a name="error---schema-file-not-in-build"></a><span data-ttu-id="b852f-102">エラー - スキーマ ファイルがビルドに存在しません</span><span class="sxs-lookup"><span data-stu-id="b852f-102">Error - Schema File Not In Build</span></span>
<span data-ttu-id="b852f-103">**説明**</span><span class="sxs-lookup"><span data-stu-id="b852f-103">**Explanation**</span></span>  
  
 <span data-ttu-id="b852f-104">コマンド (**インスタンスの検証**、**インスタンスの生成**、または**スキーマの検証**) ためを実行できませんでした、**ビルド アクション**スキーマ ファイルのプロパティに設定されて**None**、このスキーマがこれらのコマンドに参加していることを防止します。</span><span class="sxs-lookup"><span data-stu-id="b852f-104">The command (**Validate Instance**, **Generate Instance**, or **Validate Schema**) could not be performed because the **Build Action** property of the schema file is set to **None**, preventing this schema from participating in these commands.</span></span>  
  
 <span data-ttu-id="b852f-105">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="b852f-105">**User Action**</span></span>  
  
 <span data-ttu-id="b852f-106">Microsoft では、関連するスキーマ ファイルを選択します。[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーで、し、[プロパティ] ウィンドウで次のように変更します。、**ビルド アクション**プロパティを、**コンパイル**します。</span><span class="sxs-lookup"><span data-stu-id="b852f-106">Select the relevant schema file in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Solution Explorer, and then in the Properties window, change the **Build Action** property to a **Compile**.</span></span> <span data-ttu-id="b852f-107">しようとし、**インスタンスの検証**、**インスタンスの生成**、または**スキーマの検証**コマンドを再実行します。</span><span class="sxs-lookup"><span data-stu-id="b852f-107">Then attempt the **Validate Instance**, **Generate Instance**, or **Validate Schema** command again.</span></span>