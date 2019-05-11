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
# <a name="schema-validation"></a>スキーマの検証
BizTalk エディター拡張機能を提供する場合、 **ISchemaValidator**オブジェクト、フレームワークが呼び出す**ISchemaValidator.ValidateSchema** 、ユーザーを呼び出したときに、 **スキーマの検証**コマンドから、または、ユーザーは、スキーマを含む BizTalk プロジェクトをビルドするとき、コンパイル時にします。 拡張機能は、通常はカスタムのプロパティを検証しの配列としてエラー メッセージを返すことができます**IValidationInfo**オブジェクト。 エラー メッセージが表示されます、 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk エディターのコンパイラから返されたエラーと共に、タスク一覧 ウィンドウ。  
  
## <a name="see-also"></a>参照  
 [BizTalk エディターの拡張](../core/extending-biztalk-editor.md)