---
title: "BizTalk Framework アセンブラー パイプライン コンポーネントを構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components, BizTalk Framework Assembler
- BizTalk Framework Assembler [pipeline component], configuring
ms.assetid: 2fd51047-b9dd-4b98-a968-45d69148664e
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8337f5dcb2133d2a219d055751835b4ed14d379
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-biztalk-framework-assembler-pipeline-component"></a>BizTalk Framework アセンブラー パイプライン コンポーネントを構成する方法
### <a name="to-configure-the-properties-for-the-biztalk-framework-assembler-pipeline-component"></a>BizTalk Framework アセンブラー パイプライン コンポーネントのプロパティの構成  
  
1.  BizTalk Framework アセンブラー パイプライン コンポーネントを送信パイプラインのアセンブル ステージにドラッグします。  
  
2.  [プロパティ] ウィンドウ内で、**パイプライン コンポーネントのプロパティ**セクションで、次のプロパティ値を設定します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**処理命令テキストを追加します。**|このプロパティの値として処理命令を含むアセンブルされた XML ドキュメントを使用できます。 また、ドキュメントがアプリケーションの命令を含むことを許可します。 **注:**処理命令テキストは、W3C 標準の XML 処理命令に準拠する必要があります。 <br /><br /> 既定値: 追加|  
    |**XML 宣言を追加します。**|送信メッセージに XML 宣言を追加します。 次の XML 宣言が、送信メッセージに追加された true の場合、:`<?xml version='1.0' encoding='UTF8'>`です。 指定されたエンコーディングは、BizTalk Framework アセンブラー、エンコード情報を含む特定の実行時プロパティで使用されるエンコーディングとは異なります。<br /><br /> 既定値:**は True。**|  
    |**配信確認メッセージのアドレス**|BizTalk フレームワーク ドキュメントの配信確認メッセージの送信先アドレスを指定します。 **警告:**を有効になっている受信確認を BizTalk Framework アセンブラーを使用する場合は、する受信確認処理がバックログされデッドロックが生じる可能性があります。 デッドロックは、1 つのメッセージに対する複数の受信確認が別々のバッチ内で処理されるときに発生します。 この問題を回避するには、入力した配信確認メッセージのアドレス ポートの場所に対して、バッチ サイズを 1 に構成する必要があります。|  
    |**配信確認メッセージのアドレスの種類**|BizTalk フレームワーク ドキュメントの配信確認メッセージの送信先アドレスの種類を指定します。<br /><br /> 既定値: biz:**注:** biz: プレフィックスを Microsoft に送信元と送信先エンドポイントの組織の識別子を示すために使用された[!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)]と[!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)]、およびこれらのシステムとの相互運用。 プレフィックスは、既定値として提供されます。 たとえば、「="Biz:organizationname"、(src (& a) #124; dest) ="Party1"です。|  
    |**配信確認メッセージを送信した時間**|BizTalk フレームワーク ドキュメントの配信確認メッセージを、いつまでに受信するかを指定します (分単位)。<br /><br /> 既定値: 30|  
    |**送信先アドレス**|送信先アドレスを指定します。<br /><br /> 既定値: なし|  
    |**送信先アドレスの種類**|送信先アドレスの種類を指定します。<br /><br /> 既定値: biz:**注:** biz: プレフィックスは、組織内の送信元と送信先エンドポイントの識別子を示すために使用された[!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)]と[!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)]、およびこれらのシステムとの相互運用。 プレフィックスは、既定値として提供されます。 たとえば、「="Biz:organizationname"、(src (& a) #124; dest) ="Party1"です。|  
    |**ドキュメント スキーマ**|ドキュメントに適用するスキーマの名前空間および型名を示します。 詳細については、次を参照してください。[スキーマ コレクション プロパティ エディターを使用する方法](../core/how-to-use-the-schema-collection-property-editor.md)です。 **注:**の 2 つ以上のスキーマを指定する場合に、「2 つ以上の選択されたスキーマは同じターゲットの名前空間を共有」エラーが発生する可能性があります、**ドキュメント スキーマ**プロパティです。 <br /><br /> 既定値: 空のコレクション|  
    |**ドキュメントのトピック**|BizTalk フレームワーク ドキュメントの全体的な目的を一意に識別できる URI 参照を示します。<br /><br /> 既定値: なし|  
    |**エンベロープ スキーマ**|名前空間とスキーマまたはエンベロープに適用されるスキーマの型名を示します。 詳細については、次を参照してください。[スキーマ コレクション プロパティ エディターを使用する方法](../core/how-to-use-the-schema-collection-property-editor.md)です。 **注:**の 2 つ以上のスキーマを指定する場合に、「2 つ以上の選択されたスキーマは同じターゲットの名前空間を共有」エラーが発生する可能性があります、**エンベロープ スキーマ**プロパティです。 <br /><br /> 既定値: BTF2Schemas.btf2_envelope|  
    |**配信確認メッセージ要求を生成します。**|BizTalk フレームワーク ドキュメントの配信確認メッセージ要求を生成する必要があるかどうかを示します。 このプロパティは、BizTalk フレームワークの信頼できるメッセージ処理を有効にするために使用します。<br /><br /> 既定値:**は True。**|  
    |**メッセージの time to live (分単位) を**|メッセージの有効期限 (分単位) を指定します。<br /><br /> 既定値: 30|  
    |**処理命令**|XML インスタンス ドキュメントでの XML 処理命令の処理方法を指定します。<br /><br /> **追加**: の値**処理命令テキストの追加**既存のメッセージの処理命令を追加する必要があります。<br /><br /> **新規作成**: の値**処理命令テキストの追加**で入力フィールドが上書きまたは既存のメッセージの指示を処理する必要があります。<br /><br /> 場合**新規作成**が選択されている**処理命令テキストの追加**有効な処理命令を含める必要があります。<br /><br /> **無視**: 処理命令テキストがメッセージに存在する場合は削除されます。<br /><br /> 既定値:**追加**|  
    |**送信元アドレス**|送信元アドレスを指定します。<br /><br /> 既定値: なし|  
    |**ソースのアドレスの種類**|送信元アドレスの種類を指定します。<br /><br /> 既定値: biz:**注:** biz: プレフィックスは、組織内の送信元と送信先エンドポイントの識別子を示すために使用された[!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)]と[!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)]、およびこれらのシステムとの相互運用。 プレフィックスは、既定値として提供されます。 たとえば、「="Biz:organizationname"、(src (& a) #124; dest) ="Party1"です。|  
    |**ターゲット文字セット**|送信メッセージのエンコードに使用されるターゲット文字セットを指定します。<br /><br /> 既定値: なし|  
  
## <a name="see-also"></a>参照  
 [BizTalk Framework アセンブラー パイプライン コンポーネント](../core/biztalk-framework-assembler-pipeline-component.md)   
 [ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md)   
 [パイプライン AssemblerDisassembler (BizTalk Server Samples フォルダ)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)