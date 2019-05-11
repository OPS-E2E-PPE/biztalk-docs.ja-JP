---
title: フラット ファイル アセンブラー パイプライン コンポーネント |Microsoft Docs
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
ms.openlocfilehash: 666a6612be354b1c5cda9f1c4f40a3702cadfb78
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387931"
---
# <a name="flat-file-assembler-pipeline-component"></a>フラット ファイル アセンブラー パイプライン コンポーネント
フラット ファイル アセンブラーでは、個々 のドキュメントをバッチに結合し、必要に応じて、ヘッダーまたはトレーラー (またはその両方) を追加します。 フラット ファイルの詳細については、次を参照してください。[で区切られたレコードのフラット ファイル メッセージ](../core/flat-file-messages-with-delimited-records.md)します。 参照してください[位置指定レコードのフラット ファイル メッセージ](../core/flat-file-messages-with-positional-records.md)します。  
  
 フラット ファイル アセンブラー パイプライン コンポーネントは、受信 XML メッセージを検証しません。 XML 検証を確認するには、するには、送信パイプラインのプリアセンブル ステージでは、XML 検証コンポーネントを含めます。  
  
 フラット ファイル アセンブラー パイプライン コンポーネントは、Microsoft .NET Framework でサポートされる変換のみをサポートします。 カスタム テキスト ライターに書き込むことで、追加の変換を実行できます。  
  
 フラット ファイル アセンブラー パイプライン コンポーネントの構成方法の詳細については、次を参照してください。[フラット ファイル アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)します。  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージを 1 つのインターチェンジにアセンブルできません。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [フラット ファイル アセンブラー パイプライン コンポーネントでの文字エンコード](../core/character-encoding-in-the-flat-file-assembler-pipeline-component.md)  
  
-   [フラット ファイル アセンブラー パイプライン コンポーネントにおけるドキュメント構造の強化](../core/document-structure-enforcement-in-the-flat-file-assembler-pipeline-component.md)  
  
-   [フラット ファイル アセンブラー パイプライン コンポーネントでの区切り記号の保持](../core/retaining-delimiters-in-the-flat-file-assembler-pipeline-component.md)