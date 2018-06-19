---
title: ドキュメントのフラット ファイル逆アセンブラー パイプライン コンポーネントでの検証 |Microsoft ドキュメント
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
ms.openlocfilehash: 120d4664f922a653d0d532ca25213f3cb60a4e67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239418"
---
# <a name="document-validation-in-the-flat-file-disassembler-pipeline-component"></a>フラット ファイル逆アセンブラー パイプライン コンポーネントにおけるドキュメントの検証
既定では、フラット ファイル逆アセンブラー コンポーネントで処理するドキュメントが検証されることはできません。 ただし、することが検証を有効に設定して、**ドキュメント構造の検証**にコンポーネントのプロパティを**True**、かを設定して、 **FFDasm.ValidateDocumentStructure**メッセージ コンテキスト プロパティを**True**です。 ドキュメント検証が有効な場合、フラット ファイル逆アセンブラーは、ヘッダー構造、トレーラー構造、およびドキュメント構造を検証して、ドキュメント、ヘッダー、およびトレーラーの各スキーマに準拠しているかを確認します。  
  
 フラット ファイル逆アセンブラーが空のフィールドを削除することができ、ときに記録**suppress_empty_nodes ="True"** で指定された、 **schemaInfo**フラット ファイル XSD スキーマで注釈。 使用する場合、 **schemaInfo**この方法で注釈は、空のフィールドとレコードは省略可能かどうかに関係なく、フラット ファイル逆アセンブラーを削除します。 XML 検証を使用する場合と検証エラーが発生 (フラット ファイル逆アセンブラーを設定するか**ドキュメント構造の検証**プロパティを**True**または XML 検証パイプライン コンポーネントを使用して). 検証エラーが発生した場合、メッセージが中断されます。 Suppress_empty_nodes プロパティの詳細については、次を参照してください。[追加のフラット ファイル プロパティ](../core/additional-flat-file-properties.md)です。  
  
## <a name="see-also"></a>参照  
 [フラット ファイル逆アセンブラー パイプライン コンポーネント](../core/flat-file-disassembler-pipeline-component.md)   
 [フラット ファイル逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)   
 [パイプライン AssemblerDisassembler (BizTalk Server Samples フォルダ)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)