---
title: ドキュメントのフラット ファイル逆アセンブラー パイプライン コンポーネントの検証 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Validate Document Structure property
- FFDasm.ValidateDocumentStructure property
- Flat File Disassembler [pipeline component], validating documents
- pipeline components, Flat File Disassembler
ms.assetid: 8cd777e4-8aba-4c17-92e8-958e5dd57d09
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43802cde810d9803daa80ee8c070aecd8023eb57
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530812"
---
# <a name="document-validation-in-the-flat-file-disassembler-pipeline-component"></a>フラット ファイル逆アセンブラー パイプライン コンポーネントにおけるドキュメントの検証
既定では、フラット ファイル逆アセンブラー コンポーネントは、ドキュメントの処理を検証しません。 ただし、することが検証を有効に設定して、**ドキュメント構造の検証**にコンポーネントのプロパティを**True**、かを設定して、 **FFDasm.ValidateDocumentStructure**メッセージ コンテキスト プロパティを**True**します。 ドキュメントの検証が実行に設定されている場合、フラット ファイル逆アセンブラーは、ドキュメントの構造とドキュメント、ヘッダー、およびトレーラーのスキーマに準拠していることを確認するヘッダーとトレーラー構造を検証します。  
  
 フラット ファイル逆アセンブラーが空のフィールドを削除することができ、ときに記録**suppress_empty_nodes ="True"** で指定された、 **schemaInfo**フラット ファイル XSD スキーマで注釈。 使用する場合、 **schemaInfo**この方法で注釈は、空のフィールドとレコードは省略可能かどうかに関係なく、フラット ファイル逆アセンブラーを削除します。 XML 検証を使用する場合と検証エラーが発生 (フラット ファイル逆アセンブラーを設定するか**ドキュメント構造の検証**プロパティを**True**または XML 検証パイプライン コンポーネントを使用して). 検証エラーが発生した場合、メッセージが中断されます。 Suppress_empty_nodes プロパティの詳細については、次を参照してください。[追加のフラット ファイル プロパティ](../core/additional-flat-file-properties.md)します。  
  
## <a name="see-also"></a>参照  
 [フラット ファイル逆アセンブラー パイプライン コンポーネント](../core/flat-file-disassembler-pipeline-component.md)   
 [フラット ファイル逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)   
 [Pipelines-AssemblerDisassembler (BizTalk Server サンプル フォルダー)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)