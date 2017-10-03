---
title: "XML 情報は、XML アセンブラー パイプライン コンポーネントで要素を設定 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML Assembler [pipeline component], processing instructions
- Add XML declaration property
- XMLNorm.AddXMLDeclaration property
- pipeline components, XML Assembler
- XML Assembler [pipeline component], XML information set
ms.assetid: 5a262763-838e-476b-8117-30c94bc1d64a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b194b85c88f63036cd74fcd9838aa99e73de6556
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="xml-information-set-elements-in-the-xml-assembler-pipeline-component"></a>XML 情報は、XML アセンブラー パイプライン コンポーネントで要素を設定
XML アセンブラー コンポーネントでは、各種の XML 要素が次のように扱われます。  
  
|要素|Description|  
|-------------|-----------------|  
|comment|開始タグと終了タグ間のコメントが維持されます。|  
|CDATA|開始タグと終了タグ間の CDATA が維持されます。 プロパティ昇格や識別フィールドについては、CDATA の値は使用されません。|  
|処理命令|処理命令、ドキュメントの XML タグが処理される前に置かれた値に基づいて (詳細については、次を参照してください。 [XML アセンブラー パイプライン コンポーネントにおける処理命令](../core/processing-instructions-in-the-xml-assembler-pipeline-component.md))。 開始タグと終了タグの間にある処理命令が維持されます。 エンベロープの前、エンベロープ内、エンベロープの後のいずれの場合も、終了タグの後にある処理命令は無視されます。|  
|XML 宣言|XML 宣言文字列 (`<?xml version='1.0'? encoding='UTF-8'>` など) が XML アセンブラー パイプライン コンポーネントによって維持されるかどうかは、場合によって異なります。 によって制御されます、 **XML 宣言の追加**プロパティ、またはそれと同等のメッセージ コンテキスト**XMLNorm.AddXMLDeclaration**です。<br /><br /> このオプションが設定されている場合**True** XML 宣言は、ドキュメントに追加されます。 既に XML 宣言が存在した場合、既存の XML 宣言は上書きされます。<br /><br /> このオプションが設定されている場合**False**XML 宣言が追加されないこと、および既存の XML 宣言は削除されます。 メッセージ コンテキストでは、このプロパティ値は、パイプライン デザイナーで指定されたプロパティ値よりも優先されます。<br /><br /> 既定値: **True** (常には、XML 宣言を追加)|  
  
## <a name="see-also"></a>参照  
 [XML アセンブラー パイプライン コンポーネント](../core/xml-assembler-pipeline-component.md)   
 [XML アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-assembler-pipeline-component.md)   
 [パイプライン AssemblerDisassembler (BizTalk Server Samples フォルダ)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)