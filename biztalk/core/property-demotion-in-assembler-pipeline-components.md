---
title: "アセンブラー パイプライン コンポーネントでプロパティの降格 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML Assembler [pipeline component], properties
- pipeline components, properties
- BizTalk Framework Assembler [pipeline component], properties
- XML Assembler [pipeline component], about XML Assembler
- Flat File Assembler [pipeline component], properties
ms.assetid: c5275638-d594-4b0d-a818-b7a9460b41a6
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af634d302f01b18c91ebdbb7533673e8b9c545c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="property-demotion-in-assembler-pipeline-components"></a>アセンブラー パイプライン コンポーネントでプロパティの降格
プロパティの降格を使用して、メッセージ コンテキストのプロパティ値をメッセージ コンテキストまたはメッセージのヘッダーやトレーラーにコピーできます。 プロパティの降格を行うには、ドキュメントで指定した XPath 式、またはヘッダーやトレーラー スキーマで指定した XPath 式を使用します。  
  
 コンテキスト プロパティの日付データを結果のドキュメントに書き込む場合、BizTalk Server では、日付データがすべて UTC 形式であることが前提となります。  
  
 プロパティをデータに書き込むために使用される形式は、次の表の XSD データ型によって決まります。  
  
|データ型|Format|  
|---------------|------------|  
|xs:datetime|yyyy-MM-ddTHH:mm:ss.fffffffZ|  
|xs:date|yyyy-MM-ddZ|  
|xs:gDay|---ddZ|  
|xs:gMonth|--MM — Z|  
|xs:gMonthDay|--MM-ddZ|  
|xs:gYear|yyyyZ|  
|xs:gYearMonth|yyyy-MMZ|  
|xs:time|HH:mm:ss.fffffffZ|  
  
## <a name="property-demotion-and-envelopes"></a>プロパティの降格とエンベロープ  
 エンベロープ内のファイルをアセンブルするときに、システム名前空間の 1 つ以上、またはユーザーの名前空間の 1 つから値を降格すると役に立つことが多くあります。 一般的には次のようなシナリオが考えられます。  
  
-   バックエンド システムでデータのソースを追跡できるよう、システムに送信された元のファイル名を送信メッセージに含める場合。  
  
-   メッセージ本文のデータをヘッダーに書き込む場合。 たとえば注文書の処理では、出荷先名をエンベロープに書き込むと下流のシステムで役に立つことがあります。  
  
-   カスタム コードを記述せずに、多数の異なるフィールドを結合してヘッダーに含める場合。 XML アセンブラーやフラット ファイル アセンブラーのプロパティの降格で、この処理を実現できます。  
  
 重要な点としては、XML アセンブラー コンポーネントとフラット ファイル アセンブラー コンポーネントのどちらを使用しても、エンベロープとドキュメント本文用に使用するスキーマを指定できることです。 逆アセンブラーで使用されるスキーマと同じスキーマを選択したり、異なるフィールドで新しいエンベロープ スキーマを作成することもできます。  
  
 これらの概念の例は、次を参照してください。 [EnvelopeProcessing (BizTalk Server サンプル)](../core/envelopeprocessing-biztalk-server-sample.md)です。  
  
## <a name="see-also"></a>参照  
 [フラット ファイル アセンブラー パイプライン コンポーネント](../core/flat-file-assembler-pipeline-component.md)   
 [フラット ファイル アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)