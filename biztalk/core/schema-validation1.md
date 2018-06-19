---
title: スキーマ Validation1 |Microsoft ドキュメント
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
ms.openlocfilehash: 20224a77530139a97647d91b0b46f9384d6c2753
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268794"
---
# <a name="schema-validation"></a><span data-ttu-id="7fd99-102">スキーマの検証</span><span class="sxs-lookup"><span data-stu-id="7fd99-102">Schema Validation</span></span>
<span data-ttu-id="7fd99-103">BizTalk エディター拡張機能を提供する場合、 **ISchemaValidator**オブジェクト、フレームワークが呼び出す**ISchemaValidator.ValidateSchema** 、ユーザーが呼び出す場合、 **スキーマの検証**コマンド、またはユーザーが、スキーマを含む BizTalk プロジェクトを構築するときに、コンパイル時にします。</span><span class="sxs-lookup"><span data-stu-id="7fd99-103">If a BizTalk Editor extension provides an **ISchemaValidator** object, the framework will invoke **ISchemaValidator.ValidateSchema** when the user invokes the **Validate Schema** command, or during compilation when the user builds the BizTalk project containing the schema.</span></span> <span data-ttu-id="7fd99-104">拡張機能は通常、カスタム プロパティを検証しの配列としてエラー メッセージを返すことができます**IValidationInfo**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="7fd99-104">The extension usually validates the custom properties, and can return error messages as an array of **IValidationInfo** objects.</span></span> <span data-ttu-id="7fd99-105">エラー メッセージは、BizTalk エディターのコンパイラから返されたエラーと共に、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のタスク一覧ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7fd99-105">The error messages are displayed in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Task List window, along with errors returned from BizTalk Editor compiler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fd99-106">参照</span><span class="sxs-lookup"><span data-stu-id="7fd99-106">See Also</span></span>  
 [<span data-ttu-id="7fd99-107">BizTalk エディターの拡張</span><span class="sxs-lookup"><span data-stu-id="7fd99-107">Extending BizTalk Editor</span></span>](../core/extending-biztalk-editor.md)