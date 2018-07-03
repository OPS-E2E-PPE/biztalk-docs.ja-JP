---
title: 例外と、Oracle Database アダプターによるエラー処理 |Microsoft Docs
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
ms.openlocfilehash: e12822c46af24e021df060e53d83c9b8f018e1f9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978611"
---
# <a name="exceptions-and-error-handling-with-the-oracle-database-adapter"></a>例外と、Oracle Database アダプターによるエラー処理
このセクションでは、例外を示します[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]をスローします。 これらを含めることができます。  
  
- .NET Framework をスローするシステムの例外である内部例外。  
  
- LOB クライアント ライブラリをスローする LOB 例外。  
  
  詳細については、内部例外は、それぞれの .NET Framework または Oracle のマニュアルを参照してください。 例外には、問題の解決に役立つ詳細なエラー メッセージも含まれます。  
  
|例外|考えられる原因の説明|  
|---------------|---------------------------------|  
|XmlReaderParsingException|アダプターは、指定した型をサポートしていない場合、または値が正しくありませんが、型指定されている場合、この例外をスローします。 また、入力 XML が正しくない可能性があります。 間違った値には、テキストまたは数字の最大の最大量を超える場合が含まれています。 入力 XML は、操作名または名前空間が正しくない場合は、適切でない可能性があります。|  
|UnsupportedOperationException|アダプターは、アダプターのクライアントが無効なアクションを指定すると、この例外をスローします。|  
|ArgumentException|アダプターは、引数について、間違った値が指定されている場合、この例外をスローします。|  
|NotImplementedException|XMLReader のリーダーでいくつかのメソッドが実装されていない場合、アダプターはこの例外をスローします。|  
|ArgumentNullException|アダプターは、必須の引数が指定されていない場合、この例外をスローします。|  
|ArgumentOutOfRangeException|アダプターが存在しないエンティティまたは範囲外のエンティティにアクセスしようとすると、この例外をスローします。|  
|XmlReaderGenerationException|アダプターは、出力メッセージから XmlReader を生成することができない場合、この例外をスローします。|  
|MetadataException|アダプターは、メタデータの取得、参照、または検索中にエラーがある場合、この例外をスローします。|  
|CredentialsException|アダプターは、問題を取得またはセキュリティ トークンを使用してある場合、または必要な資格情報が指定されていない場合、この例外をスローします。|  
|InvalidUriException|アダプターは、接続 URI には、接続文字列に必要なコンポーネントがない場合、この例外をスローします。|  
|ConnectionException|アダプターは、ODP.NET を使用して Oracle データベースへの接続に問題がある場合、この例外をスローします。 内部例外には、Oracle の例外が含まれています。|  
|TimeoutException|アダプターは、操作の指定したタイムアウトが過ぎている場合、この例外をスローします。 内部例外には、指定したタイムアウト時間は十分に理由の詳細が含まれています。|  
|ListenerException|アダプターは、ターゲット システムからメッセージを受信することで問題がある場合、この例外をスローします。 このメッセージは、Oracle リスナーに関連する問題を示します。 内部例外には、問題の内容があります。|  
|TargetSystemException|Oracle エラーまたは無効な応答を返す場合、アダプターはこの例外をスローします。 内部例外には、Oracle のランタイム例外が含まれています。|  
|InvalidOperationException|アダプターは、アダプターでは、ターゲット システムに対して無効な操作を実行しようとすると、この例外をスローします。 内部例外には、実行中の無効な操作の詳細が含まれています。|  
|OverflowException|アダプターこの例外をスローした場合の実行中にデータセットまたは厳密に型指定の REF CURSOR の内部で Oracle の数値データ型を格納している操作をそれぞれの .NET 型に収まらない Oracle 数値データ型をこれらの大きな値が指定されています。|  
  
## <a name="see-also"></a>参照  
[Oracle データベース アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)