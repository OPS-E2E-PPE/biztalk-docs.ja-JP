---
title: XML アセンブラー パイプライン コンポーネントで処理命令 |Microsoft ドキュメント
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
ms.openlocfilehash: 85ac6045084c0aea672b0c1e9d6dfb1b4a742d55
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22265154"
---
# <a name="processing-instructions-in-the-xml-assembler-pipeline-component"></a>XML アセンブラー パイプライン コンポーネントで処理命令
処理命令は、XML ドキュメントを処理するアプリケーションに対する情報を提供します。 この情報には、ドキュメントの処理方法や表示方法などの命令が含まれます。  
  
 処理命令は、XML ドキュメントに追加、**処理命令の追加**プロパティ (または同等の**XMLNorm.ProcessingInstructionOption**メッセージ コンテキストのプロパティ)。 処理命令テキストを指定した、**処理命令テキストの追加**プロパティ (または同等の**XMLNorm.ProcessingInstruction**メッセージ コンテキストのプロパティ)。  
  
 **処理命令の追加**プロパティ (または**XMLNorm.ProcessingInstructionOption**プロパティ) は、次の表で説明される 3 つの値。  
  
|値|値|Description|  
|-----------|-----------|-----------------|  
|追加|0|XML アセンブラーからの新しい処理命令は、ドキュメントの最初の処理命令に追加されます。|  
|[新規作成]|1|XML アセンブラーからの新しい処理命令は、ドキュメントの最初の既存の処理命令を上書きします。|  
|Ignore|2|ドキュメントの最初の処理命令は、削除されます。|  
  
 メッセージ コンテキストで指定される処理命令 (またはメッセージ コンテキスト プロパティ) のペアは、パイプライン デザイナーで指定されるプロパティ ペアよりも優先されます。 たとえば場合、 **XMLNorm.ProcessingInstructionOption**として指定された**新規作成**(1) と**XMLNorm.ProcessingInstruction**が指定されていない空の処理命令は、既存の処理命令が置き換えられます。  
  
 別の例として場合**XMLNorm.ProcessingInstruction**が指定されているが、 **XMLNorm.ProcessingInstructionOption**は、メッセージ コンテキストからプロパティのいずれも使用します。 この場合、パイプライン デザイナーからの処理命令が使用されます。  
  
 既定では、**処理命令の追加**に設定されている**Append**、および**処理命令テキストの追加**が空です。  
  
## <a name="processing-properties-and-envelopes"></a>プロパティおよびエンベロープの処理  
 処理命令はエンベロープ用に維持されないので、フラット ファイル アセンブラー設定の次の組み合わせは、処理命令を持つ最も外側にあるエンベロープのみに適用されます。  
  
-   **処理命令スコープ**プロパティ「封筒」に設定します。  
  
-   **処理命令の追加**プロパティを「追加」に設定  
  
 エンベロープは、アセンブラーで指定される処理命令を使用して**追加処理命令テキストの**プロパティです。  
  
 いずれか、外部または内部エンベロープを受信メッセージで指定されている、既存の処理命令は出力メッセージに存在できません。  
  
## <a name="see-also"></a>参照  
 [XML アセンブラー パイプライン コンポーネント](../core/xml-assembler-pipeline-component.md)   
 [XML アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-assembler-pipeline-component.md)   
 [パイプライン AssemblerDisassembler (BizTalk Server Samples フォルダ)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)