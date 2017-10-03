---
title: "XML 逆アセンブラー パイプライン コンポーネントを構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, pipeline components
- pipeline components, XML Disassembler
- XML Disassembler [pipeline component], configuring
- disassembly stage, pipelines
- receive pipelines, disassembly stage
ms.assetid: 93dd9148-4ae4-4868-b85d-66eada354f58
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 376daf04abb9bb555e9190fc819c3a3360cbe3cf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-xml-disassembler-pipeline-component"></a>XML 逆アセンブラー パイプライン コンポーネントを構成する方法
XML 逆アセンブラー パイプライン コンポーネントは、受信パイプラインの逆アセンブル ステージで使用されます。  
  
### <a name="to-configure-the-properties-for-the-xml-disassembler-pipeline-component"></a>XML 逆アセンブラー パイプライン コンポーネントのプロパティを構成するには  
  
1.  XML 逆アセンブラー パイプライン コンポーネントを、受信パイプラインの逆アセンブル ステージにドラッグします。  
  
2.  [プロパティ] ウィンドウでの**パイプライン コンポーネントのプロパティ**セクションで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**認識されないメッセージを許可します。**|認識された種類のメッセージを持たないメッセージを逆アセンブラーでパススルーすることを許可するかどうかを示します。<br /><br /> 既定値: **False**|  
    |**ドキュメント スキーマ**|ドキュメントに適用するスキーマの名前空間および型名を示します。 詳細については、次を参照してください。[スキーマ コレクション プロパティ エディターを使用する方法](../core/how-to-use-the-schema-collection-property-editor.md)です。<br /><br /> このプロパティで指定するスキーマは、一意のターゲットの名前空間を持つ必要があります。 同じ名前空間を持つスキーマがあると、ドキュメント インスタンスの検証が期待どおりに機能しない場合があります。 XML 逆アセンブラー パイプラインのパラメーターとしてすべてのスキーマを指定しない場合はスキーマである必要がありますが、同じ名前空間を持つ必要があります作成するそれぞれのスキーマに対して別々 のパイプラインおよび XML 逆アセンブラー パイプライン コンポーネントごとに 1 つのスキーマを指定するか 1 つのパイプラインを使用コンポーネント。<br /><br /> 既定値: 空のコレクション|  
    |**エンベロープ スキーマ**|エンベロープに適用するスキーマの名前空間および型名を示します。 詳細については、次を参照してください。[スキーマ コレクション プロパティ エディターを使用する方法](../core/how-to-use-the-schema-collection-property-editor.md)です。<br /><br /> このプロパティで指定するスキーマは、一意のターゲットの名前空間を持つ必要があります。 同じ名前空間を持つスキーマがあると、ドキュメント インスタンスの検証が期待どおりに機能しない場合があります。 XML 逆アセンブラー パイプラインのパラメーターとしてすべてのスキーマを指定しない場合はスキーマである必要がありますが、同じ名前空間を持つ必要があります作成するそれぞれのスキーマに対して別々 のパイプラインおよび XML 逆アセンブラー パイプライン コンポーネントごとに 1 つのスキーマを指定するか 1 つのパイプラインを使用コンポーネント。<br /><br /> 既定値: 空のコレクション|  
    |**回復可能なインターチェンジ処理**|False に設定されている場合、インターチェンジ全体が 1 つの単位として逆アセンブルされることを示します (含まれるメッセージが失敗すると、インターチェンジ全体が中断されます)。<br /><br /> True に設定されている場合、インターチェンジ内のメッセージが逆アセンブラーによって個別に抽出されることを示します。メッセージの経路を通るメッセージや中断されるメッセージが存在する可能性があります。<br /><br /> 回復可能なインターチェンジ処理の詳細については、次を参照してください。[回復可能なインターチェンジ処理](../core/recoverable-interchange-processing.md)です。|  
    |**ドキュメント構造を検証します。**|ときに**True**、ドキュメントおよび必要に応じてエンベロープ スキーマに対して着信メッセージの検証を実行します。<br /><br /> 昇格させたプロパティには既定値または固定値がないと、このプロパティに設定**False**プロパティは昇格されません。<br /><br /> 既定値: **False** **注:**とき**True**、2 つ以上のスキーマを指定する場合に、「2 つまたは複数の選択したスキーマは同じターゲットの名前空間を共有」エラーが発生する可能性があります**ドキュメント スキーマ**または**エンベロープ スキーマ**プロパティです。|  
  
## <a name="see-also"></a>参照  
 [XML 逆アセンブラー パイプライン コンポーネント](../core/xml-disassembler-pipeline-component.md)   
 [XML とフラット ファイル プロパティ スキーマおよびプロパティ](../core/xml-and-flat-file-property-schema-and-properties.md)   
 [パイプライン AssemblerDisassembler (BizTalk Server Samples フォルダ)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)   
 [ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md)