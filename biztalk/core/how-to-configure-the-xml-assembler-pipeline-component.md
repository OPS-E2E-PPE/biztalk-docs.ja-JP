---
title: "XML アセンブラー パイプライン コンポーネントを構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML Assembler [pipeline component], configuring
- messages, XML documents
- messages, envelopes
- configuring, pipeline components
- pipeline components, XML Assembler
ms.assetid: 6d883819-a1d4-4ad0-b08f-fcd7583134d6
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3cf69d5bd982571aefcf794d6ad32b0e69499470
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-xml-assembler-pipeline-component"></a>XML アセンブラー パイプライン コンポーネントを構成する方法
XML アセンブラー パイプライン コンポーネントを使用すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] からメッセージを送信する前に、XML ドキュメントを XML エンベロープにラップできます。  
  
### <a name="to-configure-the-properties-for-the-xml-assembler-pipeline-component"></a>XML アセンブラー パイプライン コンポーネントのプロパティを構成するには  
  
1.  XML アセンブラー パイプライン コンポーネントを、送信パイプラインのアセンブル ステージにドラッグします。  
  
2.  [プロパティ] ウィンドウでの**パイプライン コンポーネントのプロパティ**セクションで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**処理命令を追加します。**|**追加**: の値の**処理命令テキストの追加**既存のメッセージの処理命令を追加する必要があります。<br /><br /> **新規作成:**の値の**処理命令テキストの追加**で入力フィールドが上書きまたは既存のメッセージの指示を処理する必要があります。<br /><br /> 場合**新規作成**が選択されている、**処理命令テキストの追加**有効な処理命令を含める必要があります。<br /><br /> **無視**: 処理命令テキストがメッセージに存在する場合は削除されます。<br /><br /> 既定値:**追加**|  
    |**処理命令テキストを追加します。**|ターゲットの XML ドキュメントの先頭に追加する XML 処理命令を指定します。 **注:**処理命令テキストは、W3C 標準の XML 処理命令に準拠する必要があります。 <br /><br /> 既定値: なし|  
    |**XML 宣言を追加します。**|ときに**True**、送信ドキュメントに、次のような XML 宣言を追加します:`<?xml version='1.0' encoding='UTF-8'>`です。 エンコーディングは、ターゲット ドキュメントの実行時にエンコードによって決まります。<br /><br /> 既定値:**は True。**|  
    |**ドキュメント スキーマ**|ドキュメントに適用するスキーマの名前空間および型名を示します。 詳細については、次を参照してください。[スキーマ コレクション プロパティ エディターを使用する方法](../core/how-to-use-the-schema-collection-property-editor.md)です。 **注:**の 2 つ以上のスキーマを指定する場合に、「2 つ以上の選択されたスキーマは同じターゲットの名前空間を共有」エラーが発生する可能性があります、**ドキュメント スキーマ**プロパティです。 <br /><br /> 既定値: 空のコレクション|  
    |**エンベロープ スキーマ**|名前空間とスキーマまたはエンベロープに適用されるスキーマの型名を示します。 詳細については、次を参照してください。[スキーマ コレクション プロパティ エディターを使用する方法](../core/how-to-use-the-schema-collection-property-editor.md)です。 **注:**の 2 つ以上のスキーマを指定する場合に、「2 つ以上の選択されたスキーマは同じターゲットの名前空間を共有」エラーが発生する可能性があります、**エンベロープ スキーマ**プロパティです。 <br /><br /> 既定値: 空のコレクション|  
    |**バイト オーダー マークを保存します。**|アセンブラー コンポーネントで作成されたドキュメントにバイト オーダー マーク (BOM) を追加するかどうかを指定します。<br /><br /> 既定値:**は True。**|  
    |**処理命令スコープ**|処理命令を、最も外側のエンベロープに定義するかドキュメント レベルで定義するかを指定します。<br /><br /> 既定値:**ドキュメント**|  
    |**ターゲット文字セット**|送信メッセージのエンコードに使用される文字セットを指定します。<br /><br /> 既定値: なし|  
  
## <a name="see-also"></a>参照  
 [XML アセンブラー パイプライン コンポーネント](../core/xml-assembler-pipeline-component.md)   
 [ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md)   
 [XML とフラット ファイル プロパティ スキーマおよびプロパティ](../core/xml-and-flat-file-property-schema-and-properties.md)   
 [パイプライン AssemblerDisassembler (BizTalk Server Samples フォルダ)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)