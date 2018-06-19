---
title: BizTalk Framework 逆アセンブラー パイプライン コンポーネントを構成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, BizTalk Framework Disassembler
- disassembly stage, pipelines
- receive pipelines, disassembly stage
- BizTalk Framework Disassembler [pipeline component], configuring
ms.assetid: a5599bcb-dbee-46a5-a91d-3c54f901cd30
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07fefb577e5322fa303a1a1476a976b453adb083
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249194"
---
# <a name="how-to-configure-the-biztalk-framework-disassembler-pipeline-component"></a>BizTalk Framework 逆アセンブラー パイプライン コンポーネントを構成する方法
BizTalk Framework 逆アセンブラー パイプライン コンポーネントは、受信パイプラインの逆アセンブル ステージで使用します。  
  
### <a name="to-configure-the-properties-for-the-biztalk-framework-disassembler-pipeline-component"></a>BizTalk Framework 逆アセンブラー パイプライン コンポーネントのプロパティを構成するには  
  
1.  BizTalk Framework 逆アセンブラー パイプライン コンポーネントを、受信パイプラインの逆アセンブル ステージにドラッグします。  
  
2.  [プロパティ] ウィンドウでの**パイプライン コンポーネントのプロパティ**セクションで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**認識されないメッセージを許可します。**|逆アセンブラーを通過する認識されたスキーマを持たないメッセージを許可するかどうかを示します。<br /><br /> 既定値: **False**|  
    |**ドキュメント スキーマ**|ドキュメントに適用するスキーマの名前空間および型名を示します。 詳細については、次を参照してください。[スキーマ コレクション プロパティ エディターを使用する方法](../core/how-to-use-the-schema-collection-property-editor.md)です。<br /><br /> このプロパティで指定するスキーマは、一意のターゲットの名前空間を持つ必要があります。 同じ名前空間を持つスキーマがあると、ドキュメント インスタンスの検証が期待どおりに機能しない場合があります。 スキーマが同じ名前空間を持つ必要がある場合は、それぞれのスキーマに対して別々のパイプラインを作成して BizTalk Framework 逆アセンブラー パイプライン コンポーネントごとに 1 つのスキーマを指定するか、BizTalk Framework 逆アセンブラー パイプライン コンポーネントのパラメーターとしてスキーマを指定しないで 1 つのパイプラインを使用します。<br /><br /> 既定値: 空のコレクション|  
    |**エンベロープ スキーマ**|エンベロープに適用するスキーマの名前空間および型名を示します。 詳細については、次を参照してください。[スキーマ コレクション プロパティ エディターを使用する方法](../core/how-to-use-the-schema-collection-property-editor.md)です。<br /><br /> このプロパティで指定するスキーマは、一意のターゲットの名前空間を持つ必要があります。 同じ名前空間を持つスキーマがあると、ドキュメント インスタンスの検証が期待どおりに機能しない場合があります。 スキーマが同じ名前空間を持つ必要がある場合は、それぞれのスキーマに対して別々のパイプラインを作成して BizTalk Framework 逆アセンブラー パイプライン コンポーネントごとに 1 つのスキーマを指定するか、BizTalk Framework 逆アセンブラー パイプライン コンポーネントのパラメーターとしてスキーマを指定しないで 1 つのパイプラインを使用します。<br /><br /> 既定値: 空のコレクション|  
    |**ドキュメント構造を検証します。**|ときに**True**エンベロープを含む、逆アセンブラーへの受信メッセージの検証を実行します。 **注:** とき**True**の 2 つ以上のスキーマを指定する場合に、「2 つ以上の選択されたスキーマは同じターゲットの名前空間を共有」エラーが発生する可能性があります、**ドキュメント スキーマ**または**エンベロープ スキーマ**プロパティです。 <br /><br /> 既定値: **False**|  
  
## <a name="see-also"></a>参照  
 [BizTalk Framework 逆アセンブラー パイプライン コンポーネント](../core/biztalk-framework-disassembler-pipeline-component.md)   
 [ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md)   
 [パイプライン AssemblerDisassembler (BizTalk Server Samples フォルダ)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)   
 [ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md)