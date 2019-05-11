---
title: XML 情報は、XML アセンブラー パイプライン コンポーネントで要素を設定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML Assembler [pipeline component], processing instructions
- Add XML declaration property
- XMLNorm.AddXMLDeclaration property
- pipeline components, XML Assembler
- XML Assembler [pipeline component], XML information set
ms.assetid: 5a262763-838e-476b-8117-30c94bc1d64a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c6662f65c82a79fb174fe3b97c10fc24351255b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65246400"
---
# <a name="xml-information-set-elements-in-the-xml-assembler-pipeline-component"></a>XML 情報は、XML アセンブラー パイプライン コンポーネントで要素を設定
XML アセンブラー コンポーネントは、次のように XML 情報セットの要素を処理します。  
  
|要素|説明|  
|-------------|-----------------|  
|comment|コメントは、タグと終了、ドキュメント内の XML タグの間で保持されます。|  
|CDATA|CDATA はドキュメント内の XML タグを開いたり閉じたり間保持されます。 CDATA の値がないプロパティの昇格に使用または識別フィールド。|  
|処理命令|それらの値に基づいて、ドキュメントの XML タグが処理される前に置かれた処理命令 (詳細については、次を参照してください。 [XML アセンブラー パイプライン コンポーネントにおける処理命令](../core/processing-instructions-in-the-xml-assembler-pipeline-component.md))。 処理命令の開始タグと終了タグは保持されます。 すべての命令は、前に、またはエンベロープの後に、XML 終了タグの後の処理命令は無視されます。|  
|XML 宣言|XML 宣言文字列など`<?xml version='1.0'? encoding='UTF-8'>`、XML アセンブラー パイプライン コンポーネントによって保持される場合があります。 これによって制御されますが、 **XML 宣言の追加**プロパティ、またはそれと同等のメッセージ コンテキスト**XMLNorm.AddXMLDeclaration**します。<br /><br /> このオプション設定されている場合**True** XML 宣言は、ドキュメントに追加されます。 既に XML 宣言が存在する場合は上書きされます。<br /><br /> このオプション設定されている場合**False**XML 宣言が追加されないことや、既存の XML 宣言は削除されます。 メッセージのコンテキストでこのプロパティの値は、パイプライン デザイナーで指定された値よりも優先されます。<br /><br /> 既定値:**True** (常には、XML 宣言を追加)|  
  
## <a name="see-also"></a>参照  
 [XML アセンブラー パイプライン コンポーネント](../core/xml-assembler-pipeline-component.md)   
 [XML アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-assembler-pipeline-component.md)   
 [Pipelines-AssemblerDisassembler (BizTalk Server サンプル フォルダー)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)