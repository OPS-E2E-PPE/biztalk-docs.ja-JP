---
title: "エラー - スキーマ ファイルがビルド内にありません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.edit.error.schemaFileNotInBuild
ms.assetid: 9190868d-a1ae-48bf-ac85-510086805887
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3b5d6d11bec6b9f263e2f204f004a9a162de471
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---schema-file-not-in-build"></a><span data-ttu-id="c4632-102">エラー - スキーマ ファイルがビルド内にありません。</span><span class="sxs-lookup"><span data-stu-id="c4632-102">Error - Schema File Not In Build</span></span>
<span data-ttu-id="c4632-103">**説明**</span><span class="sxs-lookup"><span data-stu-id="c4632-103">**Explanation**</span></span>  
  
 <span data-ttu-id="c4632-104">コマンドは、(**インスタンスの検証**、**インスタンスの生成**、または**スキーマの検証**) を実行できませんでしたので、**ビルド アクション**スキーマ ファイルのプロパティに設定されて**None**、このスキーマがこれらのコマンドに参加していることを妨げています。</span><span class="sxs-lookup"><span data-stu-id="c4632-104">The command (**Validate Instance**, **Generate Instance**, or **Validate Schema**) could not be performed because the **Build Action** property of the schema file is set to **None**, preventing this schema from participating in these commands.</span></span>  
  
 <span data-ttu-id="c4632-105">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="c4632-105">**User Action**</span></span>  
  
 <span data-ttu-id="c4632-106">Microsoft では、関連するスキーマ ファイルを選択して[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーで、し、[プロパティ] ウィンドウで次のように変更します。、**ビルド アクション**プロパティを、**コンパイル**です。</span><span class="sxs-lookup"><span data-stu-id="c4632-106">Select the relevant schema file in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Solution Explorer, and then in the Properties window, change the **Build Action** property to a **Compile**.</span></span> <span data-ttu-id="c4632-107">しようとし、**インスタンスの検証**、**インスタンスの生成**、または**スキーマの検証**コマンドを再です。</span><span class="sxs-lookup"><span data-stu-id="c4632-107">Then attempt the **Validate Instance**, **Generate Instance**, or **Validate Schema** command again.</span></span>