---
title: 例外と SAP アダプターを使用したエラーの処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exceptions and error handling
- error handling, troubleshooting
- troubleshooting, exceptions and error handling
ms.assetid: 598a25c5-6905-4c0c-835b-159d827b2269
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d609e456e835cc14288f239bb53b252eb58f7e9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373449"
---
# <a name="exceptions-and-error-handling-with-the-sap-adapter"></a>例外と SAP アダプターを使用したエラーの処理
例外の一覧を表示する、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]をスローします。 これらを含めることができます。  

- 内部例外、.NET Framework をスローする、システム例外  

- LOB クライアント ライブラリをスローする LOB 例外。  

  詳細については、内部例外は、.NET Framework または SAP のマニュアルを参照してください。 例外には、問題の解決に役立つ可能性のある詳細なエラー メッセージも含まれます。  

## <a name="exception-descriptions"></a>例外の説明  

|例外|考えられる原因の説明|  
|---------------|---------------------------------|  
|ObjectDisposedException|アダプターは、アダプターのクライアントが破棄された後、応答 XMLReader にアクセスしようとするときに、この例外をスローします。|  
|XmlReaderGenerationException|アダプターは、出力メッセージから XmlReader を生成することができない場合、この例外をスローします。 SAP システムから受信したデータのいくつかの問題が原因可能性もあります。 内部例外と詳細については、エラー メッセージを探します。|  
|InvalidUriException|接続 URI に接続文字列に必要なコンポーネントがあるない場合に、この例外がスローされます。|  
|ConnectionException|SAP システムへの接続に問題がある場合、または、基になる接続が無効な SAP システムでエラーのため、またはネットワークの問題が原因になった場合、この例外がスローされます。|  
|TimeoutException|操作の指定したタイムアウトが過ぎているときは、この例外がスローされます。 内部例外には、指定したタイムアウト時間は十分に理由の詳細が含まれています。|  
|XmlReaderParsingException|アダプターは、指定した型をサポートしていない場合、または値が正しくありませんが、型指定されている場合、この例外をスローします。 また、入力 XML が正しくない可能性があります。 間違った値には、テキストまたは数字の最大の最大量を超える場合が含まれています。 入力 XML は、操作名または名前空間が正しくない場合は、適切でない可能性があります。|  
|RFCException (AdapterException から派生)|アダプターは、SAP システムから受信したエラーがある場合、この例外をスローします。 SAP システムから受信した実際の例外は、内部例外です。|  
|UnsupportedOperationException|アダプターは、アダプターのクライアントが無効なアクションを指定すると、この例外をスローします。|  
|MetadataException|アダプターは、メタデータの取得、参照、または検索中にエラーがある場合、この例外をスローします。|  

## <a name="see-also"></a>参照  
[SAP アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)