---
title: "XML 逆アセンブラー パイプライン コンポーネントで検証を文書化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Validate Document Structure property
- pipeline components, XML Disassembler
- XML Disassembler [pipeline component], document validation
- XML Disassembler [pipeline component], warnings
ms.assetid: feb25033-46d3-48ed-8e1f-0cd123e94149
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2dcea790208bf0234c67c8c941e6355fb367d82
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="document-validation-in-the-xml-disassembler-pipeline-component"></a>XML 逆アセンブラー パイプライン コンポーネントにおけるドキュメントの検証
既定で、XML 逆アセンブラーは、スキーマに対する XML ドキュメントを検証しません。 ただし、設定して XML ドキュメントを検証する XML 逆アセンブラーを構成することができます、**ドキュメント構造の検証**プロパティです。  
  
> [!CAUTION]
>  昇格するフィールドを簡単なデータ型で宣言している一方で複雑なデータを含む場合、プロパティの昇格で予期しない結果が発生する可能性があります。 このシナリオを避けるためには、構成設定によってドキュメントの検証を実行する、XML 逆アセンブラー、**ドキュメント構造の検証**プロパティを**True**です。  
  
## <a name="see-also"></a>参照  
 [XML 逆アセンブラー パイプライン コンポーネント](../core/xml-disassembler-pipeline-component.md)   
 [XML 逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)