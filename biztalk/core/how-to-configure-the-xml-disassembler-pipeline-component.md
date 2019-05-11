---
title: XML 逆アセンブラー パイプライン コンポーネントを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, pipeline components
- pipeline components, XML Disassembler
- XML Disassembler [pipeline component], configuring
- disassembly stage, pipelines
- receive pipelines, disassembly stage
ms.assetid: 93dd9148-4ae4-4868-b85d-66eada354f58
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa38f975042256a52184c44e75f9b079dd00c6df
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385994"
---
# <a name="how-to-configure-the-xml-disassembler-pipeline-component"></a>XML 逆アセンブラー パイプライン コンポーネントを構成する方法
XML 逆アセンブラー パイプライン コンポーネントは、受信パイプラインの逆アセンブル ステージで使用する必要があります。  
  
### <a name="to-configure-the-properties-for-the-xml-disassembler-pipeline-component"></a>XML 逆アセンブラー パイプライン コンポーネントのプロパティを構成するには  
  
1.  XML 逆アセンブラー パイプライン コンポーネントは、受信パイプラインの逆アセンブル ステージにドラッグします。  
  
2.  [プロパティ] ウィンドウでの**パイプライン コンポーネントのプロパティ**セクションで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**認識されないメッセージを許可します。**|逆アセンブラーを通過する認識されているメッセージ型を持たないメッセージを許可するかどうかを示します。<br /><br /> 既定値:**False**|  
    |**ドキュメント スキーマ**|名前空間とスキーマまたはドキュメントに適用するスキーマの型名を示します。 詳細については、次を参照してください。[スキーマ コレクション プロパティ エディターを使用する方法](../core/how-to-use-the-schema-collection-property-editor.md)します。<br /><br /> このプロパティで指定されたスキーマは、一意のターゲット名前空間にあります。 スキーマのいずれかがある同じ名前空間、ドキュメント インスタンスの検証はどおりに動作しない可能性があります。 XML 逆アセンブラー パイプラインのパラメーターとしてすべてのスキーマを指定しない場合、スキーマにする必要がありますが、同じ名前空間を持つ必要がありますか、別々 のパイプラインの各スキーマの作成に XML 逆アセンブラー パイプライン コンポーネントごとに 1 つのスキーマを指定または 1 つのパイプラインを使用します。コンポーネント。<br /><br /> 既定値:空のコレクション|  
    |**エンベロープ スキーマ**|名前空間とスキーマまたはエンベロープに適用するスキーマの型名を示します。 詳細については、次を参照してください。[スキーマ コレクション プロパティ エディターを使用する方法](../core/how-to-use-the-schema-collection-property-editor.md)します。<br /><br /> このプロパティで指定されたスキーマは、一意のターゲット名前空間にあります。 スキーマのいずれかがある同じ名前空間、ドキュメント インスタンスの検証はどおりに動作しない可能性があります。 XML 逆アセンブラー パイプラインのパラメーターとしてすべてのスキーマを指定しない場合、スキーマにする必要がありますが、同じ名前空間を持つ必要がありますか、別々 のパイプラインの各スキーマの作成に XML 逆アセンブラー パイプライン コンポーネントごとに 1 つのスキーマを指定または 1 つのパイプラインを使用します。コンポーネント。<br /><br /> 既定値:空のコレクション|  
    |**回復可能なインターチェンジ処理**|"False"の場合は、(この場合、含まれるメッセージの失敗、インターチェンジ全体が中断されます) を単位としてインターチェンジ全体が逆アセンブルを示します。<br /><br /> "True"の場合は、インターチェンジ内のメッセージは個別に抽出される逆アセンブラーでメッセージの経路と中断されている他のユーザー メッセージやメッセージの可能性を示します。<br /><br /> 回復可能なインターチェンジ処理の詳細については、次を参照してください。[回復可能なインターチェンジ処理](../core/recoverable-interchange-processing.md)します。|  
    |**ドキュメント構造を検証します。**|ときに**True**、ドキュメントおよび必要に応じてエンベロープ スキーマに対して着信メッセージの検証を実行します。<br /><br /> 昇格させたプロパティには既定値または固定値がないと、このプロパティに設定した場合**False**プロパティは昇格されません。<br /><br /> 既定値:**False** **に注意してください。** ときに**True**、2 つ以上のスキーマを指定する場合に、「2 つ以上の選択したスキーマは同じターゲット名前空間を共有」エラーが発生する可能性があります、**ドキュメント スキーマ**または**エンベロープ スキーマ**プロパティ。|  
  
## <a name="see-also"></a>参照  
 [XML 逆アセンブラー パイプライン コンポーネント](../core/xml-disassembler-pipeline-component.md)   
 [XML とフラット ファイル プロパティ スキーマおよびプロパティ](../core/xml-and-flat-file-property-schema-and-properties.md)   
 [Pipelines-assemblerdisassembler (BizTalk Server Samples フォルダー)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)   
 [ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md)