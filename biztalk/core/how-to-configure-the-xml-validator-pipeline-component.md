---
title: XML 検証パイプライン コンポーネントを構成する方法 |Microsoft Docs
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
ms.openlocfilehash: 89c136079a6283fe5e2eebd063718f97008029fc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340223"
---
# <a name="how-to-configure-the-xml-validator-pipeline-component"></a>XML 検証パイプライン コンポーネントを構成する方法
XML 検証パイプライン コンポーネントは、送信 (アセンブルとアセンブル) を除くいずれかの段階で使用できるまたは受信パイプライン。  
  
### <a name="to-configure-the-properties-for-the-xml-validator-pipeline-component"></a>XML 検証パイプライン コンポーネントのプロパティを構成するには  
  
1.  XML 検証パイプライン コンポーネントは、受信パイプラインの検証ステージにドラッグします。  
  
2.  [プロパティ] ウィンドウでの**パイプライン コンポーネントのプロパティ**セクションで、次を設定します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**ドキュメント スキーマ**|名前空間とスキーマまたはドキュメントに適用するスキーマの型名を示します。 詳細については、次を参照してください。[スキーマ コレクション プロパティ エディターを使用する方法](../core/how-to-use-the-schema-collection-property-editor.md)します。 スキーマが指定されていない場合、実行時にスキーマ検出は、メッセージのターゲットの名前空間とルート要素名の情報を使用して行われます。 **注:** 2 つ以上のスキーマを指定する場合に、「2 つ以上の選択したスキーマは同じターゲット名前空間を共有」エラーが発生する可能性があります、**ドキュメント スキーマ**プロパティ。 <br /><br /> 既定値:空のコレクション|  
    |回復可能なインターチェンジ処理|"False"の場合は、(この場合、含まれるメッセージの失敗、インターチェンジ全体が中断されます)、ユニットとしてインターチェンジ全体を検証することを示します。<br /><br /> "True"の場合は、インターチェンジ内のメッセージは個別に抽出される検証ツールによってメッセージの経路と中断されている他のユーザー メッセージやメッセージの可能性を示します。<br /><br /> 回復可能なインターチェンジ処理の詳細については、次を参照してください。[回復可能なインターチェンジ処理](../core/recoverable-interchange-processing.md)します。|  
  
## <a name="see-also"></a>参照  
 [XML 検証パイプライン コンポーネント](../core/xml-validator-pipeline-component.md)   
 [ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md)