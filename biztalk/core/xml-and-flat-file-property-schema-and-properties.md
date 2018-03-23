---
title: XML とフラット ファイル プロパティ スキーマおよびプロパティ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d917b82-62c6-489f-99a9-97e429b6f7c0
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb69a5375603d307c15a0bf884c924c0f6e6bb31
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
---
# <a name="xml-and-flat-file-property-schema-and-properties"></a>XML とフラット ファイル プロパティ スキーマおよびプロパティ
**http://schemas.microsoft.com/BizTalk/2003/xmlnorm-properties**名前空間には、フラット ファイル アセンブラとフラット ファイル逆アセンブラー パイプライン コンポーネントの構成に使用できるプロパティが含まれています。 次の表に、プロパティを示します。  

## <a name="properties-list"></a>[プロパティ]
  
|プロパティ|型|Description|  
|--------------|----------|-----------------|  
|**FlatFileHeaderDocument**|xs:string|受信フラット ファイル ドキュメントのヘッダーをこのプロパティに格納できます。|  
|**AllowUnrecognizedMessage**|xs:Boolean|認識されないメッセージを XML コンポーネントで処理するかどうかを指定します。|  
|**ProcessingInstruction**|xs:string|送信ドキュメント用の処理命令テキストです。|  
|**DocumentSpecName**|xs:string|ドキュメントの解析またはシリアル化のために使用する XML コンポーネントのスキーマです。<br /><br /> このプロパティで指定するスキーマは、一意のターゲットの名前空間 (# root) を持つ必要があります。 同じ名前空間 (# root) を持つスキーマがあると、ドキュメント インスタンスの検証が期待どおりに機能しない場合があります。 この名前空間 (# root) は一意にする必要があります。  スキーマが同じ名前空間 (# root) を持つ必要がある場合は、それぞれのスキーマに対して別々のパイプラインを作成して XML 逆アセンブラー パイプライン コンポーネントごとに 1 つのスキーマを指定するか、XML 逆アセンブラー パイプライン コンポーネントのパラメーターとしてスキーマを指定しないで 1 つのパイプラインを使用します。  これは、ターゲットの名前空間がない場合も機能します。|  
|**EnvelopeSpecName**|xs:string|ドキュメントの解析またはシリアル化のために使用するエンベロープ仕様です。<br /><br /> このプロパティで指定するスキーマは、一意のターゲットの名前空間 (# root) を持つ必要があります。 同じ名前空間 (# root) を持つスキーマがあると、ドキュメント インスタンスの検証が期待どおりに機能しない場合があります。 この名前空間 (# root) は一意にする必要があります。  スキーマが同じ名前空間 (# root) を持つ必要がある場合は、それぞれのスキーマに対して別々のパイプラインを作成して XML 逆アセンブラー パイプライン コンポーネントごとに 1 つのスキーマを指定するか、XML 逆アセンブラー パイプライン コンポーネントのパラメーターとしてスキーマを指定しないで 1 つのパイプラインを使用します。  これは、ターゲットの名前空間がない場合も機能します。|  
|**TargetCharset**|xs:string|送信メッセージのエンコードに使用する XML コンポーネントの文字セットです。|  
|**SourceCharset**|xs:string|XML 逆アセンブラーで処理する前のドキュメントのエンコードに使用する文字セットです。|  
|**ProcessingInstructionOption**|xs:int|送信ドキュメントへの処理命令の追加方法を指定します。 ProcessingInstructionOption の詳細については、次を参照してください。 [XML アセンブラー パイプライン コンポーネントにおける処理命令](../core/processing-instructions-in-the-xml-assembler-pipeline-component.md)です。|  
|**AddXMLDeclaration**|xs:boolean|送信ドキュメントに XML 宣言を追加するかどうかを指定します。|  
|**HeaderSpecName**|xs:string|フラット ファイル ドキュメントのヘッダーを指定します。|  
|**TrailerSpecName**|xs:string|フラット ファイル ドキュメントのトレーラーを指定します。|  
|**PromotePropertiesOnly**|xs:boolean|設定すると **True**, 、XML 逆アセンブラー コンポーネントがメッセージ エンベロープを削除するか、逆アセンブルしていません。 プロパティの昇格のみが実行されます。|  
  
## <a name="see-also"></a>参照  
-  [フラット ファイル アセンブラー パイプライン コンポーネントの構成](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)   
-  [フラット ファイル逆アセンブラー パイプライン コンポーネントの構成](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)   
-  [XML アセンブラー パイプライン コンポーネントの構成](../core/how-to-configure-the-xml-assembler-pipeline-component.md)   
-  [XML 逆アセンブラー パイプライン コンポーネントの構成](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)   
-  [ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md)   
-  **メッセージ コンテキスト プロパティ** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]