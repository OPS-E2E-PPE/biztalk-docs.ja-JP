---
title: 例外と、Oracle データベース アダプターによるエラー処理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exception, LOB
- exception, inner
- exceptions, error handling
- error handling, exceptions
ms.assetid: df9a1244-63cd-438e-8a06-99383fbeba2c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bd85c53a1e13d127883e463cafec742f2751722
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215170"
---
# <a name="exceptions-and-error-handling-with-the-oracle-database-adapter"></a>例外と、Oracle データベース アダプターによるエラー処理
このセクションでは、例外を一覧表示する、[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]をスローします。 これらを含めることができます。  
  
-   .NET Framework をスローするためのシステム例外である内部例外。  
  
-   LOB LOB クライアント ライブラリからスローされる例外。  
  
 詳細については、内部例外は、それぞれの .NET Framework または Oracle のマニュアルを参照してください。 例外には、問題の解決に役立つ詳細なエラー メッセージも含まれます。  
  
|例外|考えられる原因/説明|  
|---------------|---------------------------------|  
|XmlReaderParsingException|アダプターは、指定した型をサポートしていない場合、または種類の正しくない値が指定されている場合、この例外をスローします。 また、入力 XML は適切でない可能性があります。 正しくない値には、テキストまたは数字の最大の最大量を超えている場合が含まれています。 入力 XML が操作名または名前空間が正しくない場合は、正しくない可能性があります。|  
|UnsupportedOperationException|アダプターは、アダプターのクライアントが無効なアクションを指定すると、この例外をスローします。|  
|ArgumentException|引数に対して正しくない値が指定されている場合、アダプターはこの例外をスローします。|  
|NotImplementedException|XMLReader リーダー内のいくつかのメソッドが実装されていない場合、アダプターはこの例外をスローします。|  
|ArgumentNullException|アダプターは、必須の引数が指定されていない場合、この例外をスローします。|  
|ArgumentOutOfRangeException|存在しないエンティティまたは範囲外のエンティティにアクセスしようとすると、アダプターはこの例外をスローします。|  
|XmlReaderGenerationException|アダプターは、出力メッセージから XmlReader を生成することがあるときに、この例外をスローします。|  
|MetadataException|アダプターは、メタデータの取得、参照、または検索中にエラーがある場合、この例外をスローします。|  
|CredentialsException|アダプターは、ある問題を取得する値またはセキュリティ トークンを使用する場合、または必要な資格情報が指定されていない場合、この例外をスローします。|  
|InvalidUriException|アダプターは、接続 URI は、接続文字列に必要なコンポーネントを持っていない場合、この例外をスローします。|  
|使用して ConnectionException|アダプターは、ODP.NET を使用して Oracle データベースへの接続に問題がある場合、この例外をスローします。 内部例外には、Oracle は、例外が含まれています。|  
|TimeoutException|アダプターは、操作の指定したタイムアウトがも過ぎている場合、この例外をスローします。 内部例外には、指定されたタイムアウトだったための十分な理由の詳細が含まれています。|  
|ListenerException|アダプターは、対象システムからメッセージを受信することに問題がある場合、この例外をスローします。 このメッセージは、Oracle リスナーに関連する問題を示します。 内部例外には、問題の詳細があります。|  
|TargetSystemException|アダプターは、Oracle、エラーまたは無効な応答を返す場合、この例外をスローします。 内部例外には、Oracle のランタイム例外が含まれています。|  
|InvalidOperationException|アダプターは、アダプターは、ターゲット システムに無効な操作を実行しようとした場合、この例外をスローします。 内部例外には、実行中の無効な操作の詳細が含まれています。|  
|OverflowException|アダプターでは、この例外をスローした場合の実行中にデータセットまたは REF CURSOR の弱い型指定の内部 Oracle 数値データ型を含む操作大きな値が指定されて、それぞれの .NET 型に収まらないこれらの Oracle 数値データ型。|  
  
## <a name="see-also"></a>参照  
[Oracle データベース アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)