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
ms.openlocfilehash: c09d381a74b8f5083b600de73b72ac3c4d4da00d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400828"
---
# <a name="unrecognized-messages-in-the-xml-disassembler-pipeline-component"></a>XML 逆アセンブラー パイプライン コンポーネントで認識されないメッセージ
XML 逆アセンブラー コンポーネントは、次の場合に「認識されない」としてメッセージを処理可能性があります。  
  
- XML メッセージには、本文のない、空の本文、または空の本文にデータを受け取りました。  
  
- XML メッセージを受信したが、そのスキーマが展開されていません。  
  
  に基づいて認識されないメッセージを処理、**認識されないメッセージを許可**プロパティ (または、 **XMLNorm.AllowUnrecognizedMessage**メッセージ コンテキストのプロパティ)。  
  
  場合**認識されないメッセージを許可**に設定されている**True**次のようにします。  
  
- XML 逆アセンブラーでメッセージ本文のない、空や null 本文では、または本文のパスで空や null データが変更されていません。  
  
- 展開されたスキーマが関連付けられていないパスを持つ XML ドキュメントでは、XML 逆アセンブラーで変更されていません。  
  
- 関連付けられている展開済みスキーマを持つ XML ドキュメントは、スキーマが明示的にコンポーネントのプロパティで参照されているか、スキーマ解決プロセスで見つかったかどうかに関係なく、XML 逆アセンブラーによって処理されます。  
  
  場合**認識されないメッセージを許可**に設定されている**False**次のようにします。  
  
- メッセージ本文のないか、空や null 本体、または本文に空や null データは、XML 逆アセンブラーは渡されません。  
  
- 関連付けられている展開されたスキーマがない XML ドキュメントは、逆アセンブラーでは渡されません。 エラーが報告され、可能であれば、メッセージは中断されます。  
  
- 関連付けられている展開済みスキーマを持つ XML ドキュメントは、スキーマが明示的にコンポーネントのプロパティで参照されているか、スキーマ解決プロセスで見つかったかどうかに関係なく、XML 逆アセンブラーによって処理されます。  
  
  既定では、XML 逆アセンブラーは、認識されないメッセージを許可しません。  
  
> [!NOTE]
>  XML 以外のメッセージに関係なく、XML 逆アセンブラーによって処理されない、**認識されないメッセージを許可**プロパティの設定。  
  
## <a name="see-also"></a>参照  
 [XML 逆アセンブラー パイプライン コンポーネント](../core/xml-disassembler-pipeline-component.md)   
 [XML 逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)