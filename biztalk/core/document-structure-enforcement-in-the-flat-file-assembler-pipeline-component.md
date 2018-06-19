---
title: フラット ファイル アセンブラー パイプライン コンポーネントにおける構造の強化を文書化 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, Flat File Assembler
- Flat File Assembler [pipeline component], document structure
ms.assetid: 3ac75706-1d4d-443a-a4bf-af8f79a6a092
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb35c7b31eda69d03d532d13d975d618d4f36f76
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238706"
---
# <a name="document-structure-enforcement-in-the-flat-file-assembler-pipeline-component"></a><span data-ttu-id="c3cd3-102">フラット ファイル アセンブラー パイプライン コンポーネントにおけるドキュメント構造の強化</span><span class="sxs-lookup"><span data-stu-id="c3cd3-102">Document Structure Enforcement in the Flat File Assembler Pipeline Component</span></span>
<span data-ttu-id="c3cd3-103">フラット ファイル アセンブラーでドキュメントまたはエンベロープ スキーマが明示的に参照されている場合、参照されたスキーマに対応するメッセージ タイプのドキュメントだけが処理されます。</span><span class="sxs-lookup"><span data-stu-id="c3cd3-103">If document or envelope schemas are explicitly referenced in the Flat File Assembler, the Flat File Assembler ensures that only documents with the message type corresponding to referenced schemas are processed.</span></span> <span data-ttu-id="c3cd3-104">その他すべてのドキュメントは、該当するスキーマが配置されていたとしても、処理から除外されます。</span><span class="sxs-lookup"><span data-stu-id="c3cd3-104">All the other documents are not processed even though a schema may be deployed for them.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c3cd3-105">エンベロープ スキーマは最初のメッセージからのみ取得されます。</span><span class="sxs-lookup"><span data-stu-id="c3cd3-105">The envelope schema is taken from the first message only.</span></span> <span data-ttu-id="c3cd3-106">エンベロープのプロパティは常に最初のメッセージから取得されます。</span><span class="sxs-lookup"><span data-stu-id="c3cd3-106">The properties for the envelope are always taken from the first message.</span></span>