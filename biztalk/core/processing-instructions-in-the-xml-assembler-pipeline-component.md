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
ms.openlocfilehash: df3b56a3703e56dd4b3f474b4846999bae9858f0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016108"
---
# <a name="processing-instructions-in-the-xml-assembler-pipeline-component"></a>手順については、XML アセンブラー パイプライン コンポーネントでの処理
処理命令は、XML ドキュメントを処理するアプリケーションに対する情報を提供します。 この情報には、ドキュメントの処理方法や表示方法などの命令が含まれます。  
  
 処理命令は、XML ドキュメントに追加、**処理命令の追加**プロパティ (または同等の**XMLNorm.ProcessingInstructionOption**メッセージ コンテキストのプロパティ)。 処理命令テキストを指定した、**処理命令テキストの追加**プロパティ (または同等の**XMLNorm.ProcessingInstruction**メッセージ コンテキストのプロパティ)。  
  
 **処理命令の追加**プロパティ (または**XMLNorm.ProcessingInstructionOption**プロパティ) は、次の表で説明されている 3 つの値。  
  
|値|値|説明|  
|-----------|-----------|-----------------|  
|追加|0|XML アセンブラーからの新しい処理命令は、ドキュメントの最初の処理命令に追加されます。|  
|新規作成します。|1|XML アセンブラーからの新しい処理命令は、ドキュメントの最初の既存の処理命令を上書きします。|  
|Ignore|2|ドキュメントの最初の処理命令は、削除されます。|  
  
 メッセージ コンテキストで指定される処理命令 (またはメッセージ コンテキスト プロパティ) のペアは、パイプライン デザイナーで指定されるプロパティ ペアよりも優先されます。 たとえば場合、 **XMLNorm.ProcessingInstructionOption**として指定されて**新規作成**(1) と**XMLNorm.ProcessingInstruction**が指定されていない空の処理命令は、既存の処理命令が置き換えられます。  
  
 別の例として場合**XMLNorm.ProcessingInstruction**が指定されて、 **XMLNorm.ProcessingInstructionOption**は、メッセージ コンテキストからプロパティのいずれもが使用されます。 この場合、パイプライン デザイナーからの処理命令が使用されます。  
  
 既定では、**処理命令の追加**に設定されている**Append**、および**処理命令テキストの追加**が空です。  
  
## <a name="processing-properties-and-envelopes"></a>プロパティおよびエンベロープの処理  
 処理命令はエンベロープ用に維持されないので、フラット ファイル アセンブラー設定の次の組み合わせは、処理命令を持つ最も外側にあるエンベロープのみに適用されます。  
  
- **処理命令スコープ**プロパティが「エンベロープ」に設定  
  
- **処理命令の追加**プロパティを「追加」「に設定  
  
  アセンブラーので指定される処理命令はエンベロープを使用して、**追加処理命令テキストの**プロパティ。  
  
  いずれか、外部または内部エンベロープを着信メッセージで指定されている既存の処理手順については出力メッセージに存在できません。  
  
## <a name="see-also"></a>参照  
 [XML アセンブラー パイプライン コンポーネント](../core/xml-assembler-pipeline-component.md)   
 [XML アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-assembler-pipeline-component.md)   
 [Pipelines-AssemblerDisassembler (BizTalk Server サンプル フォルダー)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)