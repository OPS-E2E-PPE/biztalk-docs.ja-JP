---
title: "認識されないメッセージを XML アセンブラー パイプライン コンポーネント |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XMLNorm.AllowUnrecognizedMessage property
- XML Assembler [pipeline component], unrecognized messages
- pipeline components, XML Assembler
ms.assetid: dd98512a-33a4-4b2e-977e-1b3a30747c6a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6766554374413c3d1b6a3ce385f24d4046521c91
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="unrecognized-messages-in-the-xml-assembler-pipeline-component"></a>XML アセンブラー パイプライン コンポーネントで認識されないメッセージ
XML アセンブラー コンポーネントは、メッセージが次に示す事項に該当する場合、"認識されない" メッセージとして処理します。  
  
-   ボディ部がない。  
  
-   ボディ部が空である。  
  
-   ボディ部にデータがない。  
  
-   展開されている関連スキーマがない。  
  
> [!NOTE]
>  XML 以外のメッセージは、常に "認識されない" メッセージとして処理されます。  
  
 によって、XML アセンブラーが認識されないメッセージを処理する方法を制御、 **XMLNorm.AllowUnrecognizedMessage**メッセージ コンテキスト プロパティです。  
  
 ときに**XMLNorm.AllowUnrecognizedMessage**に設定されている**True**、XML アセンブラーが XML ドキュメントを次のように処理します。  
  
-   ボディ部のないメッセージ、ボディ部が空のメッセージ、またはボディ部にデータがないメッセージは、アセンブラーを通じて変更せずに渡されます。  
  
-   展開されたスキーマがドキュメントに関連付けられていない場合、アセンブラーを通じて変更せずに渡されます。  
  
-   スキーマがコンポーネントのプロパティで明示的に参照されているか、スキーマ解決プロセスで見つかったかどうかに関係なく、展開されたスキーマがドキュメントに関連付けられている場合は、アセンブラーによって処理されます。  
  
 場合**XMLNorm.AllowUnrecognizedMessage**に設定されている**False**、XML アセンブラーが XML ドキュメントを次のように処理します。  
  
-   ボディ部のないメッセージ、ボディ部が空のメッセージ、またはボディ部にデータがないメッセージは、処理されません。 エラーが報告され、メッセージが中断されます。  
  
-   展開されたスキーマがメッセージに関連付けられていない場合、メッセージは処理されません。 エラーが報告され、メッセージが中断されます。  
  
-   スキーマがコンポーネントのプロパティで明示的に参照されているか、スキーマ解決プロセスで見つかったかどうかに関係なく、展開されたスキーマがドキュメントに関連付けられている場合は、アセンブラーによって処理されます。  
  
-   既定では、XML アセンブラー コンポーネントはメッセージを許可しません認識されていない (つまり、 **XMLNorm.AllowUnrecognizedMessages**と見なされます**False**メッセージ コンテキストに設定されていない場合)。  
  
## <a name="see-also"></a>参照  
 [XML アセンブラー パイプライン コンポーネント](../core/xml-assembler-pipeline-component.md)   
 [XML アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-assembler-pipeline-component.md)   
 [パイプライン AssemblerDisassembler (BizTalk Server Samples フォルダ)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)