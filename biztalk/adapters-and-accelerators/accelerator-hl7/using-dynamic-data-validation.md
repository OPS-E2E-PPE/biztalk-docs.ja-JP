---
title: "動的なデータ検証を使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dynamic data validation
- validating, dynamic data
ms.assetid: 8dac7f74-92a7-447c-97bf-b1f3ce39b614
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3387117648329828c9276545eafddca6872c4aa2
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="using-dynamic-data-validation"></a>動的なデータ検証を使用します。
動的データの検証の重要な部分は、メッセージの内容をメッセージの形式とメッセージの内容の検証を含む動的データに対して検証しています。 ドキュメント スキーマを[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Server は、XSD ファイルで実装して、定義して、メッセージの形式を検証します。 ビジネス ルールは、メッセージの内容を定義する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ビジネス ルール エンジン ポリシーを介してを検証します。 コンテンツの検証には、メッセージ インスタンス内のデータが、相対的な頻度で変化するデータと一致することの確認を含めることができます。 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]コードを再コンパイルやサービスをシャット ダウンすることがなく、運用環境でこのデータを更新できるように、動的な方法でこの種類の検証を実装します。  
  
## <a name="validate-and-expose-data"></a>検証し、データの公開  
 動的なデータ検証 (DDV) を実行するのには、2 つの手順があります。  
  
-   データを公開します。  
  
-   そのデータを使用する検証規則を適用します。  
  
 DDV は、保存、公開すると、動的なデータをキャッシュ用の次のサポートを提供します。  
  
-   ビジネス ルール エンジンまたはメッセージ クラスは、検証を実行します。  
  
-   ビジネス ルール エンジンは、データベース テーブル列のボキャブラリを使用してデータを公開します。 ビジネス ルール エンジンは、パイプラインまたはオーケストレーションから実行している規則セットを実装することによってメッセージに対してこの動的なデータを検証します。  
  
-   SQL Enterprise Manager、クエリ アナライザー、デザイン時にパッシブな公開の動的なデータなどの既存 SQL インターフェイス。  
  
-   ビジネス ルール エンジン データベース テーブル列のボキャブラリ定義では、実行時に動的なデータを公開します。  
  
-   ビジネス ルール エンジンは、実行時に、メッセージ インスタンス データを公開します。  
  
-   ビジネス ルール エンジンの XML ドキュメントのボキャブラリの定義は、デザイン時に、メッセージ インスタンス データを公開します。  
  
-   できますを作成するルール デザイン時にビジネス ルール作成ツールのユーザー インターフェイスまたは直接でビジネス ルール言語 (BRL) XML をテキスト エディターでします。  
  
 ビジネス ルールとビジネス ルール エンジンの詳細については、「開発ビジネス ルールを使用」BizTalk Server のヘルプを参照してください。  
  
## <a name="extending-ddv"></a>DDV を拡張します。  
 クロス フィールド検証の HL7 ベースまたはデータ型の検証を変更する場合は、次の 2 つを注意してください必要があります。  
  
-   既存のルールを変更する場合は、再展開する必要はありません。  
  
-   作成、パイプライン コンポーネントに影響する新しい規則を削除するか、し、再コンパイルがあります。  
  
## <a name="see-also"></a>参照  
 [プログラミング ガイド](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md)   
 [メッセージ強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)