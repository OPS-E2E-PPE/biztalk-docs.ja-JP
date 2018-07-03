---
title: XML 逆アセンブラーで認識されないメッセージのパイプライン コンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Allow Unrecognized Messages property
- XMLNorm.AllowUnrecognizedMessage property
- pipeline components, XML Disassembler
- XML Disassembler [pipeline component], unrecognized messages
ms.assetid: 5a6be3a8-0bac-426a-bf0b-5091191091de
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c7df0ea8abe05f866d5cb4f9fb86d85083e1690
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987667"
---
# <a name="unrecognized-messages-in-the-xml-disassembler-pipeline-component"></a>XML 逆アセンブラー パイプライン コンポーネントで認識されないメッセージ
次のような場合、XML 逆アセンブラー コンポーネントで、メッセージが "認識されないメッセージ" として処理されます。  
  
- 受信した XML メッセージに本文が含まれていない、本文が空である、または、本文のデータが空である  
  
- XML メッセージを受信したが、そのメッセージに必要なスキーマが展開されていない  
  
  に基づいて認識されないメッセージを処理、**認識されないメッセージを許可**プロパティ (または、 **XMLNorm.AllowUnrecognizedMessage**メッセージ コンテキストのプロパティ)。  
  
  場合**認識されないメッセージを許可**に設定されている**True**次のようにします。  
  
- メッセージに本文が含まれていない、本文が空 (null) である、または本文のデータが空 (null) である場合、そのメッセージは変更されずに XML 逆アセンブラーを通過します。  
  
- XML ドキュメントに関連するスキーマが展開されていない場合、その XML ドキュメントは変更されずに XML 逆アセンブラーを通過します。  
  
- スキーマがコンポーネントのプロパティで明示的に参照されているか、スキーマ解決プロセスで見つかったかどうかに関係なく、XML ドキュメントのスキーマが展開されていた場合、その XML ドキュメントは XML 逆アセンブラーによって処理されます。  
  
  場合**認識されないメッセージを許可**に設定されている**False**次のようにします。  
  
- メッセージに本文が含まれていない、本文が空 (null) である、または本文のデータが空 (null) である場合、そのメッセージは XML 逆アセンブラーを通過できません。  
  
- XML ドキュメントに関連するスキーマが展開されていない場合、その XML ドキュメントは XML 逆アセンブラーを通過できません。 エラーが報告され、可能な場合はメッセージが中断されます。  
  
- スキーマがコンポーネントのプロパティで明示的に参照されているか、スキーマ解決プロセスで見つかったかどうかに関係なく、XML ドキュメントのスキーマが展開されていた場合、その XML ドキュメントは XML 逆アセンブラーによって処理されます。  
  
  既定では、XML 逆アセンブラーは、認識されないメッセージを許可しません。  
  
> [!NOTE]
>  XML 以外のメッセージに関係なく、XML 逆アセンブラーによって処理されない、**認識されないメッセージを許可**プロパティの設定。  
  
## <a name="see-also"></a>参照  
 [XML 逆アセンブラー パイプライン コンポーネント](../core/xml-disassembler-pipeline-component.md)   
 [XML 逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)