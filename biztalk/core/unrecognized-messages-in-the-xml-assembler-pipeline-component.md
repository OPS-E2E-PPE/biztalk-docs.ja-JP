---
title: XML アセンブラーで認識されないメッセージのパイプライン コンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XMLNorm.AllowUnrecognizedMessage property
- XML Assembler [pipeline component], unrecognized messages
- pipeline components, XML Assembler
ms.assetid: dd98512a-33a4-4b2e-977e-1b3a30747c6a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c61a82f051349b69d72089093f4646325490a943
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292608"
---
# <a name="unrecognized-messages-in-the-xml-assembler-pipeline-component"></a>XML アセンブラー パイプライン コンポーネントで認識されないメッセージ
XML アセンブラー コンポーネントでは、メッセージがメッセージは「認識されない」として扱われます。  
  
-   ボディ部がないです。  
  
-   空の本文。  
  
-   ボディ部にデータがありません。  
  
-   関連付けられているスキーマが展開されているはありません。  
  
> [!NOTE]
>  XML 以外のメッセージの処理は常に認識されないとします。  
  
 XML アセンブラーが認識されないメッセージを処理する方法がによって制御される、 **XMLNorm.AllowUnrecognizedMessage**メッセージ コンテキスト プロパティ。  
  
 ときに**XMLNorm.AllowUnrecognizedMessage**に設定されている**True**、XML アセンブラーが XML ドキュメントを次のように処理します。  
  
- メッセージのボディ部がないと、空の本文の一部またはデータが空の本文部分パスでは、アセンブラーを通じて変更されていません。  
  
- アセンブラーを通じて変更せずに関連付けられている展開されたスキーマがないドキュメントが渡されます。  
  
- 関連付けられている展開済みのスキーマを持つドキュメントは、(かにかかわらず、スキーマが明示的にコンポーネントのプロパティで参照されるスキーマの解決プロセスで見つかった) アセンブラーによって処理されます。  
  
  場合**XMLNorm.AllowUnrecognizedMessage**に設定されている**False**、XML アセンブラーが XML ドキュメントを次のように処理します。  
  
- メッセージのボディ部がないと、空の本文の一部または本文部分に空のデータは処理されません。 エラーが報告され、メッセージは中断されます。  
  
- 関連付けられている展開されたスキーマがないメッセージは処理されません。 エラーが報告され、メッセージは中断されます。  
  
- 関連付けられている展開済みのスキーマを持つドキュメントは、(かにかかわらず、スキーマが明示的にコンポーネントのプロパティで参照されるスキーマの解決プロセスで見つかった) アセンブラーによって処理されます。  
  
- 既定では、XML アセンブラー コンポーネントにより認識されないメッセージ (つまり、 **XMLNorm.AllowUnrecognizedMessages**と見なされます**False**メッセージ コンテキストに設定されていない場合)。  
  
## <a name="see-also"></a>参照  
 [XML アセンブラー パイプライン コンポーネント](../core/xml-assembler-pipeline-component.md)   
 [XML アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-assembler-pipeline-component.md)   
 [Pipelines-AssemblerDisassembler (BizTalk Server サンプル フォルダー)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)