---
title: スキーマ Validation1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 599f1bbb-2af5-4278-8b0f-0e5a6517e8e3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35156317c55aa31a0947f244031e1e2b3d2516f6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396878"
---
# <a name="schema-validation"></a><span data-ttu-id="db6b5-102">スキーマの検証</span><span class="sxs-lookup"><span data-stu-id="db6b5-102">Schema Validation</span></span>
<span data-ttu-id="db6b5-103">BizTalk エディター拡張機能を提供する場合、 **ISchemaValidator**オブジェクト、フレームワークが呼び出す**ISchemaValidator.ValidateSchema** 、ユーザーを呼び出したときに、 **スキーマの検証**コマンドから、または、ユーザーは、スキーマを含む BizTalk プロジェクトをビルドするとき、コンパイル時にします。</span><span class="sxs-lookup"><span data-stu-id="db6b5-103">If a BizTalk Editor extension provides an **ISchemaValidator** object, the framework will invoke **ISchemaValidator.ValidateSchema** when the user invokes the **Validate Schema** command, or during compilation when the user builds the BizTalk project containing the schema.</span></span> <span data-ttu-id="db6b5-104">拡張機能は、通常はカスタムのプロパティを検証しの配列としてエラー メッセージを返すことができます**IValidationInfo**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="db6b5-104">The extension usually validates the custom properties, and can return error messages as an array of **IValidationInfo** objects.</span></span> <span data-ttu-id="db6b5-105">エラー メッセージが表示されます、 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk エディターのコンパイラから返されたエラーと共に、タスク一覧 ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="db6b5-105">The error messages are displayed in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Task List window, along with errors returned from BizTalk Editor compiler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db6b5-106">参照</span><span class="sxs-lookup"><span data-stu-id="db6b5-106">See Also</span></span>  
 [<span data-ttu-id="db6b5-107">BizTalk エディターの拡張</span><span class="sxs-lookup"><span data-stu-id="db6b5-107">Extending BizTalk Editor</span></span>](../core/extending-biztalk-editor.md)