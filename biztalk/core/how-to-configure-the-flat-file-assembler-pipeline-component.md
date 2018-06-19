---
title: フラット ファイル アセンブラー パイプライン コンポーネントを構成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 7fe9c7a0720db68d8e629410dd3f0a443a99d7a4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248634"
---
# <a name="how-to-configure-the-flat-file-assembler-pipeline-component"></a>フラット ファイル アセンブラー パイプライン コンポーネントを構成する方法
フラット ファイル アセンブラー パイプライン コンポーネントは、XML ドキュメントがサーバーから送信される前に、このドキュメントを区切り記号付きフラット ファイル形式または位置指定フラット ファイル形式にシリアル化する場合に使用されます。  
  
### <a name="to-configure-the-properties-for-the-flat-file-assembler-pipeline-component"></a>フラット ファイル アセンブラー パイプライン コンポーネントのプロパティを構成するには  
  
1.  フラット ファイル アセンブラー パイプライン コンポーネントを、送信パイプラインのアセンブル ステージにドラッグします。  
  
2.  [プロパティ] ウィンドウでの**パイプライン コンポーネントのプロパティ**セクションで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**ドキュメント スキーマ**|XML 形式からフラット ファイル形式へのメッセージのシリアル化に使用するフラット ファイルのドキュメント スキーマを選択します。 スキーマを指定しない場合、実行時にスキーマ探索が行われます。 フラット ファイル ドキュメント スキーマは、BizTalk エディターで作成できます。<br /><br /> 既定値: なし|  
    |**ヘッダー スキーマ**|フラット ファイル メッセージのヘッダー部のスキーマを選択します。 ヘッダー スキーマは、という名前のメッセージ コンテキスト プロパティで指定することも**HeaderSpecName** xmlnorm 名前空間の下。 この場合、パイプライン デザイナーで指定されたヘッダー スキーマは無視されます。<br /><br /> フラット ファイル メッセージのヘッダー部のスキーマは、BizTalk エディターで作成できます。<br /><br /> 既定値: なし|  
    |**バイト オーダー マークを保存します。**|かどうかをバイトを追加するオーダー マーク (BOM)、アセンブラー コンポーネントによって生成されたドキュメントを指定します。<br /><br /> 既定値: **False**|  
    |**ターゲット文字セット**|送信メッセージのエンコードに使用されるターゲット文字セットを指定します。<br /><br /> 既定値: なし|  
    |**トレーラー スキーマ**|フラット ファイル メッセージのトレーラー部のスキーマを選択します。 BizTalk エディターでフラット ファイル メッセージのトレーラー部のスキーマを作成することができます。<br /><br /> 既定値: なし|  
  
## <a name="see-also"></a>参照  
 [フラット ファイル アセンブラー パイプライン コンポーネント](../core/flat-file-assembler-pipeline-component.md)   
 [ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md)   
 [XML とフラット ファイル プロパティ スキーマおよびプロパティ](../core/xml-and-flat-file-property-schema-and-properties.md)   
 [パイプライン AssemblerDisassembler (BizTalk Server Samples フォルダ)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)