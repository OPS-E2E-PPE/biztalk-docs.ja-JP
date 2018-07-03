---
title: フラット ファイル逆アセンブラー パイプライン コンポーネントにおける文字エンコーディング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IBaseMessagePart.Charset property
- XMLNorm.SourceCharset property
- pipeline components, Flat File Disassembler
- Flat File Disassembler [pipeline component], character encoding
ms.assetid: 0dbe24fb-c431-4edf-8aa9-4c040d6a7b32
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2a7ef27ec23fb7470aff74df2915150f892e07a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988811"
---
# <a name="character-encoding-in-the-flat-file-disassembler-pipeline-component"></a>フラット ファイル逆アセンブラー パイプライン コンポーネントでの文字エン コード
フラット ファイル逆アセンブラーでは、次のアルゴリズムに基づいて、入力メッセージを処理するためのエンコードに使用する文字セットを決定します。  
  
1. バイト順マークがデータ内に存在する場合、これによってエンコード情報が決定されます。 このエンコード情報は、逆アセンブラーでは保持されません (つまり、これは保存されません、 **XMLNorm.SourceCharset**プロパティ)。  
  
2. の場合、 **IBaseMessagePart.Charset**プロパティが設定されて、が指定されてエンコードが使用されます。  
  
3. IBaseMessagePart.Charset プロパティも設定されていない場合、ヘッダーまたはドキュメント スキーマにコードページ情報が含まれていれば、これが使用されます。  
  
4. 上記のいずれにも該当しない場合は、UTF-8 エンコードが使用されます。  
  
   逆アセンブラーがでメッセージ コンテキストにエンコード情報を保存の前に、2、3、および 4 の場合、 **XMLNorm.SourceCharset**プロパティ。  
  
## <a name="see-also"></a>参照  
 [フラット ファイル逆アセンブラー パイプライン コンポーネント](../core/flat-file-disassembler-pipeline-component.md)   
 [フラット ファイル逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)   
 [Pipelines-AssemblerDisassembler (BizTalk Server サンプル フォルダー)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)