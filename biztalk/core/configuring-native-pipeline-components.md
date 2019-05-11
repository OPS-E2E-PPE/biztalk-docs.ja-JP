---
title: ネイティブ パイプライン コンポーネントの構成 |Microsoft Docs
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
ms.openlocfilehash: 9b9d60c963231f61684cc58187d40bc23141ff1d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355299"
---
# <a name="configuring-native-pipeline-components"></a>ネイティブ パイプライン コンポーネントの構成
パイプライン コンポーネントは、デザイン時に、独自のカスタム プロパティを公開することができます。 コンポーネントで定義されているパブリック プロパティは、読み取りし、書き込みのプロパティが実装されるアクセサーを提供するパイプライン デザイナーでレンダリングされます。 パイプライン デザイナーはそれらの宣言に従ってコンポーネントのプロパティを表示します。たとえば、プロパティは読み取り専用として宣言されている場合、それが表示されますようパイプライン デザイナーで。  
  
 カスタム パイプライン コンポーネントを実装する必要があります、 **IPersistPropertyBag**これらのカスタム プロパティの作成を有効にするインターフェイス。 プロパティで作成された、 **IPersistPropertyBag**インターフェイスは、Microsoft のプロパティ ウィンドウで設定できる[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ネイティブ パイプライン コンポーネントのすべてのプロパティと同様、します。 このセクションでは、各パイプラインが含まれるコンポーネントを構成するための手順を説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [ネイティブ パイプライン コンポーネントを構成する方法](../core/how-to-configure-native-pipeline-components.md)  
  
-   [BizTalk Framework アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-biztalk-framework-assembler-pipeline-component.md)  
  
-   [BizTalk Framework 逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-biztalk-framework-disassembler-pipeline-component.md)  
  
-   [BizTalk Framework スキーマおよびプロパティ](../core/biztalk-framework-schema-and-properties.md)  
  
-   [フラット ファイル アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)  
  
-   [フラット ファイル逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)  
  
-   [MIME-SMIME デコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)  
  
-   [MIME-SMIME エンコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)  
  
-   [MIME-SMIME プロパティ スキーマおよびプロパティ](../core/mime-smime-property-schema-and-properties.md)  
  
-   [パーティの解決パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-party-resolution-pipeline-component.md)  
  
-   [XML アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-assembler-pipeline-component.md)  
  
-   [XML 逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)  
  
-   [XML とフラット ファイル プロパティ スキーマおよびプロパティ](../core/xml-and-flat-file-property-schema-and-properties.md)  
  
-   [XML 検証パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-validator-pipeline-component.md)