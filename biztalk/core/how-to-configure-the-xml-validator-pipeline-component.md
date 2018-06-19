---
title: XML 検証パイプライン コンポーネントを構成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML Validator [pipeline component]
- send pipelines, validating
- pipeline components, XML Validator
- receive pipelines, validating
ms.assetid: 3b3becaf-703c-4399-a5ed-e7082e31e6e9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 821ad6a1353c0aa29866fd36fe84a7ea6317690b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248386"
---
# <a name="how-to-configure-the-xml-validator-pipeline-component"></a>XML 検証パイプライン コンポーネントを構成する方法
XML 検証パイプライン コンポーネントは、送信パイプラインまたは受信パイプラインの逆アセンブル ステージとアセンブル ステージを除くすべてのステージで使用できます。  
  
### <a name="to-configure-the-properties-for-the-xml-validator-pipeline-component"></a>XML 検証パイプライン コンポーネントのプロパティを構成するには  
  
1.  XML 検証パイプライン コンポーネントを、受信パイプラインの検証ステージにドラッグします。  
  
2.  [プロパティ] ウィンドウでの**パイプライン コンポーネントのプロパティ**セクションで、次を設定します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**ドキュメント スキーマ**|ドキュメントに適用するスキーマの名前空間および型名を示します。 詳細については、次を参照してください。[スキーマ コレクション プロパティ エディターを使用する方法](../core/how-to-use-the-schema-collection-property-editor.md)です。 スキーマが指定されていない場合、実行時のスキーマ探索には、メッセージのターゲットの名前空間とルート要素名の情報が使用されます。 **注:** の 2 つ以上のスキーマを指定する場合に、「2 つ以上の選択されたスキーマは同じターゲットの名前空間を共有」エラーが発生する可能性があります、**ドキュメント スキーマ**プロパティです。 <br /><br /> 既定値: 空のコレクション|  
    |回復可能なインターチェンジ処理|False に設定されている場合、インターチェンジ全体が 1 つの単位として検証されることを示します (含まれるメッセージが失敗すると、インターチェンジ全体が中断されます)。<br /><br /> True に設定されている場合、インターチェンジ内のメッセージが検証ツールによって個別に抽出されることを示します。メッセージの経路を通るメッセージや中断されるメッセージが存在する可能性があります。<br /><br /> 回復可能なインターチェンジ処理の詳細については、次を参照してください。[回復可能なインターチェンジ処理](../core/recoverable-interchange-processing.md)です。|  
  
## <a name="see-also"></a>参照  
 [XML 検証パイプライン コンポーネント](../core/xml-validator-pipeline-component.md)   
 [ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md)