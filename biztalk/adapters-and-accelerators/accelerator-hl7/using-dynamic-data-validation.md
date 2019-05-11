---
title: 動的データの検証を使用して |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- dynamic data validation
- validating, dynamic data
ms.assetid: 8dac7f74-92a7-447c-97bf-b1f3ce39b614
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cad46899eb05520303116c08547a2b0e581608d8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65286435"
---
# <a name="using-dynamic-data-validation"></a>動的データ検証を使用します。
動的データの検証の重要な部分は、メッセージの内容に対して、メッセージの形式とメッセージの内容の検証を含む動的データを検証しています。 MicrosoftBizTalk Server は、XSD ファイルでは、ドキュメント スキーマを定義し、メッセージ形式を検証します。 ビジネス ルールは、メッセージの内容を定義する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ビジネス ルール エンジン ポリシーを検証します。 コンテンツの検証には、メッセージ インスタンス内のデータが、相対的な頻度で変わる可能性のあるデータと一致することの確認を含めることができます。 Microsoft[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]のコードを再コンパイルやサービスをシャット ダウンすることがなく、運用環境では、このデータを更新できるように、動的な方法でこの種類の検証を実装します。  
  
## <a name="validate-and-expose-data"></a>検証し、データの公開  
 動的データ検証 (DDV) を実行するのには、2 つの手順があります。  
  
- データを公開します。  
  
- そのデータを使用して検証規則を適用します。  
  
  DDV は、保存、公開すると、動的なデータをキャッシュ用の次のサポートを提供します。  
  
- ビジネス ルール エンジンまたはメッセージのクラスは、検証を実行します。  
  
- ビジネス ルール エンジンは、データベース テーブルの列のボキャブラリを使用してデータを公開します。 ビジネス ルール エンジンは、パイプラインまたはオーケストレーションから実行している規則セットを実装することによって、メッセージに対してこの動的なデータを検証します。  
  
- 既存の SQL インターフェイスなど、SQL Enterprise Manager、クエリ アナライザーでは、デザイン時にパッシブは動的なデータを公開します。  
  
- ビジネス ルール エンジン データベース テーブル列のボキャブラリ定義では、実行時に動的なデータを公開します。  
  
- ビジネス ルール エンジンは、実行時に、メッセージ インスタンス データを公開します。  
  
- ビジネス ルール エンジンの XML ドキュメントのボキャブラリの定義は、デザイン時に、メッセージ インスタンス データを公開します。  
  
- 作成できますルール デザイン時にビジネス ルール作成ツールのユーザー インターフェイスまたは直接でビジネス ルール言語 (BRL) XML テキスト エディターで。  
  
  ビジネス ルールとビジネス ルール エンジンの詳細については、「の開発とビジネス ルール」BizTalk Server のヘルプを参照してください。  
  
## <a name="extending-ddv"></a>DDV を拡張します。  
 HL7 ベースのクロス フィールド検証やデータ型の検証を変更する場合は、2 つのことを注意してくださいする必要があります。  
  
-   既存のルールを変更する場合は、再デプロイする必要はありません。  
  
-   、作成またはパイプライン コンポーネントに影響を与える新しいルールを削除するがコンパイルする必要があります。  
  
## <a name="see-also"></a>参照  
 [プログラミング ガイド](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md)   
 [メッセージ強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)