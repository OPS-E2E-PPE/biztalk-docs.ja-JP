---
title: "フラット ファイル逆アセンブラー パイプライン コンポーネントを構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Flat File Disassembler [pipeline component], configuring
- pipeline components, Flat File Disassembler
- messages, flat files
ms.assetid: c09996f6-6035-42a3-a75f-4def4ac39a95
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 403262bc18115923cdc5552a3b5e9e68d52f013e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-flat-file-disassembler-pipeline-component"></a>フラット ファイル逆アセンブラー パイプライン コンポーネントを構成する方法
フラット ファイル逆アセンブラー パイプライン コンポーネントは、フラット ファイル形式のドキュメントを逆アセンブルして XML 形式に変換するために使用されます。  
  
### <a name="to-configure-the-properties-for-the-flat-file-disassembler-pipeline-component"></a>フラット ファイル逆アセンブラー パイプライン コンポーネントのプロパティを構成するには  
  
1.  フラット ファイル逆アセンブラー パイプライン コンポーネントを、受信パイプラインの逆アセンブル ステージにドラッグします。  
  
2.  [プロパティ] ウィンドウでの**パイプライン コンポーネントのプロパティ**セクションで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**ドキュメント スキーマ**|フラット ファイル形式から XML 形式へメッセージを解析する際に使用するフラット ファイルのドキュメント スキーマを選択します。 解析用のフラット ファイル ドキュメント スキーマは、BizTalk エディターで作成できます。<br /><br /> 既定値: なし**注:**コンパイル時エラーが発生またはこのプロパティのスキーマを指定する必要があります。|  
    |**ヘッダー スキーマ**|フラット ファイル メッセージのヘッダー部のスキーマを選択します。 フラット ファイル メッセージのヘッダー部のスキーマは、BizTalk エディターで作成できます。<br /><br /> 既定値: なし|  
    |**ヘッダーを保存します。**|このプロパティを設定**True**メッセージ コンテキストで、フラット ファイル メッセージのヘッダーを格納する必要がある場合。 フラット ファイル メッセージのヘッダーを保存すると、ヘッダー構造およびコンテンツは BizTalk Server でメッセージと共に移動されます。 ヘッダーは、フラット ファイル アセンブラー パイプライン コンポーネントで、メッセージをフラット ファイル形式にシリアル化する際に使用されます。<br /><br /> ヘッダー スキーマ名は実行時に動的に取得されることがあります。そのため、保存したヘッダーがフラット ファイル アセンブラーでシリアル化されるとき、ヘッダー ドキュメントのデザイン時プロパティにヘッダー スキーマ名が含まれていない場合があります。 この場合、保存したヘッダーのメッセージの種類が使用されます。<br /><br /> 既定値: **False**|  
    |**トレーラー スキーマ**|フラット ファイル メッセージのトレーラー部のスキーマを選択します。 フラット ファイル メッセージのトレーラー部のスキーマは、BizTalk エディターで作成できます。<br /><br /> 既定値: なし|  
    |**回復可能なインターチェンジ処理**|False に設定されている場合、インターチェンジ全体が 1 つの単位として逆アセンブルされることを示します (含まれるメッセージが失敗すると、インターチェンジ全体が中断されます)。<br /><br /> True に設定されている場合、インターチェンジ内のメッセージが逆アセンブラーによって個別に抽出されることを示します。メッセージの経路を通るメッセージや中断されるメッセージが存在する可能性があります。<br /><br /> 回復可能なインターチェンジ処理の詳細については、次を参照してください。[回復可能なインターチェンジ処理](../core/recoverable-interchange-processing.md)です。|  
    |**ドキュメント構造を検証します。**|このプロパティを設定**True** (ヘッダー、ボディ、およびトレーラー) がスキーマに準拠しているかどうかを確認するフラット ファイル メッセージのすべての部分を検証する必要がある場合。 設定されているために、このオプションがフラット ファイル逆アセンブラーのパフォーマンスを低下**False**既定です。<br /><br /> 既定値: **False**|  
  
## <a name="see-also"></a>参照  
 [フラット ファイル逆アセンブラー パイプライン コンポーネント](../core/flat-file-disassembler-pipeline-component.md)   
 [ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md)   
 [XML とフラット ファイル プロパティ スキーマおよびプロパティ](../core/xml-and-flat-file-property-schema-and-properties.md)   
 [パイプライン AssemblerDisassembler (BizTalk Server Samples フォルダ)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)