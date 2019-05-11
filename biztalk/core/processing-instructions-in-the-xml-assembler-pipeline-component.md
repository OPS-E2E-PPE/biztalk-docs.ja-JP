---
title: 手順については、XML アセンブラー パイプライン コンポーネントでの処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XMLNorm.ProcessingInstructionOption property
- envelopes, processing instructions
- XML Assembler [pipeline component], processing instructions
- Processing instruction scope property
- XMLNorm.ProcessingInstruction property
- envelopes, XML Assembler [pipeline component]
- pipeline components, XML Assembler
ms.assetid: d8ea453e-3b20-417d-bf25-9d424b0150fd
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3366ed738020ebf90fadfb104f860f0cdb952168
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396988"
---
# <a name="processing-instructions-in-the-xml-assembler-pipeline-component"></a>手順については、XML アセンブラー パイプライン コンポーネントでの処理
処理命令は、XML ドキュメントを処理するアプリケーションに情報を提供します。 このような情報は、ドキュメントを処理する方法に関する指示を含めることができ、それを表示する方法。  
  
 処理命令は、XML ドキュメントに追加、**処理命令の追加**プロパティ (または同等の**XMLNorm.ProcessingInstructionOption**メッセージ コンテキストのプロパティ)。 処理命令テキストを指定した、**処理命令テキストの追加**プロパティ (または同等の**XMLNorm.ProcessingInstruction**メッセージ コンテキストのプロパティ)。  
  
 **処理命令の追加**プロパティ (または**XMLNorm.ProcessingInstructionOption**プロパティ) は、次の表で説明されている 3 つの値。  
  
|値|値|説明|  
|-----------|-----------|-----------------|  
|追加|0|XML アセンブラーからの新しい処理命令は、ドキュメントの先頭にある処理命令に付加されます。|  
|新規作成します。|1|XML アセンブラーからの新しい処理命令は、ドキュメントの先頭にある既存の処理命令を上書きします。|  
|Ignore|2|ドキュメントの先頭にある処理命令が削除されます。|  
  
 処理命令 (またはメッセージ コンテキストのプロパティ) のメッセージ コンテキストで指定されたペアは、パイプライン デザイナーで指定されるプロパティ ペアよりも優先されます。 たとえば場合、 **XMLNorm.ProcessingInstructionOption**として指定されて**新規作成**(1) と**XMLNorm.ProcessingInstruction**が指定されていない空の処理命令は、既存の処理命令が置き換えられます。  
  
 別の例として場合**XMLNorm.ProcessingInstruction**が指定されて、 **XMLNorm.ProcessingInstructionOption**は、メッセージ コンテキストからプロパティのいずれもが使用されます。 この場合、パイプライン デザイナーからの処理命令が使用されます。  
  
 既定では、**処理命令の追加**に設定されている**Append**、および**処理命令テキストの追加**が空です。  
  
## <a name="processing-properties-and-envelopes"></a>プロパティおよびエンベロープの処理  
 処理命令はエンベロープ用保持されず、ため、処理命令を持つ最も外側にあるエンベロープのみにフラット ファイル アセンブラー設定の次の組み合わせが発生します。  
  
- **処理命令スコープ**プロパティが「エンベロープ」に設定  
  
- **処理命令の追加**プロパティを「追加」「に設定  
  
  アセンブラーので指定される処理命令はエンベロープを使用して、**追加処理命令テキストの**プロパティ。  
  
  いずれか、外部または内部エンベロープを着信メッセージで指定されている既存の処理手順については出力メッセージに存在できません。  
  
## <a name="see-also"></a>参照  
 [XML アセンブラー パイプライン コンポーネント](../core/xml-assembler-pipeline-component.md)   
 [XML アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-assembler-pipeline-component.md)   
 [Pipelines-AssemblerDisassembler (BizTalk Server サンプル フォルダー)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)