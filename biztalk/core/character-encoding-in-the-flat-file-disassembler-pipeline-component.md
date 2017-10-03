---
title: "フラット ファイル逆アセンブラー パイプライン コンポーネントにおける文字エンコーディング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IBaseMessagePart.Charset property
- XMLNorm.SourceCharset property
- pipeline components, Flat File Disassembler
- Flat File Disassembler [pipeline component], character encoding
ms.assetid: 0dbe24fb-c431-4edf-8aa9-4c040d6a7b32
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 839a3377f27417757e394c946fe96acc83752355
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="character-encoding-in-the-flat-file-disassembler-pipeline-component"></a>フラット ファイル逆アセンブラー パイプライン コンポーネントでの文字エン コード
フラット ファイル逆アセンブラーでは、次のアルゴリズムに基づいて、入力メッセージを処理するためのエンコードに使用する文字セットを決定します。  
  
1.  バイト順マークがデータ内に存在する場合、これによってエンコード情報が決定されます。 このエンコード情報は、逆アセンブラーでは保持されません (つまり、これは保存されません、 **XMLNorm.SourceCharset**プロパティ)。  
  
2.  それ以外の場合、 **IBaseMessagePart.Charset**プロパティが設定されてがあります指定されたエンコーディングを使用します。  
  
3.  IBaseMessagePart.Charset プロパティも設定されていない場合、ヘッダーまたはドキュメント スキーマにコードページ情報が含まれていれば、これが使用されます。  
  
4.  上記のいずれにも該当しない場合は、UTF-8 エンコードが使用されます。  
  
 前述の 2、3、および 4、逆アセンブラー保存エンコード情報、メッセージ コンテキスト内で、 **XMLNorm.SourceCharset**プロパティです。  
  
## <a name="see-also"></a>参照  
 [フラット ファイル逆アセンブラー パイプライン コンポーネント](../core/flat-file-disassembler-pipeline-component.md)   
 [フラット ファイル逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)   
 [パイプライン AssemblerDisassembler (BizTalk Server Samples フォルダ)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)