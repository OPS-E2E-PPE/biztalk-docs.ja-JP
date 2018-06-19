---
title: ネイティブ パイプライン コンポーネントの構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Pipeline Designer, pipeline components
- pipeline components, configuring
- Pipeline Designer, code sample
- IPersistPropertyBag interface
ms.assetid: a3332a60-8cd6-43fa-9ecf-e1e54e71fef7
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94475334395f8c360bbb636cfa9cbadcf3bf4fe3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233178"
---
# <a name="configuring-native-pipeline-components"></a>ネイティブ パイプライン コンポーネントの構成
パイプライン コンポーネントは、独自のカスタム プロパティをデザイン時に公開できます。 コンポーネントのパブリック プロパティに読み取りと書き込みのアクセサーが実装されていた場合、これらのすべてのプロパティがパイプライン デザイナーに表示されます。 パイプライン デザイナーは、対応する宣言に従ってコンポーネントのプロパティを表示します。たとえば、プロパティが読み取り専用として宣言されていた場合、パイプライン デザイナーでもそのように表示されます。  
  
 カスタム パイプライン コンポーネントを実装する必要があります、 **IPersistPropertyBag**をこれらのカスタム プロパティの作成を有効にするインターフェイスです。 作成されたプロパティ、 **IPersistPropertyBag**インターフェイスは、Microsoft のプロパティ ウィンドウで設定できます[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ネイティブ パイプライン コンポーネントのすべてのプロパティと同様、します。 このセクションでは、追加される各パイプライン コンポーネントを構成するための手順について説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [ネイティブ パイプライン コンポーネントを構成する方法](../core/how-to-configure-native-pipeline-components.md)  
  
-   [BizTalk Framework アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-biztalk-framework-assembler-pipeline-component.md)  
  
-   [BizTalk Framework 逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-biztalk-framework-disassembler-pipeline-component.md)  
  
-   [BizTalk Framework スキーマおよびプロパティ](../core/biztalk-framework-schema-and-properties.md)  
  
-   [フラット ファイル アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)  
  
-   [フラット ファイル逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)  
  
-   [MIME/SMIME デコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)  
  
-   [MIME-SMIME エンコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)  
  
-   [MIME/SMIME プロパティ スキーマおよびプロパティ](../core/mime-smime-property-schema-and-properties.md)  
  
-   [パーティの解決パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-party-resolution-pipeline-component.md)  
  
-   [XML アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-assembler-pipeline-component.md)  
  
-   [XML 逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)  
  
-   [XML とフラット ファイル プロパティ スキーマおよびプロパティ](../core/xml-and-flat-file-property-schema-and-properties.md)  
  
-   [XML 検証パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-validator-pipeline-component.md)