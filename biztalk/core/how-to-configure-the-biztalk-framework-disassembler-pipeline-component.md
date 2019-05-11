---
title: BizTalk Framework 逆アセンブラー パイプライン コンポーネントを構成する方法 |Microsoft Docs
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
ms.openlocfilehash: 46ce50dc68f7a11cd63c7244c9abcb6930a08f3f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341144"
---
# <a name="how-to-configure-the-biztalk-framework-disassembler-pipeline-component"></a>BizTalk Framework 逆アセンブラー パイプライン コンポーネントを構成する方法
BizTalk Framework 逆アセンブラー パイプライン コンポーネントは、受信パイプラインの逆アセンブル ステージで使用する必要があります。  
  
### <a name="to-configure-the-properties-for-the-biztalk-framework-disassembler-pipeline-component"></a>BizTalk Framework 逆アセンブラー パイプライン コンポーネントのプロパティを構成するには  
  
1.  BizTalk Framework 逆アセンブラー パイプライン コンポーネントは、受信パイプラインの逆アセンブル ステージにドラッグします。  
  
2.  [プロパティ] ウィンドウでの**パイプライン コンポーネントのプロパティ**セクションで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**認識されないメッセージを許可します。**|逆アセンブラーを通過する認識されたスキーマを持たないメッセージを許可するかどうかを示します。<br /><br /> 既定値:**False**|  
    |**ドキュメント スキーマ**|名前空間とスキーマまたはドキュメントに適用するスキーマの型名を示します。 詳細については、次を参照してください。[スキーマ コレクション プロパティ エディターを使用する方法](../core/how-to-use-the-schema-collection-property-editor.md)します。<br /><br /> このプロパティで指定されたスキーマは、一意のターゲット名前空間にあります。 スキーマのいずれかがある同じ名前空間、ドキュメント インスタンスの検証はどおりに動作しない可能性があります。 BizTalk のパラメーターとしてすべてのスキーマを指定しない場合、スキーマにする必要がありますが、同じ名前空間を持つ必要がありますか、別々 のパイプラインの各スキーマの作成に BizTalk Framework 逆アセンブラー パイプライン コンポーネントごとに 1 つのスキーマを指定または 1 つのパイプラインを使用します。Framework 逆アセンブラー パイプライン コンポーネントです。<br /><br /> 既定値:空のコレクション|  
    |**エンベロープ スキーマ**|名前空間とスキーマまたはエンベロープに適用するスキーマの型名を示します。 詳細については、次を参照してください。[スキーマ コレクション プロパティ エディターを使用する方法](../core/how-to-use-the-schema-collection-property-editor.md)します。<br /><br /> このプロパティで指定されたスキーマは、一意のターゲット名前空間にあります。 スキーマのいずれかがある同じ名前空間、ドキュメント インスタンスの検証はどおりに動作しない可能性があります。 BizTalk のパラメーターとしてすべてのスキーマを指定しない場合、スキーマにする必要がありますが、同じ名前空間を持つ必要がありますか、別々 のパイプラインの各スキーマの作成に BizTalk Framework 逆アセンブラー パイプライン コンポーネントごとに 1 つのスキーマを指定または 1 つのパイプラインを使用します。Framework 逆アセンブラー パイプライン コンポーネントです。<br /><br /> 既定値:空のコレクション|  
    |**ドキュメント構造を検証します。**|ときに**True**エンベロープを含む、逆アセンブラーへの受信メッセージの検証を実行します。 **注:** ときに**True**、2 つ以上のスキーマを指定する場合に、「2 つ以上の選択したスキーマは同じターゲット名前空間を共有」エラーが発生する可能性があります、**ドキュメント スキーマ**または**エンベロープ スキーマ**プロパティ。 <br /><br /> 既定値:**False**|  
  
## <a name="see-also"></a>参照  
 [BizTalk Framework 逆アセンブラー パイプライン コンポーネント](../core/biztalk-framework-disassembler-pipeline-component.md)   
 [ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md)   
 [Pipelines-assemblerdisassembler (BizTalk Server Samples フォルダー)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)   
 [ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md)