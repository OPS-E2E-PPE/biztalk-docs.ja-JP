---
title: XML アセンブラーで認識されないメッセージのパイプライン コンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XMLNorm.AllowUnrecognizedMessage property
- XML Assembler [pipeline component], unrecognized messages
- pipeline components, XML Assembler
ms.assetid: dd98512a-33a4-4b2e-977e-1b3a30747c6a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de9f072fc09126d56397725f93505afaca46adf4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974819"
---
# <a name="unrecognized-messages-in-the-xml-assembler-pipeline-component"></a>XML アセンブラー パイプライン コンポーネントで認識されないメッセージ
XML アセンブラー コンポーネントは、メッセージが次に示す事項に該当する場合、"認識されない" メッセージとして処理します。  
  
-   ボディ部がない。  
  
-   ボディ部が空である。  
  
-   ボディ部にデータがない。  
  
-   展開されている関連スキーマがない。  
  
> [!NOTE]
>  XML 以外のメッセージは、常に "認識されない" メッセージとして処理されます。  
  
 XML アセンブラーが認識されないメッセージを処理する方法がによって制御される、 **XMLNorm.AllowUnrecognizedMessage**メッセージ コンテキスト プロパティ。  
  
 ときに**XMLNorm.AllowUnrecognizedMessage**に設定されている**True**、XML アセンブラーが XML ドキュメントを次のように処理します。  
  
- ボディ部のないメッセージ、ボディ部が空のメッセージ、またはボディ部にデータがないメッセージは、アセンブラーを通じて変更せずに渡されます。  
  
- 展開されたスキーマがドキュメントに関連付けられていない場合、アセンブラーを通じて変更せずに渡されます。  
  
- スキーマがコンポーネントのプロパティで明示的に参照されているか、スキーマ解決プロセスで見つかったかどうかに関係なく、展開されたスキーマがドキュメントに関連付けられている場合は、アセンブラーによって処理されます。  
  
  場合**XMLNorm.AllowUnrecognizedMessage**に設定されている**False**、XML アセンブラーが XML ドキュメントを次のように処理します。  
  
- ボディ部のないメッセージ、ボディ部が空のメッセージ、またはボディ部にデータがないメッセージは、処理されません。 エラーが報告され、メッセージが中断されます。  
  
- 展開されたスキーマがメッセージに関連付けられていない場合、メッセージは処理されません。 エラーが報告され、メッセージが中断されます。  
  
- スキーマがコンポーネントのプロパティで明示的に参照されているか、スキーマ解決プロセスで見つかったかどうかに関係なく、展開されたスキーマがドキュメントに関連付けられている場合は、アセンブラーによって処理されます。  
  
- 既定では、XML アセンブラー コンポーネントにより認識されないメッセージ (つまり、 **XMLNorm.AllowUnrecognizedMessages**と見なされます**False**メッセージ コンテキストに設定されていない場合)。  
  
## <a name="see-also"></a>参照  
 [XML アセンブラー パイプライン コンポーネント](../core/xml-assembler-pipeline-component.md)   
 [XML アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-assembler-pipeline-component.md)   
 [Pipelines-AssemblerDisassembler (BizTalk Server サンプル フォルダー)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)