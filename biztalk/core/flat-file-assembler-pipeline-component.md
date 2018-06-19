---
title: フラット ファイル アセンブラー パイプライン コンポーネント |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, Flat File Assembler
- Flat File Assembler [pipeline component]
ms.assetid: 3c851771-55b2-4d21-9291-d707dd66837c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 385b1f8ea6c2ce707069cde522ea2f6712290be7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245866"
---
# <a name="flat-file-assembler-pipeline-component"></a>フラット ファイル アセンブラー パイプライン コンポーネント
フラット ファイル アセンブラーは、個別のドキュメントを 1 つのバッチとしてまとめ、必要に応じて、ヘッダーやトレーラーを追加します。 フラット ファイルの詳細については、次を参照してください。[区切り記号付きレコードとフラット ファイル メッセージ](../core/flat-file-messages-with-delimited-records.md)です。 参照してください[位置指定レコードのフラット ファイル メッセージ](../core/flat-file-messages-with-positional-records.md)です。  
  
 フラット ファイル アセンブラー パイプライン コンポーネントでは、受信した XML メッセージは検証されません。 XML 検証を実行するには、送信パイプラインのプリアセンブル ステージに XML 検証コンポーネントを追加する必要があります。  
  
 フラット ファイル アセンブラー パイプライン コンポーネントでサポートされる変換は、Microsoft .NET Framework がサポートしている変換に限定されます。 カスタム テキスト ライターに出力することで、その他のさまざまな変換を実行できます。  
  
 フラット ファイル アセンブラー パイプライン コンポーネントの構成方法の詳細については、次を参照してください。 [、フラット ファイル アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)です。  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、複数のメッセージを 1 つのインターチェンジとしてアセンブルすることはできません。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [フラット ファイル アセンブラー パイプライン コンポーネントでの文字エン コード](../core/character-encoding-in-the-flat-file-assembler-pipeline-component.md)  
  
-   [フラット ファイル アセンブラー パイプライン コンポーネントにおけるドキュメント構造の強化](../core/document-structure-enforcement-in-the-flat-file-assembler-pipeline-component.md)  
  
-   [フラット ファイル アセンブラー パイプライン コンポーネントの区切り記号の保持](../core/retaining-delimiters-in-the-flat-file-assembler-pipeline-component.md)