---
title: "例外と、SAP アダプターのエラー処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exceptions and error handling
- error handling, troubleshooting
- troubleshooting, exceptions and error handling
ms.assetid: 598a25c5-6905-4c0c-835b-159d827b2269
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 043f76f7fc730430610b7598bbab208ca8b135a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="exceptions-and-error-handling-with-the-sap-adapter"></a>例外とエラーは、SAP アダプターの処理
例外の一覧を[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]をスローします。 これらを含めることができます。  
  
-   システム例外、.NET Framework をスローするは、内部例外  
  
-   LOB LOB クライアント ライブラリからスローされる例外。  
  
 詳細については、内部例外は、.NET Framework または SAP のマニュアルを参照してください。 例外には、問題を解決する助けとなる詳細なエラー メッセージも含まれます。  

## <a name="exception-descriptions"></a>例外の説明  
|例外|考えられる原因/説明|  
|---------------|---------------------------------|  
|ObjectDisposedException|アダプターは、アダプターのクライアントが、破棄された後、応答 XMLReader にアクセスしようとするときに、この例外をスローします。|  
|XmlReaderGenerationException|アダプターは、出力メッセージから XmlReader を生成することがあるときに、この例外をスローします。 SAP システムから受信したデータをいくつかの問題のため可能性もあります。 内部例外と詳細については、エラー メッセージを探します。|  
|InvalidUriException|接続 URI は、接続文字列に必要なコンポーネントを持っていない場合に、この例外がスローされます。|  
|使用して ConnectionException|SAP システムへの接続に問題がある場合、または基になる接続が無効で、SAP システムでエラーのためか、ネットワークの問題になる場合は、この例外がスローされます。|  
|TimeoutException|操作の指定したタイムアウトがも過ぎている場合は、この例外がスローされます。 内部例外には、指定されたタイムアウトだったための十分な理由の詳細が含まれています。|  
|XmlReaderParsingException|アダプターは、指定した型をサポートしていない場合、または種類の正しくない値が指定されている場合、この例外をスローします。 また、入力 XML が正しくない可能性があります。 正しくない値には、テキストまたは数字の最大の最大量を超えている場合が含まれています。 入力 XML が操作名または名前空間が正しくない場合は、正しくない可能性があります。|  
|RFCException (AdapterException から派生)|アダプターは、SAP システムから受信したエラーがある場合、この例外をスローします。 SAP システムから受信した実際の例外は、内部例外です。|  
|UnsupportedOperationException|アダプターは、アダプターのクライアントが無効なアクションを指定すると、この例外をスローします。|  
|MetadataException|アダプターは、メタデータの取得、参照、または検索中にエラーがある場合、この例外をスローします。|  
  
## <a name="see-also"></a>参照  
[SAP アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)