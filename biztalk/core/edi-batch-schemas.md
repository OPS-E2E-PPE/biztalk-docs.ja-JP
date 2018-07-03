---
title: EDI のバッチ スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 26da8036-8fe0-481e-b1e9-7f2e5b090768
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a25391fbc42b8e368a44f652ae691ff8bc2722dc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999227"
---
# <a name="edi-batch-schemas"></a>EDI のバッチ スキーマ
保存されたインターチェンジが BizTalk Server で処理される際には、以下の 3 つ以上のスキーマが使用されます。  

- 保存されたバッチ インターチェンジ (BaseArtifacts.dll に配置された X12_BatchSchema または Edifact_BatchSchema) のルート ノードを検証するためのバッチ スキーマ (インターチェンジ XML スキーマ)。  

- インターチェンジ、グループ、およびトランザクション セットのヘッダーとトレーラー (BaseArtifacts.dll に配置された X12ServiceSchema または EdifactServiceSchema) を検証するためのエンベロープ サービス スキーマ。 詳細については、次を参照してください。 [EDI サービスと管理スキーマ](../core/edi-service-and-control-schemas.md)します。  

- (プロジェクト内に配置された) バッチ インターチェンジ内にある各ドキュメントの種類のドキュメント スキーマ。 詳細については、次を参照してください。 [EDI ドキュメント スキーマ](../core/edi-document-schemas.md)します。  

  バッチ スキーマは、保存中の受信および送信の各バッチ インターチェンジを検証するために、実行時に使用されます。 また、バッチ スキーマは、メッセージ インスタンスを検証および生成するために、デザイン時にも使用されます。  

## <a name="batch-schemas-used-at-runtime"></a>実行時に使用されるバッチ スキーマ  
 バッチ スキーマの 2 つの標準的なバージョンが存在: 使用される X12_BatchSchema.xsd X12 エンコードと EDIFACT エンコードに使用される EDIFACT_BatchSchema.xsd です。 これらのスキーマは、制御セグメントを含むテンプレートです。 これらのスキーマは、次のルート名および名前空間を保持します。  


|       スキーマ        |       ルート ノード       |                    Namespace                     |
|---------------------|-----------------------|--------------------------------------------------|
|   X12_BatchSchema   |   X12InterchangeXML   | http://schemas.microsoft.com/Edi/X12_BatchSchema |
| Edifact_BatchSchema | EdifactInterchangeXML |     http://schemas.microsoft.com/Edi/Edifact     |

 受信パイプラインによって生成された XML インスタンス ドキュメントの種類は定数である (\<エンコード\>_BatchSchema.xml) この標準のスキーマを参照します。 このインスタンスはオーケストレーションのマップで使用できますが、使用前にドキュメントの種類と名前空間を変更して、必要な実際のスキーマをマップする必要があります。  

 バッチ スキーマは BaseArtifacts.dll に配置されるので、プロジェクトのデザイン時に指定する必要はありません。  

## <a name="batch-schemas-in-the-schema-store"></a>スキーマ ストア内のバッチ スキーマ  
 保存されたバッチを BizTalk Server で処理する際に実行時に使用されるバッチ スキーマは、BaseArtifacts.dll アセンブリに配置されます。 これらは、自動的にランタイム処理で利用できます。 Edifact_BatchSchema および X12_BatchSchema は、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI の BizTalk スキーマ ストアでも使用できます。 インターチェンジの生成または検証するデザイン時にのみ使用これらの各スキーマは。 いずれのスキーマも、受信パイプラインまたは送信パイプラインでの実行時の検証には必要ありません。  

## <a name="see-also"></a>参照  
 [EDI スキーマ](../core/edi-schemas.md)   
 [受信バッチの処理](../core/processing-incoming-batches.md)