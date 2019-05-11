---
title: フラット ファイル アセンブラー パイプライン コンポーネントを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, Flat File Assembler
- Flat File Assembler [pipeline component], configuring
- messages, flat files
ms.assetid: 5af61bba-4eb2-4bb9-a655-394a76d08d3b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0db8ce0e52ec4dfc5368f172747dc51ef7704626
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340875"
---
# <a name="how-to-configure-the-flat-file-assembler-pipeline-component"></a>フラット ファイル アセンブラー パイプライン コンポーネントを構成する方法
フラット ファイル アセンブラー パイプライン コンポーネントは、XML ドキュメントをサーバーから送信する前に区切り文字/位置指定フラット ファイル形式にシリアル化に使用されます。  
  
### <a name="to-configure-the-properties-for-the-flat-file-assembler-pipeline-component"></a>フラット ファイル アセンブラー パイプライン コンポーネントのプロパティを構成するには  
  
1.  フラット ファイル アセンブラー パイプライン コンポーネントは、送信パイプラインのアセンブル ステージにドラッグします。  
  
2.  [プロパティ] ウィンドウでの**パイプライン コンポーネントのプロパティ**セクションで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**ドキュメント スキーマ**|XML からフラット ファイル形式へのメッセージをシリアル化するために使用するフラット ファイル ドキュメント スキーマを選択します。 スキーマが指定されていない場合は、実行時のスキーマの検出が行われます。 BizTalk エディターでフラット ファイル ドキュメント スキーマを作成することができます。<br /><br /> 既定値:なし|  
    |**ヘッダー スキーマ**|フラット ファイル メッセージのヘッダー部のスキーマを選択します。 ヘッダー スキーマは、という名前のメッセージ コンテキスト プロパティで指定することも**HeaderSpecName** xmlnorm 名前空間の下。 この場合、パイプライン デザイナーで指定されたヘッダー スキーマが上書きされます。<br /><br /> BizTalk エディターでフラット ファイル メッセージのヘッダー部のスキーマを作成できます。<br /><br /> 既定値:なし|  
    |**バイト オーダー マークを保存します。**|かどうか、バイトを追加するオーダー マーク (BOM) アセンブラー コンポーネントによって生成されたドキュメントを指定します。<br /><br /> 既定値:**False**|  
    |**ターゲット文字セット**|送信メッセージのエンコードに使用されるターゲット文字セットを指定します。<br /><br /> 既定値:なし|  
    |**トレーラー スキーマ**|フラット ファイル メッセージのトレーラー部のスキーマを選択します。 BizTalk エディターでフラット ファイル メッセージのトレーラー部のスキーマを作成することができます。<br /><br /> 既定値:なし|  
  
## <a name="see-also"></a>参照  
 [フラット ファイル アセンブラー パイプライン コンポーネント](../core/flat-file-assembler-pipeline-component.md)   
 [ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md)   
 [XML とフラット ファイル プロパティ スキーマおよびプロパティ](../core/xml-and-flat-file-property-schema-and-properties.md)   
 [Pipelines-AssemblerDisassembler (BizTalk Server サンプル フォルダー)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)